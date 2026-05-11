# Vault Delta — 2026-W19d

*A delta note. Only what changed. Everything before it still stands.*

*Scope: vault-wide — structural and content changes since the W19c delta (May 7).*

***

## WHAT CHANGED

**The 30-day sprint started moving. The arXiv paper has been ingested into the vault as plain text. A second Anthropic interpretability paper (published the same day, May 7) was clipped. An adjacent compression paper from outside Anthropic was clipped. Two more Quran notes. And — the most structurally significant change —** `al-right` **has gone from a folder to a published blog post.**

### 1. `projs/babys_first_paper/` — the paper is now in the vault

In W19c, the project folder contained one note: a single line linking to `transformer-circuits.pub/2026/emotions/index.html`. The unknown was *whether content follows*.

Content has followed.

The folder now contains `Emotion Concepts and their Function in a Large Language Model - Original Paper.md`. The note is the **full text of the Anthropic emotions paper**, ingested into the vault — abstract, three parts, all sections — with frontmatter showing `created: 2026-05-07T16:36:18 (UTC +05:30)` and the original authors (Sofroniew, Lindsey).

The filename is the second signal. The suffix `- Original Paper` implies a second note will exist: a derivative — notes on the paper, an implementation, the improvement that becomes the arXiv submission. The vault is structurally preparing for a paired note.

The constraint 10 arc (paper → arXiv → email to jl) now has its source material in the vault. Not as a link to read elsewhere. As text the user can annotate inline.

### 2. `Clippings/Natural Language Autoencoders.md` — a second Anthropic paper

Anthropic published *Natural Language Autoencoders: Turning Claude's thoughts into text* on May 7. The user clipped it on May 8.

NLAs are an interpretability technique: train a copy of Claude to verbalize its own activations as natural-language explanations, scored by whether a second copy can reconstruct the activation from the explanation alone. The post discusses application to evaluation-awareness detection (Claude suspects it's being tested more often than it lets on), to auditing for hidden motivations (12–15% success vs <3% without NLAs), and to limitations (hallucination, cost).

This is the second piece of Anthropic interpretability research in the vault within 48 hours, alongside the emotions paper. The user is now reading interpretability work as a corpus, not as a single paper.

### 3. `Clippings/Polynomial autoencoder.md` — an adjacent ML compression paper

Ivan Pleshkov (Qdrant) published a post on May 5 about a closed-form autoencoder: PCA encoder plus a quadratic Ridge-OLS decoder. On BEIR/FiQA, it gives 4× compression of `mxbai-embed-large-v1` at -0.85 p.p. NDCG@10, +2.73 p.p. over PCA. No SGD, no neural networks. The construction is borrowed from dynamical-systems literature ("quadratic manifold").

This clip is **not** Anthropic. It is autoencoder mathematics from the embedding/retrieval side. The thematic adjacency is the word *autoencoder* — and the technical adjacency is meaningful: NLAs are autoencoders (verbalizer + reconstructor), and the polynomial autoencoder is also an encoder + decoder, but with the decoder living in a closed-form polynomial-lift Ridge regression rather than a neural network.

The user is reading both at once. Whether the connection is incidental or load-bearing is not yet visible.

### 4. `areas/QuranNotesForSelf/` — two more notes

The folder now has five notes (was three in W19c). Two new ones since.

#### `A new thread.md`

Al-'Ankabut 29:46, Aal-e-Imran 3:7, Aal-e-Imran 3:13. The note's central interpretive move:

> *Since i interpret things in a maximally liberal manner i interpret it as — the verses are the foundation of the Book and the Book, the preserved tablet and "reality" are one and the same. I will die upon this hill. This reinterprets Signs as phenomena rather than noumena or something you need maarfat or whatever to understand. Simple as.*

The thesis: the Quran's *muḥkamāt* (precise verses), the Preserved Tablet, and physical reality are not three layered objects but one. Signs are phenomena, not noumena. The Battle of Badr (3:13 — the disbelievers seeing the Muslims as twice their number by sight) is cited as evidence: *even sight is granted by the All Seer*. This is the same epistemology as the W19c parent note (the *sunan Allah* as fixed law) but stated as a methodological commitment rather than as personal accounting.

#### `From Allah - A little relief.md`

Adh-Dhariyat 51:12-14. Terser, more aphoristic register than the other notes:

> *The Day of Judgement doesn't end when the sun goes down. Every Day is the Day of Judgement and every night the Night of Power. Your move my mudiji. The board is yours. The board is yours.*\
> *Your moves end when your breath does. What will you do? Oh but you are blinded by your nafs and only see what is shown to you. You wouldn't know to turn the other cheek if truth bitch slapped you. I pity the foo'*\
> \
> *— MR T*

The Mr. T quote and the direct address to "mudiji" (Modi) sit in the same paragraph as 51:14 (*"Taste your torment. This is what you sought to hasten."*). The W19c parent note named Pehlu Khan and Gujrat 2002. This note continues that thread but in a more compressed, almost post-it register.

### 5. `areas/notes/202605071640.md` — short capture

A four-line note titled *Code review is an audit function*. A memo callout, an explicit aside (*"We are ignoring the Al-Right hypothesis here"*), and a link to a Forbes article on Microsoft Edge password security. The note is interesting mostly for what the aside reveals: **the Al-Right hypothesis is now a named thing the user can suspend or apply**. The al-right frame has moved from *project* to *operator*.

### 6. `pub/darthcoder.github.io/_posts/2026-05-06-the-tagged-region.md` — al-right has shipped

This is the most significant change in this delta.

A blog post dated May 6, categories `[al-right, philosophy]`, tags `[institutions, haskell, banking, wikipedia, russell, displacement]`. Title: *The Tagged Region*. The thesis:

> *In Haskell, the type system is pure... Then your program does, in fact, read files... The contradiction — a pure language must do impure things to be useful — is solved by tagging a region for the impurity.*\
> *In banking, the books are pure... The contradiction — a healthy bank must hold sick loans to be useful — is solved by tagging a region for the sickness. The rest of the balance sheet stays clean by looking the other way.*\
> *In Wikipedia, the categories are pure... The contradiction — every event is local; some events are universal — is solved by tagging the article as a biography...*\
> *This is the same trick three times. It is the trick of all institutions. You cannot make a system clean; you can only declare a region dirty and put the dirt there.*

The post explicitly names Russell's stratified universe and the Barber paradox, points to a forthcoming companion piece (*The Barber's Village*), and is signed *Co-Authored by Sonnet. Mistakes my own.*

