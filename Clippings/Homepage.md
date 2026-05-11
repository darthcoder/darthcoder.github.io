---
title: "Homepage"
source: "https://kayhan.dev/posts/012-arrow-flight-vs-json-nextjs-snowflake-benchmark/"
author:
  - "[[Kayhan Babaee]]"
published: 2026-05-09
created: 2026-05-10
description: "A benchmark of three transport variants between a Snowflake warehouse and a Next.js SSR consumer: JSON over HTTP, Python Arrow Flight, and Go Arrow Flight."
tags:
  - "clippings"
---
### Arrow Flight vs JSON in Next.js: Benchmarking Python and Go Transports for Snowflake

For a Next.js dashboard backed by Snowflake, the path from warehouse to browser is familiar: a Python service runs the SQL, serializes the result to JSON, and the dashboard fetches it. Most panels render fast enough that the transport never feels like the bottleneck. But two questions had been nagging at me:

1. How much does moving from JSON to Arrow Flight over gRPC save?
2. Does rewriting the server in Go on top of ADBC give a meaningful jump beyond Python Flight, or is Python Flight already close to the ceiling?

I built three transport variants, ran them through the same Next.js SSR layer against the same Snowflake warehouse, and measured them across five row counts and two query shapes. This post is what came out.

## The Three Variants

I refer to them as Variant 1, 2, and 3 throughout. All three serve the same SQL queries. Only the transport changes.

### Variant 1: Python + JSON over HTTP

The control. A FastAPI server runs the query through SQLAlchemy, builds a list of dicts, and returns `json.dumps`.

```python
@app.post("/query")
async def query(body: dict):
    sql = body["sql"]
    params = body.get("params", {})

    session = get_bench_session()
    try:
        result = session.execute(text(sql), params)
        columns = list(result.keys())
        rows = [dict(zip(columns, row)) for row in result.fetchall()]
    finally:
        session.close()

    payload = json.dumps({"data": rows}, default=str).encode()
    return Response(content=payload, media_type="application/json")
```

This is the baseline most teams ship by default. SQLAlchemy session, `fetchall()`, list of dicts, JSON response.

### Variant 2: Python + Arrow Flight over gRPC

