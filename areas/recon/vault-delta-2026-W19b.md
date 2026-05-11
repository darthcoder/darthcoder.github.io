# Vault Delta — 2026-W19b

*A delta note. Only what changed. Everything before it still stands.*

*Scope: `projs/gate/` — structural expansion since the W19 delta.*

***

## WHAT CHANGED

**Two new subfolders. Twelve new notes. A structural reorganization of the gate project. Three theory-of-computation notes written in voice-note register rather than study register.**

### 1. Structural reorganization — `projs/gate/` now has two subfolders

The W19 delta recorded six notes at or near the gate project root:

- `Syllabus.md`
- `Syllabus CS.md`
- `Propositional and first order logic.md`
- `Sets.md`
- `Relations.md`
- `Counting.md`

Since then, the project has reorganized. The four working notes have migrated into `projs/gate/Math/`, and a new `projs/gate/theory of computation/` subfolder has appeared. The gate project now has a two-track architecture: discrete mathematics under `Math/`, theory of computation under `theory of computation/`.

This is a structural commitment. The project is no longer a flat folder of early notes — it has internal topology.

### 2. `projs/gate/Math/` — seven new stubs added to existing four working notes

The four original working notes (Propositional and first order logic, Sets, Relations, Counting) are now inside `Math/`. Seven additional notes have been created as stubs:

| Note | Status |
|---|---|
| `partial orders.md` | 1-line stub (see note below) |
| `lattices.md` | 1-line stub |
| `Monoids.md` | 1-line stub |
| `Groups.md` | 1-line stub |
| `Graphs - connectivity, matching, coloring.md` | 1-line stub |
| `recurrence relations.md` | 1-line stub |
| `generating functions.md` | 1-line stub |

All seven are empty placeholders — titles without content. This is the vault's standard stub pattern: claim the territory, fill it later.

**On `partial orders.md`:** The W19 delta tracked a `partial orders.md` stub at the vault root and flagged its placement outside `projs/gate/` as potentially significant. The note now lives at `projs/gate/Math/partial orders.md`. Whether it was moved here or the vault-root placement was incidental (created in the wrong folder, immediately corrected) is not determinable. Either way: the question of whether partial orders represents a mathematical interest wider than GATE prep has not resolved — it has merely been absorbed into the exam project.

**The algebra cluster is notable.** Monoids → Groups → lattices is a specific progression: semigroups with identity, groups, order-theoretic structures. These appear together in the GATE CS Discrete Mathematics syllabus under Algebraic Structures. The vault is tracking them as a unit. Combined with partial orders, the `Math/` folder is building toward the order theory and algebraic structures sections of the syllabus simultaneously.

### 3. `projs/gate/theory of computation/` — five notes, three registers

A new subfolder dedicated to Theory of Computation. Five notes:

| Note | Status |
|---|---|
| `Regular expressions and finite automata.md` | 1-line stub |
| `pumping lemma.md` | 1-line stub |
| `Regular and context-free languages.md` | Voice note (substantive) |
| `Context-free grammars and push-down automata.md` | Voice note (brief) |
| `Turing machines and undecidability.md` | Voice note (brief) |

**The two pure stubs** (Regular expressions and finite automata, pumping lemma) follow the same pattern as the Math stubs: placeholders.

**The three voice notes** are different in register from anything in the Math subfolder. They are not study notes. They are reactions.

---

**`Turing machines and undecidability.md`:**

> *Why cant machines resolve undecidability? Does that make me a machine. Just choose something Jesus.*

One line. The technical content of the note (undecidability, the halting problem) is being mapped immediately onto the author's personal situation. The institution hasn't resolved the posting. The author is waiting. The note does not explain the Halting Problem — it uses it as a mirror.

---

**`Context-free grammars and push-down automata.md`:**

> *The automata will no longer by pushed down. Get back, give us some breathe.*

One line. Wordplay — "push-down automata" as a metaphor for institutional pressure. "The automata will no longer by pushed down" is a statement of intent dressed as a grammar joke. Lighter in register than the Turing note.

---

**`Regular and context-free languages.md`:**

The longest of the three. Three paragraphs. The first is the most significant:

> *context-free grammars give rise to context-free languages but context gives rise to meaning. Well theres your big problem solved for you.*

Then:

> *I still have to give GATE. WTF, I'm Darthcoder on Github since 2008. I was chmod before some of these students were born. Doesn't feel fair. Maybe a Wittgenstenian approach is warranted? Baby steps.*

Then a third paragraph referencing a Grokk link (`transformer-circuits.pub/2026/emotions/index.html`), with a plan to improve the results on arXiv by October and send an email in draft — *"ceteris paribus with an equal measure of shock and awe. I will figure out the rest yesterday. Lol."*