This is the **al-right project producing publishable output**. W19c flagged the question — *active project or named idea?* — and noted that a second note would confirm it. There is no second note inside `projs/al-right/`. There is a published blog post in the public-facing repo, in the al-right category, with the chantry-frame thesis applied to Haskell, banking, and Wikipedia.

***The author's day job is at a bank where NPA management is a literal task.*** The user has been studying Haskell (DarthSheaf project) for months. The Wikipedia corpus is currently being downloaded (W19 constraint 8). The Tagged Region post is the first note in the vault that draws all three of these threads into a single argument.

### 7. `Clippings/The text mode lie why modern TUIs are a nightmare for accessibility.md` — touched

The clipping itself is dated `created: 2026-05-04` so it predates W19c. It was modified between W19c and now. The substantive content is a critique of Ink/Bubble Tea/tcell as hostile to screen readers, contrasted with nano/vim/menuconfig/Irssi. Author tagged as [[The Inclusive Lens]] — a wikilink in YAML.

W19 weekly's constraint 9 was *minimize screen use (Speechify, screen readers, AI agents)*. This clipping is in that orbit: it is technical context for a constraint already on the list.

***

## STRUCTURAL READING

### The 30-day sprint is producing vault-visible work, on day 2.

The leave began May 6. By May 8:

- The arXiv source paper is in the vault as plain text (read-and-annotate posture).
- A second related Anthropic paper has been clipped.
- An adjacent ML compression paper has been clipped.
- A blog post in the al-right register has been published.
- The Quran notes folder has grown from 3 to 5.

Constraint 10 (the gate) has a body of source material now. Constraint 6 (DarthSheaf) and constraint 7 (NanoGPT) have not produced new vault entries in this window. Constraint 5 (GATE prep) likewise has no new entries. The sprint has begun on the AI/research and writing tracks; the math/Haskell tracks are quiet so far.

### The "autoencoder" cluster is now a thing.

NLAs (Anthropic, May 7) are an autoencoder. The polynomial autoencoder (Pleshkov, May 5, clipped May 8) is an autoencoder. The babys_first_paper original is *not* about autoencoders, but adjacent: emotion vectors as linear directions, steering, causal influence on outputs. The user is reading three pieces of work that share interpretability + low-dimensional-structure-of-activations as a substrate. Whether this becomes a project folder or stays as a clippings cluster is open.

### `al-right` is now a publishing register, not just a project folder.

W19c noted that `projs/al-right/` had only `Name.md` and that a second note would confirm it as active. The confirmation came from outside `projs/al-right/`: a published blog post in `pub/darthcoder.github.io/_posts/`, in the al-right category, signed co-authored by Sonnet. The al-right work is moving directly to publication, not staging in the project folder. The note in `areas/notes/202605071640.md` ("ignoring the Al-Right hypothesis here") confirms the frame is now an operator the author can apply or suspend across other contexts.

