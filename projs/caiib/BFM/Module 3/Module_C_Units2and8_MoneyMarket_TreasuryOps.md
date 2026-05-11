# Module C — Units 2 & 8: Money Market + Treasury Operations & Technology
### CAIIB BFM | Light Units — Trivia Pass

---

## Unit 2: Money Market & Call Money Market

### What It Is
```
Short term borrowing and lending — typically under 1 year.
Banks borrow here when they're short of funds TODAY.
Banks lend here when they have surplus funds TODAY.
```

### The Money Market Instruments (Know These Cold)

| Instrument | Tenor | Who Issues | Plain English |
|---|---|---|---|
| **Call Money** | Overnight (1 day) | Banks | Banks lend to each other overnight |
| **Notice Money** | 2–14 days | Banks | Same as call, slightly longer |
| **Term Money** | 15 days–1 year | Banks | Fixed term interbank lending |
| **T-Bills** | 91, 182, 364 days | Government | Short term govt borrowing |
| **CPs** (Commercial Paper) | 7 days–1 year | Corporates | Corporates borrow short term |
| **CDs** (Certificate of Deposit) | 7 days–1 year | Banks | Banks raise short term deposits |
| **CBLO / TREPS** | Overnight–1 year | All | Collateralised borrowing (RBI platform) |

### The Rate Hierarchy
```
Repo Rate (RBI) → sets the floor/ceiling
        ↓
Call Money Rate → floats daily based on demand/supply
        ↓
T-Bill Rate → slightly higher than repo, risk-free
        ↓
CP Rate → higher than T-Bill (corporate = more risk)
        ↓
CD Rate → between T-Bill and CP
```

> **Rule:** Risk goes up → Rate goes up. Government < Bank < Corporate. Always.

### Call Money Specific Rules
```
Participants: Scheduled Commercial Banks + Primary Dealers ONLY
              (NOT corporates, NOT NBFCs in call money)

Rate: Purely market determined — RBI does not fix it
      BUT stays close to Repo rate corridor

If banks have surplus → call rate falls (supply > demand)
If banks have deficit → call rate rises (demand > supply)
```

### Decision Tree
```
Q: Overnight borrowing between banks?
→ Call Money

Q: 7–14 day borrowing between banks?
→ Notice Money

Q: Corporate issuing short term paper?
→ Commercial Paper (CP)

Q: Bank issuing short term deposit instrument?
→ Certificate of Deposit (CD)

Q: Who can participate in call money?
→ Scheduled Commercial Banks + Primary Dealers ONLY

Q: What determines call money rate?
→ Market forces (demand/supply) within RBI's repo corridor
```

### Elimination Rules
- Corporates can borrow in call money market → **WRONG** — only banks + PDs
- RBI fixes call money rate → **WRONG** — market determined
- CP can be issued by banks → **WRONG** — CPs are corporate, CDs are bank
- T-Bills have credit risk → **WRONG** — government paper = zero credit risk

---

## Unit 8: Treasury Operations & Technology

### What It Is
```
How treasury actually runs day to day.
Systems, processes, platforms, controls.
Pure trivia — no numericals.
```

### The Dealing Room Structure

```
FRONT OFFICE → Dealers take positions, execute trades
MID OFFICE   → Risk monitoring, P&L, limit tracking (independent)
BACK OFFICE  → Settlement, confirmation, reconciliation (independent)

Same rule as Module B Unit 8 — front never controls mid or back.
```

### Key Platforms & Systems

| Platform/System | What it does |
|---|---|
| **NDS-OM** | RBI's platform for G-Sec trading (Negotiated Dealing System - Order Matching) |
| **CCIL** | Clears and settles forex + G-Sec trades (central counterparty) |
| **SWIFT** | Messaging system for international transactions |
| **Bloomberg / Reuters** | Market data, pricing, dealing terminals |
| **CBS** (Core Banking System) | Bank's main system — treasury integrates with this |
| **TMS** (Treasury Management System) | Dedicated treasury software — deal capture, risk, reporting |

### The Trade Lifecycle
```
Deal Capture (Front Office)
      ↓
Confirmation (Back Office checks counterparty confirms)
      ↓
Risk & P&L Update (Mid Office marks to market)
      ↓
Settlement (Back Office — money and securities exchange)
      ↓
Reconciliation (Back Office — books match nostro/vostro)
```

### STP — Straight Through Processing
```
STP = Trade flows from capture to settlement with ZERO manual intervention
    = Reduces operational risk
    = Faster settlement
    = Fewer errors

Higher STP % = better treasury operations
```

### Key Treasury Technology Concepts

| Term | Plain English |
|---|---|
| **STP** | Automated end-to-end processing, no manual touch |
| **Mark to Market (MTM)** | Revalue positions at current market price daily |
| **Nostro** | Our account held at a foreign bank ("our money abroad") |
| **Vostro** | Foreign bank's account held with us ("their money here") |
| **DVP** | Delivery vs Payment — securities and cash settle simultaneously |

### Nostro / Vostro (Classic Exam Trap)
```
From YOUR bank's perspective:
NOSTRO = YOUR account in THEIR books (you hold money abroad)
VOSTRO = THEIR account in YOUR books (they hold money here)

Same account, two names, depends on whose perspective.
```

### Decision Tree
```
Q: Where are G-Secs traded electronically?
→ NDS-OM

Q: Who clears and settles G-Sec and forex trades?
→ CCIL

Q: International messaging for bank transactions?
→ SWIFT

Q: What is MTM?
→ Revaluing positions at today's market price (daily)

Q: Nostro vs Vostro?
→ Nostro = our account abroad | Vostro = their account with us

Q: What reduces operational risk in settlement?
→ STP + DVP
```

### Elimination Rules
- CCIL is a trading platform → **WRONG** — it's a clearing and settlement platform
- NDS-OM is for forex trading → **WRONG** — it's for G-Sec trading
- Nostro and Vostro are different accounts → **WRONG** — same account, different perspective
- MTM is done monthly → **WRONG** — daily

---

## Cross-Unit Link

```
Unit 2 (Money Market) feeds Unit 8 (Treasury Operations):

Call money shortage → Treasury borrows in call market (Unit 2)
                   → Deal captured in TMS (Unit 8)
                   → Settled via CCIL (Unit 8)
                   → Reconciled against Nostro (Unit 8)
```

---

*CAIIB BFM — Module C, Units 2 & 8 | Exam: First Sunday of June 2026*
