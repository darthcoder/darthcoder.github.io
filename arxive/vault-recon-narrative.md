# Vault Recon Narrative — for `.claude/memory.md`

*Compiled 2026-05-03 from W18-series delta notes and recon of `projs/`, `staging/`, `pub/`, `areas/periodic/weekly/`. Intended to be appended to `.claude/memory.md` so future sessions can orient quickly.*

---

## What this vault actually is

A personal knowledge graph in Tolaria (Markdown + YAML frontmatter), but in practice it operates as **a working chamber for a single author across multiple registers simultaneously**. It is not a notebook, not a wiki, not a journal — it is all three running in parallel, with structural traffic between them.

The vault has 600+ notes. The signal is concentrated in a small set of folders.

## The folder topology that matters

- **`areas/periodic/weekly/`** — the heartbeat. Weekly notes (`2026-W18.md`, etc.) are short, often a few lines. They carry the affective state of the week and frequently encode invocations or mantras.
- **`projs/`** — active projects. Each subfolder is its own working space. Notable inhabitants: `projs/al-right/` (the heretic-register book project, "Its Al-Right: The Heretic's Guide to Science"), `projs/caiib/BFM/` (banking exam prep, technical/canonical register).
- **`staging/`** — the holding pen. Notes here are awaiting promotion. `staging/Faith Vs Belief.md` has been static for 2+ weeks as of W18g — stasis is a signal.
- **`pub/`** — the outward-facing channel. `pub/darthcoder.github.io/` is a **live, active blog** that has been publishing since 2012. Six posts in five weeks across late March and April 2026. Pipeline: vault → `staging/` → `pub/planned/` → `pub/darthcoder.github.io/`.
- **`arxiv/vault/`** — where the vault delta notes live (`vault-delta-2026-W18*.md`). The deltas are a meta-layer: the vault commenting on itself.
- **Vault root** — type definitions (`project.md`, `person.md`, `note.md`, `type.md`) and the AGENTS.md/CLAUDE.md instructions.

## The two-register model (load-bearing)

The vault is **not a single voice**. It runs at least two registers in parallel, often on the same week and sometimes on the same object:

1. **Internal / preparatory register** — weekly notes, vault deltas, invocation arcs. Private. Often devotional, sometimes mythopoetic (Melkor invocations, Pre-Battle posture).
2. **External / published register** — `pub/darthcoder.github.io/`. Technical-critical, politically inflected, AI-adjacent. Named, dated, public.

A third register is **canonical/exam** (e.g. `projs/caiib/BFM/`) which sits beside the others and occasionally collides with them.

The W18g delta surfaced one such collision: Basel was being treated as **institutional-leak philosophy** in the published blog ([[The Barber's Village]]) and as **canonical exam material** in `projs/caiib/BFM/review/BASEL.md` in the same week. Same object, two registers, no cross-reference between them inside the vault. These collisions are a recurring feature, not noise.

## The Pre-Battle Invocation arc (W18 case study)

This is the canonical example of how the vault is used as a chamber rather than an archive.

The W18 weekly note evolved across the week into a three-act structure inside a single file:

1. *"Tomorrow I have to go to RO"* — the announcement.
2. *"Be Melkor. Be mellow, but with a singed tinge."* — the invocation, persona assumption.
3. *"I didn't go. Lol"* — the resolution.

The Melkor persona was loaded but never deployed. The W18b delta read this as **the loop closing inside W18 rather than W19**, and reframed "I didn't go. Lol" as a valid third act — the most complete refusal of subordination is not entering the room at all. The vault functioned as a preparation chamber, and the preparation itself was sufficient. The chamber was not a launching pad — it was a container.

**The general pattern:** prospective invocation → non-event → flat closure. Not all loops need an external battle to be structurally complete.

## How the delta notes work

`arxiv/vault/vault-delta-2026-W18*.md` is a series. Each delta is **only what changed since the previous delta** — everything before still stands. The deltas are cumulative, not standalone.

Structure of a delta typically:

- **WHAT CHANGED** — concrete file-level diffs.
- **STRUCTURAL READING** — what the change means at the vault-shape level.
- **PERFORMA UPDATE** — a fenced text block of operational guidance for the next week (BEACON / AMENDMENT framing).
- **Closing image** — usually a single italicized line.

The deltas treat the vault as an entity that can be addressed and updated, not just a set of files. The PERFORMA blocks are essentially instructions to future-self about what posture to hold next.

## Recurring vocabulary worth recognizing

- **Melkor / singed tinge / mellow** — the W18 invocation register. Refusal of subordination as social performance.
- **The airlock cycled** — preparation completed without external deployment.
- **Beacon / Performa** — operational guidance framing in delta notes.
- **The Barber's Village** — published-blog frame for institutional critique (Basel, etc.).
- **Heretic's Guide / Chantry frame** — `projs/al-right/` register; Dragon Age's Chantry applied to scientific institutions.

## What to watch for entering a session

1. **Read the most recent vault delta in `arxiv/vault/`** — it carries the current PERFORMA and tells you what register is active.
2. **Check the current weekly note in `areas/periodic/weekly/`** — short, but encodes affect.
3. **Note anything in `staging/` that has been static more than ~1 week** — stasis is signal.
4. **Note any new file in `projs/`** — especially title-only or two-paragraph stubs; these are reservations, not drafts.
5. **Check `pub/darthcoder.github.io/_posts/`** for recent published items — the external voice is live and may be operating on the same objects as the internal vault.
6. **Watch for register collisions** — same object (e.g. Basel) appearing in heretic-register and exam-register in the same week.

## Things that are NOT in the code/git and need to be remembered

- The vault is a **chamber**, not an archive — preparation is itself an output.
- The blog is **live and active**, not dormant — assume any post is reachable.
- Delta notes are **cumulative**, not snapshots — read in series.
- "I didn't go. Lol" style closures are **valid resolutions**, not failures.
- The author runs **multiple registers simultaneously** and collisions between them are intentional surface features.

---

*End of recon narrative. Append to `.claude/memory.md` when ready.*