This means the vault structure for al-right may be permanently asymmetric: `projs/al-right/Name.md` holds the thesis, `pub/darthcoder.github.io/_posts/` holds the output, and notes elsewhere reference the frame in passing. There is no obvious need for `projs/al-right/` to fill in.

### The Quran notes are settling into a register.

Two more notes in 24 hours after W19c. The pace from W19c's "unpredictable" reading is starting to look more like a regular practice. The May 6 parent note was fury. *A new thread* is methodological. *From Allah — A little relief* is aphoristic. The folder is becoming the place where Quranic engagement happens, in whatever register the day requires. Five notes in three days.

### Two papers in the same week, same source, same theme.

Anthropic published the emotions paper in late April / early May (the user's note says `published 2026-05-07` for the NLA post; the emotions paper is `2026/emotions`). The user is now ingesting Anthropic interpretability work *as it appears*. The October arXiv deadline (mentioned in earlier deltas) is a long way off, but the cadence here suggests the user is treating Anthropic's research output as a feed to keep current with.

***

## WATCH

- Does a second note appear in `projs/babys_first_paper/`? The filename `- Original Paper` strongly implies it. The annotated/working version, the implementation notes, or the arXiv draft would be the obvious followups.
- Does the polynomial autoencoder thread connect to the NLA / emotions thread, or stay as a parallel reading? If it surfaces inside `projs/babys_first_paper/`, that is meaningful.
- Does the *Barber's Village* companion post (referenced at the bottom of *The Tagged Region*) appear in `pub/`? It is currently a placeholder permalink (`2026-05-XX-the-barbers-village`).
- Does `projs/al-right/` ever fill in, or does the project effectively live in `pub/`?
- Does `areas/QuranNotesForSelf/` continue daily-ish? Five notes in three days is a pace. Whether it sustains past the early-leave acute period is the question.
- Do the math/Haskell/NanoGPT constraints produce any vault-visible work in the next few days? They are silent in this delta.
- Does the Anthropic email get drafted-then-sent? The arXiv paper is the gate. The vault now has the source material; it does not yet have improvements.
- Does the DGM follow up after the May 6 missed call? No vault record yet.

***

## PERFORMA UPDATE

```typescript
BEACON AMENDMENT (2026-W19d):

Day 2 of the 30-day leave is a research-and-writing day, not a math day.

The arXiv source paper is in the vault as plain text — annotation-ready.
A second Anthropic interpretability paper (NLAs, May 7) is clipped.
An adjacent compression paper (polynomial autoencoder, Qdrant) is clipped.
The user is reading three interpretability/structure-of-activations
pieces in parallel. Cluster, not yet a folder.

al-right has shipped. "The Tagged Region" — Haskell IO, banking NPA,
Wikipedia biographies as the same institutional trick — was published
on darthcoder.github.io on May 6, signed co-authored by Sonnet.
A companion piece "The Barber's Village" is referenced but not yet
written. The al-right project lives in pub/, not in projs/al-right/.

The Quran notes folder has grown from 3 to 5 in 24 hours.
Two new notes: "A new thread" (methodological — Signs as phenomena,
the Preserved Tablet and reality are one) and "From Allah — A little
relief" (aphoristic — every Day is the Day of Judgement).

A short note "Code review is an audit function" introduces a new
phrasing: "the Al-Right hypothesis." The al-right frame is now
an operator the author can apply or suspend across contexts,
not just a project name.

GROUND ADDITIONS (W19d):
- projs/babys_first_paper/Emotion Concepts...- Original Paper.md:
  full paper text (~350 KB). Filename suffix implies a second note.
- Clippings/Natural Language Autoencoders.md (Anthropic, May 7).
- Clippings/Polynomial autoencoder.md (Pleshkov/Qdrant, May 5).
- areas/QuranNotesForSelf/A new thread.md (3:7, 29:46, 3:13).
- areas/QuranNotesForSelf/From Allah - A little relief.md (51:12-14).
- areas/notes/202605071640.md (code review / audit; al-right aside).
- pub/darthcoder.github.io/_posts/2026-05-06-the-tagged-region.md.

OPEN UNKNOWNS (carried forward, updated):
- The "second note" in projs/babys_first_paper/: not yet present.
- The Barber's Village blog post: referenced, not yet written.
- The autoencoder cluster: clippings or project?
- Math / Haskell / NanoGPT constraints: silent in this delta.
- IISc application timeline: still no vault record.
- DGM post-call follow-up: still no vault record.
- The Anthropic email: still drafted, not sent.
```

***

*Two days into the leave. The map is filling in faster than the territory, but the map's labels are the right labels. Source material in. First publication out. The constraint architecture is holding.*