Variant 2 talks to Snowflake through `snowflake-connector-python` directly. (Variant 1 used the same connector indirectly through SQLAlchemy's adapter.) The server uses `pyarrow.flight.FlightServerBase` and streams the Arrow batches returned by `cur.fetch_arrow_batches()`.

```python
class BenchFlightServer(flight.FlightServerBase):
    def do_get(self, context, ticket):
        req = json.loads(ticket.ticket.decode("utf-8"))
        sql = req["sql"]
        params = req.get("params", {})

        conn = _get_conn()
        cur = conn.cursor()
        try:
            cur.execute(sql, params)
            tables = list(cur.fetch_arrow_batches())
            table = pa.concat_tables(tables) if len(tables) > 1 else tables[0]
            return flight.RecordBatchStream(table)
        finally:
            cur.close()
```

`fetch_arrow_batches` asks Snowflake to return Arrow IPC chunks over the wire instead of row tuples. The Snowflake Python connector decodes each chunk and yields it. `RecordBatchStream` wraps the result and Flight handles the gRPC transport.

The server holds a single persistent connection with auto-reconnect on stale sessions. Without that, every request opens a new Snowflake session. The handshake overhead is well known in the Snowflake driver world; I measured the equivalent overhead on the Go side below as roughly 1.5 seconds per request.

### Variant 3: Go + ADBC + Arrow Flight over gRPC

A Go server using the ADBC Snowflake driver. ADBC is the Arrow-native database connectivity API; the Go driver returns Arrow batches without an intermediate serialization step.

```
func (s *flightServer) DoGet(ticket *flight.Ticket, stream flight.FlightService_DoGetServer) error {
    var req queryRequest
    json.Unmarshal(ticket.Ticket, &req)

    cnxn, _ := s.getConn(stream.Context())
    stmt, _ := cnxn.NewStatement()
    defer stmt.Close()
    stmt.SetSqlQuery(req.SQL)

    reader, _, _ := stmt.ExecuteQuery(stream.Context())
    defer reader.Release()

    writer := flight.NewRecordWriter(stream, ipc.WithSchema(reader.Schema()))
    defer writer.Close()

    for reader.Next() {
        writer.Write(reader.Record())
    }
    return nil
}
```

(Error handling and the connection-reset path are elided here.)

The same connection-pooling lesson applied. Without a persistent connection, ADBC opens a new Snowflake session per request (1.5 second overhead). Reusing a single connection brings small queries down to about 200 ms.

## The Next.js Consumer

A single API route consumes all three variants. Variant 1 uses `fetch()`. Variants 2 and 3 share a Flight client built on `@grpc/grpc-js`.

```typescript
export const runtime = "nodejs";

export async function POST(
    req: NextRequest,
    { params }: { params: Promise<{ variant: string }> }
) {
    const { variant } = await params;
    const port = PORTS[variant];
    const body = await req.json();

    if (variant === "1") {
        const upstream = await fetch(\`http://localhost:${port}/query\`, {
            method: "POST",
            headers: { "Content-Type": "application/json" },
            body: JSON.stringify({ sql: body.sql, params: body.params }),
        });
        const buf = await upstream.arrayBuffer();
        const json = JSON.parse(new TextDecoder().decode(buf));
        return NextResponse.json({ rowCount: json.data.length });
    }

    const { ipcBytes } = await doGetFlight(port, body.sql, body.params);
    const table = tableFromIPC(ipcBytes);
    return NextResponse.json({ rowCount: table.numRows });
}
```

Three Next.js gotchas worth flagging up front:

- The route needs `export const runtime = "nodejs"`. `@grpc/grpc-js` does not run on the edge runtime.
- Add `serverExternalPackages: ["@grpc/grpc-js", "protobufjs"]` to `next.config.ts`. Turbopack tries to bundle `protobufjs` and breaks because it uses `fs.readFileSync` for descriptor files.
- `bun --bun run dev` does not work for this route. Bun's Node compatibility layer is missing pieces of the `http2` internals that `@grpc/grpc-js` depends on. `npx next dev` works.

The Flight client itself has a couple of protocol quirks on the wire (Arrow Flight uses a non-standard protobuf field number for the data body, and IPC messages need 8-byte alignment when reassembled), but the parsing is a one-time setup cost. I will not belabour it here.

## The Setup

### Environment

| Component | Version |
| --- | --- |
| Machine | Apple Silicon (arm64), macOS 26.4.1 |
| Python | 3.13.9 (CPython, Clang 20.1.4) |
| Go | 1.26.2 darwin/arm64 |
| Node.js | 25.9.0 |
| Next.js | 16.2.4 (Turbopack) |
| PyArrow | 23.0.1 |
| apache-arrow (JS) | 21.1.0 |
| @grpc/grpc-js | 1.14.3 |
| snowflake-connector-python | 4.4.0 |
| arrow-adbc (Go) | 1.4.0 |
| arrow-go | 18.1.1 |

Snowflake warehouse: standard tier, dedicated role. `USE_CACHED_RESULT = FALSE` so every query hits the warehouse.

### Methodology

End-to-end latency measured from a Python harness, through the Next.js API route, to Snowflake and back. Each scenario ran 10 times in randomized order to avoid warmup bias.

Two query shapes:

- **Numeric**: 10 columns, fixed-precision numbers
- **String**: 10 columns, variable-length text

Five row counts: 100, 1K, 10K, 100K, 1M.

## Latency

### p50, Numeric

| Rows | V1 | V2 | V3 |
| --- | --- | --- | --- |
| 100 | 428 ms | 278 ms | 273 ms |
| 1K | 416 ms | 260 ms | 243 ms |
| 10K | 721 ms | 690 ms | 645 ms |
| 100K | 1,650 ms | 1,543 ms | 1,567 ms |
| **1M** | **7,508 ms** | **5,403 ms** | **5,092 ms** |

### p50, String

| Rows | V1 | V2 | V3 |
| --- | --- | --- | --- |
| 100 | 428 ms | 202 ms | 197 ms |
| 1K | 554 ms | 512 ms | 618 ms |
| 10K | 951 ms | 862 ms | 827 ms |
| 100K | 1,408 ms | 1,333 ms | 1,317 ms |
| **1M** | **5,562 ms** | **3,442 ms** | **2,671 ms** |

### p95, Numeric

| Rows | V1 | V2 | V3 |
| --- | --- | --- | --- |
| 100 | 484 ms | 314 ms | 682 ms |
| 1K | 495 ms | 1,181 ms | 271 ms |
| 10K | 1,128 ms | 891 ms | 1,346 ms |
| 100K | 2,048 ms | 1,725 ms | 1,745 ms |
| **1M** | **13,400 ms** | **6,026 ms** | **5,932 ms** |

### p95, String

| Rows | V1 | V2 | V3 |
| --- | --- | --- | --- |
| 100 | 517 ms | 229 ms | 257 ms |
| 1K | 763 ms | 893 ms | 842 ms |
| 10K | 1,020 ms | 1,246 ms | 1,032 ms |
| 100K | 1,970 ms | 1,528 ms | 1,637 ms |
| **1M** | **7,431 ms** | **3,789 ms** | **3,032 ms** |

A few patterns stand out.

At small sizes (100 to 1K rows), Variants 2 and 3 are 30 to 50 percent faster than Variant 1. The latency floor for Snowflake itself is around 200 to 300 ms; the overhead in Variant 1 (SQLAlchemy session, list-of-dicts conversion, JSON encoding) adds roughly 150 ms on top of that, making Variant 1 take about 1.5x as long as the Flight variants at this scale.

At medium sizes (10K to 100K rows), the gap narrows. The query itself dominates and transport differences are measurable but not dramatic.

At 1M rows, Variant 1 is 50 percent slower than Variant 3 on the median for numeric (7.5 s vs 5.1 s) and roughly 2x slower for string (5.6 s vs 2.7 s). The p95 tail is the worse story for Variant 1: at 1M numeric rows, Variant 1 hits 13.4 s at the 95th percentile while Variants 2 and 3 stay under 6 s. That puts V1 numeric at roughly 1.8x its median, while the Flight variants stay within 10 to 15 percent of theirs across both query shapes. (The string workload is kinder to V1's tail at 1.34x.)

Variant 3's edge over Variant 2 is small at most sizes. At 1M string rows it widens to 22 percent on the median (2.7 s vs 3.4 s), which is the only place the Go variant clearly differentiates on raw latency.

## Memory: The Real Story

The latency numbers are interesting, but the memory numbers are where the real divergence shows up.

| Variant | Steady State | After 1M Query |
| --- | --- | --- |
| Variant 1 (Python + JSON) | ~440 MB | **2,242 MB** |
| Variant 2 (Python + Flight) | ~420 MB | **552 MB** |
| Variant 3 (Go + Flight) | ~130 MB | **357 MB** |

A single 1M-row request takes Variant 1 to 2.2 GB resident. Variant 2 holds at 552 MB. Variant 3 hits 357 MB.

The likely reason is that the JSON path materializes the result in multiple places at once:

1. SQLAlchemy buffers the full result as a list of row tuples after `fetchall()`
2. The route converts those tuples to a list of dicts (`{column: value}` per row)
3. `json.dumps` produces the encoded byte string while the dict list still exists

These representations live in memory simultaneously until the response is written and Python's garbage collector reclaims them. The benchmark only measured peak RSS, not the breakdown per stage; a 2.2 GB peak is consistent with multiple large allocations overlapping.

Variant 2 streams Arrow batches from Snowflake and concatenates them into a single Arrow table once. Variant 3 streams batches over the wire without ever holding the full result in a single allocation.

For pod sizing, the practical impact is large. A 4 GB pod can serve roughly one concurrent 1M-row request on Variant 1 before going down. Variant 2 fits about seven. Variant 3 fits about eleven. (Treating per-request peak RSS as the all-in cost, which is conservative; if memory releases between overlapping requests, the practical ceiling is higher.)

On a 1 GB pod (typical for a serverless deploy), Variant 1 cannot serve a 1M-row request at all. Variant 2 fits one. Variant 3 fits two or three.

If your service is memory-bound, the migration from Variant 1 to Variant 2 pays for itself before any latency consideration enters the conversation.

## Concurrency

I ran four parallel requests at the 1K-string scenario. The Python GIL plus the overhead of a fresh SQLAlchemy session per request made Variant 1's tail latency unstable.

| Variant | Mean | Stddev |
| --- | --- | --- |
| Variant 1 | 1,504 ms | 890 ms |
| Variant 2 | 518 ms | 46 ms |
| Variant 3 | 680 ms | 202 ms |

Variant 2's tight stddev (46 ms) is the most useful number here. For a dashboard hosting many panels at once, that predictability matters more than the median. Variant 1's 890 ms stddev means a panel that loaded fine in isolation can block the page when it loads alongside others.

Variant 3 has worse concurrency variance than Variant 2 in this test (202 ms stddev vs 46 ms). I did not dig into the cause, but suspect it relates to how ADBC serializes parallel requests through a single Snowflake connection.

## Client-Side Decode

Decode happens once on the Next.js SSR side and again in the browser if the data is shipped to the client. The cost differs by an order of magnitude at scale.

| Rows | V1 (`JSON.parse`) | V2/V3 (`tableFromIPC`) |
| --- | --- | --- |
| 100 | 0.1 ms | 0.2 to 0.3 ms |
| 1K | 0.7 ms | 0.3 to 0.4 ms |
| 10K | 6.5 ms | 0.6 ms |
| 100K | 68 ms | 1.0 to 1.2 ms |
| **1M** | **660 ms** | **3.5 to 4.5 ms** |

At 1M rows, `JSON.parse` blocks the SSR worker for 660 ms. `tableFromIPC` takes under 5 ms.

For server-side rendering, that is 660 ms of CPU on the worker per request. The browser pattern is similar in shape: I measured up to 10K rows directly in Chrome (7 to 10 ms for `JSON.parse` vs 3 to 4 ms for `tableFromIPC`). At 100K rows the JSON path blocks the main thread for 400 to 700 ms while Arrow stays under 5 ms. I did not measure the browser at 1M, but the SSR numbers suggest JSON would block for hundreds of ms longer than Arrow.

## Payload Size

| Rows | V1 (JSON) | V2 (Arrow) | V3 (Arrow) |
| --- | --- | --- | --- |
| 100 | 30 KB | 8 KB | 20 KB |
| 1K | 305 KB | 60 KB | 164 KB |
| 10K | 3.0 MB | 586 KB | 1.6 MB |
| 100K | 30 MB | 5.8 MB | 16 MB |
| **1M** | **289 MB** | **56 MB** | **153 MB** |

JSON is roughly 5x larger than Variant 2's Arrow output for fixed-precision numeric data. Arrow's columnar layout encodes 1M numeric rows in 56 MB; the same data in JSON is 289 MB.

Variant 3's payload is 2 to 3x larger than Variant 2's for the same data. The Python Snowflake connector strips null-heavy columns more and uses tighter type inference. ADBC preserves the full Snowflake schema metadata, which is closer to "raw" but more verbose on the wire.

Bandwidth matters most for mobile or remote clients. At 100 Mbit/s the JSON variant takes 23 seconds to transfer 1M rows. Variant 2 takes 4 seconds. Over a 4G mobile connection (10 Mbit/s sustained), the JSON variant takes about 4 minutes.

## A Caveat for Wide Schemas

The benchmark above used 10-column queries. I did not run the wide-schema case in this round, but in earlier exploration with 50+ column projections the picture inverts.

`fetch_arrow_batches()` and ADBC both trigger Snowflake's server-side conversion into Arrow IPC format. For 5 to 10 columns this is fast. With 50+ columns I saw the conversion add on the order of 2 to 3 seconds per 100K rows compared to the raw tuple path that the JSON variant uses.

If your dashboard panels return wide tables (50+ columns of mixed types), Variant 1 can win on raw query time even though it loses on memory, decode, and bandwidth.

This is the one place I would benchmark your own schema before assuming Arrow is faster.

## Decision Framework

| Scenario | Best Choice | Reason |
| --- | --- | --- |
| Small panels (under 10K rows), single user | Variant 1 | Latency floor is Snowflake itself |
| Concurrent dashboard load | Variant 2 | Tight tail latency under load |
| Large exports (100K to 1M rows) | Variant 3 | About 2x faster on string at 1M rows, 6x less memory than Variant 1 |
| Wide schemas (50+ cols) | Variant 1 | Snowflake's Arrow conversion adds overhead (observed separately, not in this benchmark) |
| Mobile or bandwidth-constrained clients | Variant 2 | 5x smaller payload than JSON |
| Memory-constrained pods (1 to 4 GB) | Variant 2 or 3 | Variant 1 OOMs at 1M rows |
| Browser hydration on critical path | Variant 2 or 3 | 150x faster SSR decode at 1M rows |

## Migrating Variant 1 to Variant 2

This is the path I would take first for almost any production service. The migration is smaller than it sounds because:

- The Snowflake driver stays the same
- The Python language stays the same
- The deployment model stays the same
- The Next.js API route is the only place that needs new client code

The actual changes:

1. Replace FastAPI with `pyarrow.flight.FlightServerBase`
2. Replace `fetchall()` plus `dict(zip(...))` with `cur.fetch_arrow_batches()`
3. Replace `JSONResponse` with `flight.RecordBatchStream`
4. On the Next.js side, replace `fetch()` with a Flight client built on `@grpc/grpc-js`
5. Set `runtime = "nodejs"` and add `@grpc/grpc-js` to `serverExternalPackages` in `next.config.ts`

The Flight client takes a couple of evenings to write because of the protocol quirks I mentioned, but you only write it once.

## Migrating Variant 2 to Variant 3

Variant 3 gives you better memory and tail latency at 1M rows. The cost is operational:

- A second runtime in your stack (Go alongside Python)
- Manual connection pooling and reconnect logic in Go
- ADBC's error behaviour is less polished than the Python connector
- The resulting service does one thing (query Snowflake, stream Arrow), so you are maintaining a small piece of dedicated infrastructure

For the workloads I tested, Variant 2 was the sweet spot. I would reach for Variant 3 if I were running export endpoints serving 1M+ row downloads on small pods, or if the service had no business logic and could afford to be a thin proxy in a different language.

## Final Takeaway

The two questions I opened this post with had clear answers.

**Is Arrow Flight worth it over JSON?** For any workload above "small dashboard with a single user", yes. The memory savings alone justify the change at scale: 552 MB vs 2.2 GB at 1M rows is the difference between fitting in a 1 GB pod and crashing it. The latency and bandwidth wins come along for free.

**Does Go give you a meaningful jump over Python Flight?** Sometimes. At 1M rows the median latency win is real (5.1 s vs 5.4 s numeric, 2.7 s vs 3.4 s string). The p95 tail is tighter for V3 on string (3.0 s vs 3.8 s) but essentially the same on numeric (5.9 s vs 6.0 s). The memory win is large (357 MB vs 552 MB). At 1K to 100K rows, the difference is noise. If you have a workload that lives at the high end and a service architecture that can absorb a Go runtime, Variant 3 buys you headroom. Otherwise Variant 2 is good enough.

The result that surprised me most was how often Variant 1 still wins. For wide schemas, Snowflake's own Arrow conversion overhead can wipe out the wire-level advantage Arrow gives you. Benchmark your actual schema shape before assuming Arrow is faster everywhere.