Three things in one note:
1. A philosophical aside on context and meaning (direct engagement with the material)
2. A statement of identity friction — the author has been writing code since before most GATE candidates existed. Having to prove competency to a syllabus feels absurd. The Wittgensteinian note is: the game of GATE has rules; you can't refuse to play the game by pointing out its rules are arbitrary — you have to play and win, *then* comment on the rules.
3. A forward plan: arXiv paper, October deadline, an email to be sent afterward. This is not GATE prep. This is a separate track running alongside GATE prep — the research/publication track.

The third paragraph is the first appearance in the vault of an arXiv submission plan. It is buried inside a theory-of-computation stub. The placement is either incidental (written wherever the vault was open) or tells us something about the mental state when it was written: theory of computation as the register in which long-term academic ambition becomes legible.

***

## STRUCTURAL READING

### The gate project has moved from flat to structured in under two weeks.

W19 opened with six notes at the root. The project now has two subfolders, eleven working notes (four with content, seven stubs), and five theory-of-computation notes. The structural analogy to the CAIIB project (which has three paper folders) is not exact, but the direction is similar: an exam project that starts as a list and becomes a map.

### The Math stubs follow the syllabus; the ToC notes do not.

The `Math/` stubs (Monoids, Groups, lattices, partial orders, Graphs, recurrence relations, generating functions) are direct syllabus items. They are being created in advance of content — territory claims.

The `theory of computation/` notes are not syllabus items in the same sense. Three of the five are voice notes, reactions, identity statements. This may reflect the author's relationship to ToC as a domain: less unfamiliar (the Darthcoder-since-2008 comment establishes that this is not new territory) and therefore easier to react to than to study from scratch.

The Math notes are careful and structured (Sets.md, Relations.md, Counting.md are full formal notes with definitions and proofs). The ToC notes are personal. The vault is studying mathematics; it is *commenting on* theory of computation.

### The arXiv plan is new and untracked.

The transformer-circuits reference and October deadline in `Regular and context-free languages.md` do not appear anywhere else in the vault. There is no `projs/` folder for this work, no note tracking the paper, no wikilink. It is a note to self dropped into a theory-of-computation stub. Whether this represents an active plan or an aspirational note-while-distracted is not determinable. But it is the first explicit mention of an arXiv submission timeline in the vault's history.

The logic: study GATE → get into IISc → do research → publish → become a professor. The arXiv plan may be an acceleration of that arc, or it may be a parallel track that predates the IISc ambition. The vault does not say.

***

## WATCH

- Do the seven Math stubs receive content, and in what order? The algebra cluster (Monoids, Groups, lattices) may develop together; graphs and combinatorics (recurrence relations, generating functions) may follow the Counting note's pattern.
- Does `partial orders.md` receive content now that it is inside `projs/gate/Math/`? The placement resolves the structural question; the content question remains open.
- Do the three ToC voice notes get upgraded to study notes, or do they stay as reactions? The Turing and CFG notes are one-liners; the Regular/CFL note has more texture.
- Does the arXiv plan surface anywhere else? Is there a paper in progress, or was the October reference aspirational?
- Does `projs/gate/` grow a third subfolder (e.g. `algorithms/`, `databases/`, `operating systems/`) as the GATE CS syllabus widens?
- The gate project has moved fast: 6 notes in W19, now 18 notes and a two-subfolder structure within the same week. Does this pace hold?

***

## PERFORMA UPDATE

```text
BEACON AMENDMENT (2026-W19b):

projs/gate/ has internal topology now. Math/ and theory of computation/
are separate tracks. The Math notes are formal and careful; the ToC
notes are voice notes, reactions, identity friction.

One new unknown: an arXiv submission plan buried in
Regular and context-free languages.md. October deadline. No project
folder. Not tracked elsewhere. The vault is running a third thread
(research/publication) that is not yet a project.

The seven new Math stubs fill out the algebra and combinatorics
sections of the GATE CS syllabus. The project is building a map
before it builds the territory.

GROUND ADDITIONS (W19b):
- projs/gate/Math/: partial orders, lattices, Monoids, Groups, Graphs,
  recurrence relations, generating functions — all stubs.
  Algebra cluster (Monoids→Groups→lattices) is a unit.
- projs/gate/theory of computation/: 5 notes.
  2 pure stubs (Regular expressions, pumping lemma).
  3 voice notes — Turing (undecidability as mirror), CFG/PDA (wordplay),
  Regular/CFL (identity friction + arXiv plan).
- Structural: gate project is now two-track, not flat.

NEW UNKNOWN:
- arXiv plan: transformer-circuits.pub/2026/emotions/index.html,
  improve results, submit by October, then send an email.
  Not in any projs/ folder. First appearance.
```

***

*The map is expanding. The territory is mostly still stubs. The author is Darthcoder on GitHub since 2008 and was chmod before some of these students were born. Baby steps.*
