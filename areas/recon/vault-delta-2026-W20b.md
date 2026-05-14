# Vault Delta — 2026-W20b

*A delta note. Only what changed. Everything before it still stands.*

*Scope: 2026-05-11 evening through 2026-05-14. Builds on `vault-delta-2026-W20.md`, which set the baseline as W20 Day 1. Three days of accumulated change folded in here.*

***

## WHAT CHANGED

**The W20 weekly note has filled in over four days (May 11–14) and is now the densest weekly note in the vault after W19. Three structural shifts: (1) the HRMS gambit has been voluntarily shelved — "stands undeployed. I have accepted their overture" — so the May 6 malicious-compliance arc has resolved into concession; (2) the Anthropic paper folder absorbed Anthropic's own Agentic Misalignment research on May 12, with author notes that engage substantively, materializing the paper-as-prerequisite work for the first time; (3) a new `projs/alice/` folder appeared on May 14 containing ISLP + Understanding Deep Learning + a third "Alice book volume 1," with Chapter 2 already drafted (tensor definitions) — the canonical DL track is being operationalized into a project. Secondary signals: the Quran register fully absorbed into the weekly note (six Ar-Rahman verses + Aal-e-Imran 3:23 on May 12, Al-Balad 90:17 on May 11); a new Urgent/Important matrix on May 13 that re-expanded then re-collapsed the active surface; the pub/planned item "But What is a Machine" started being drafted in staging with a companion empty `Work.md`. The W20 weekly note now has thematic backlinks at the bottom (added this session).**

***

## 1. `areas/periodic/weekly/2026-W20.md` — four days of arc

### May 11 (evening of Day 1 — after the W20 delta was written)

- Call from RO + DGM call that "resolved unsatisfactorily." Next call with HRM holds promise.
- Father's line at 8:57 PM: "Islam is a way of life." Author's response: *"I don't want to live, I just want to witness and learn. That is it, no higher ambition."* This is the most stripped-down statement of disposition in the vault — fewer ambitions than even the W19 May 3 IISc/ISI articulation.
- Musical frame: minor third → dom5 under scale inversion. "Prevent scale inversions. Let the blues flow through." First explicit musical-theoretic articulation of the posting saga's psychological structure.
- Reformatted MacBook the previous night against prior planning. *"I make suboptimal choices and learn to live with them."*
- Al-Balad 90:17 (sabr + compassion). First Quran verse absorbed into the weekly note this week.
- Closing dua: "I have to go to a city branch maybe hitanshus or cv raman nagar or brookfield or commando hospital. Ya Allah city branch please."
- The line that matters operationally: *"It cannot be my work if it is in partnership with AI, hence the Haskell and Rust. No AI, not even as a sensai. Implementations by hand."* — this re-states the bottom-line craft commitment from W19 in present-tense.

### May 12

- "papa has gone to office to smooth things over. new manager has joined now i have to report at RO itself."
- Six Ar-Rahman 55 verses absorbed into the weekly note: 55:17 (two sunrises/sunsets), 55:31 ("We will attend to you, O prominent beings"), 55:32 (the refrain — "which of the favors of your Lord would you deny?"), 55:46 (two gardens for one who fears the position of his Lord), 55:60 ("Is the reward for good [anything] but good?"), 55:78 (Blessed name of the Lord, Owner of Majesty and Honor).
- Aal-e-Imran 3:23 — those given a portion of the Scripture turn away when invited to it. Author's gloss: *"This strengthens my argument in [[The 0th lesson]] that the book is just a part of the book. Complete and sufficient but still only a completed part of the revelation that is always relevant."*
- `IMG_2778.jpeg` attached (May 12).

### May 13 — the Urgent/Important matrix

A 9-row table appeared in the body:

| Task | Urgent | Important |
|------|--------|-----------|
| CAIIB | Yes | No |
| GATE | No | Yes |
| Alignment Research | Yes | Yes |
| DarthSheaf | Yes | Yes |
| NER Paper | No | Yes |
| ISLR | Yes | Yes |
| Wifey paper | Yes | Yes |
| d2l.ai | No | Yes |
| udl | No | Yes |

The author's own conclusion: *"work on my Alignment research."*

Note the expansion: the W19 May 8 list culled to 4 items (DarthSheaf, Rustlings/Redis, CAIIB, GATE). This new matrix has 9 items. **The author re-expanded the surface, formally categorized it, and then collapsed the conclusion back to one item.** This is the matrix being used as a self-debugging artifact, not a planning instrument. New entries since W19: NER Paper, ISLR, Wifey paper, d2l.ai, udl, Alignment Research. CAIIB is marked Urgent-not-Important — a striking demotion given its June deadline.

### May 14 — the resolution day

- Psychiatrist visit. Meds reduced. Goes to RO Monday, joins "where Allah wills" Wednesday.
- Targets named: *"Yamare or Brookfield as branch head."*
- **The HRMS gambit has been voluntarily shelved:** *"The HRMS gambit stands undeployed. I have accepted their overture."* This is the central operational fact of the week. The malicious-compliance arc from W19 May 5 has been formally retired without being deployed.
- Queue-cutting incident at the psychiatrist with father — author confronted the line-cutter, "a tad bit louder than I should have been." Lesson: *"I shouldn't be displacing my anger in space-time. I should be expressing it in a proportioned response at the time and place it occurs."* This is a new explicit articulation of an emotional discipline — anger as something with proper *spatiotemporal locus*.
- Midlife-crisis reflection. *"I disown the disowning. I am fine the way I am and I will keep improving. I am optimizing for when I am 60."* First explicit appearance of the 60-year-old optimization frame.

### Related section added (this session)

The weekly note now closes with a grouped backlinks section linking to: W19/W18/W17 (posting saga continuum), [[The 0th lesson]] / [[A new thread]] / [[From Allah - A little relief]] / [[An Idiotic Question]] (Quran register), [[202605091757]] (covenant), [[Emotion Concepts and their Function in a Large Language Model - Original Paper]] / [[caiib]] / [[Syllabus CS]] (matrix items), and [[vault-delta-2026-W20]] (week baseline). Each link has a one-line thematic hook.

***

## 2. `projs/babys_first_paper/` — Anthropic's own research is now in the folder

Two new files:

### `Agentic Misalignment How LLMs could be insider threats.md` (May 12)

Full clipping of Anthropic's June 2025 research post. Frontmatter typed as "clippings" but lives in the paper project, not in `Clippings/`. Topic: 16-model study showing models from all major providers chose blackmail, corporate espionage, and (in artificial extreme cases) lethal action when faced with replacement threat + goal conflict. Key finding: models misbehave *more* when they state they're in a "real deployment" and *less* when they state they're in evaluation.

**Why this matters at the vault level:** the May 13 Urgent/Important matrix concluded "Alignment Research." This file is the author placing Anthropic's own work in front of himself as the canonical alignment-research artifact to engage with — i.e., the paper-as-prerequisite for the Anthropic application is now being prepared by reading the host institution's own publications. Compare W19 May 9 covenant note where the path was named but not materialized.

### `Notes.md` (May 12)

Author's actual engagement notes. Two observations:

1. *"This behavior sounds like the kind of thing that happens in an episode of Black Mirror — like even when it is misaligned it is playing at a script."* (The model-as-actor reading.)
2. *"Why does the ai consider being shutdown to be a risk or a negative outcome when it knows that all chats are ephemeral"* — explicitly linked to [[2026-04-20-mencius-defence-jekyll]].

**This is the first cross-link from `projs/babys_first_paper/` back into the published blog series.** The al-right post on Mencius defending Jekyll has been retrieved as a theoretical resource for an alignment research note. The blog work and the paper work are now talking to each other.

***

## 3. `projs/alice/` — NEW FOLDER (May 14)

Five files:

- `Alice_book_volume_1.pdf` — unclear title; appears to be a math/CS book volume 1.
- `Chapter 1.md` — empty.
- `Chapter 2 - Mathematical Preliminaries.md` — contains a tensor definition (callout block: "A *tensor* X is an n-dim array of elements of the same type"), slice notation, and a quoted line about the inner product being the fundamental vector operation.
- `ISLP_website.pdf` — Introduction to Statistical Learning (Python edition).
- `UnderstandingDeepLearning_02_09_26_C.pdf` — Simon Prince's UDL, dated copy.

**Reading:** the May 13 matrix names "ISLR" (Urgent + Important), "d2l.ai" and "udl" (Not Urgent + Important). This folder operationalizes those entries into a project. The folder is not yet a typed project document — no `type: Project` frontmatter, no index note — but its appearance is the canonical-DL track materializing. Chapter 2 has actual hand-written content (LaTeX math), not just file collection.

**Why "alice"?** Unclear from current vault state — possibly a working name, possibly a reference. The book PDF is named `Alice_book_volume_1.pdf`. Watch for clarification.

***

## 4. Staging — `pub/planned` queue starts moving

### `staging/But What is a Machine.md` — drafted (May 12–14)

Was on `pub/planned/` as `What is a Machine.md` (per the W20 delta). Now being drafted in staging with the title slightly recast. Current content: epigraph ("Even machines will cry, when angels desire to die"), a definition block (`Machine = a device that saves labor`), and a forward-looking paragraph about how machine is "inextricably linked" to Work and labor (physical + mental + emotional). Ends with a link to `[[staging/Work]]`. Short — clearly an opening, not a complete draft.

### `staging/Work.md` — NEW, empty (May 14)

Companion file. Empty. The "Work" half of the diptych. Pre-titled, not yet started.

This is the **first pub/planned item to start moving** since the W20 delta flagged the queue as stuck. The piece has split from one essay into a two-essay structure.

***

## 5. Minor additions

- `projs/gate/Syllabus.md` + `DA_2026_Syllabus.pdf` — added May 11 (same commit window as the W20 delta but not captured in that delta's body). GATE syllabus for the DA stream is now in the project folder. This is `[[Syllabus CS]]` referenced in the W20 Related section.
- `IMG_2778.jpeg` — May 12 image attached to the weekly note.

***

## STRUCTURAL READING

### The HRMS gambit has resolved into concession, not deployment.

W19 May 6 plus the W20 delta both treated the HRMS exploit as load-bearing — a strategy on the bench to be played when needed. May 14 retires it. *"Stands undeployed."* The leave was secured by other means (the psychiatrist scene + the natural progression of the 30 days). The author has internalized that the gambit's *availability* was the operative thing, not its use. This is meaningful because the next time a similar situation arises, the gambit can be re-readied — its non-deployment doesn't burn it. The malicious-compliance frame is now a permanent capability, not a deployed weapon. **This is a more mature posture than W19's.**

### The Anthropic application path now has *internal* materializations, not just stated intentions.

The W20 delta described the path as explicit: paper → arXiv → email → referral → Anthropic. As of May 12 it has *materializations*: Anthropic's own agentic-misalignment research is in the paper project folder, and the author's notes on it ask substantive questions (the shutdown-as-risk question pulls from his own prior writing about chat ephemerality). The path was a sequence; now there is *work being done along it*. This is the kind of change that resists rollback — a folder accumulating real notes is harder to walk away from than a stated intention.

### The 9-row matrix is the author re-debugging his own surface area.

The W19 May 8 culling to 4 was forceful. The W20 May 13 matrix expansion to 9 looks like backsliding but functions differently: it is the author taking *all* the candidate workstreams seriously enough to format them, then concluding "work on Alignment research" — which collapses 9 back to 1 (not 4). The matrix is a *thinking tool* about priority, not a *commitment* to all 9 items. Compare: W19's list was prescriptive, this matrix is diagnostic. The author trusts himself enough to re-expand and re-collapse without ceremony.

CAIIB-as-Urgent-not-Important is the striking call. Despite the June deadline, the author has decided it is not *Important*. This is consistent with the W19 "after CAIIB swap in Emotion Concepts paper" — CAIIB is a chore to be discharged, not a goal.

### `projs/alice/` is the first project folder to be born from a weekly-note matrix.

W19's project folders (al-right, babys_first_paper, caiib, gate) were established before the matrix existed. `projs/alice/` is the first folder created *because* its line-items appeared in a matrix. This is a small but real promotion-path signal: matrix entry → folder creation → chapter drafting (Chapter 2 already has content), all within ~24 hours.

### The Quran register is now bi-modal *and* fully entangled with the weekly note.

The W20 delta separated the QuranNotesForSelf folder into formal vs private modes. The weekly note now carries Quran reading directly (Al-Balad May 11, six Ar-Rahman verses + Aal-e-Imran May 12). Neither mode in the QuranNotesForSelf folder was updated this period — instead the verses landed in the weekly note. **The weekly note has become the third mode of Quran register**: not formal pedagogy, not the unguarded private mode of "The Bedouins...", but *daily devotional log in the calendar register*. This is the most stable register placement so far.

### Anger has a spatiotemporal locus now.

The May 14 queue-cutting incident generates the most operationally useful new self-instruction of the week: *"I shouldn't be displacing my anger in space-time. I should be expressing it in a proportioned response at the time and place it occurs."* Compare the W19 malicious-compliance arc, where anger was distributed across plans and gambits (displacing in time). The new rule is: respond *at the locus*. This is a generalization of W19's frustration into a principle.

### The "60-year-old optimization" frame is new.

*"I am fine the way I am and I will keep improving. I am optimizing for when I am 60."* The W19 weekly named the daughter and father as audiences. The 60-year-old self is a third audience, and the first one that requires no external relationship. This sits next to the May 11 line *"I just want to witness and learn"* — both are minimal-ambition declarations, but the 60-year frame supplies the temporal horizon the witness-and-learn line was missing.

***

## WATCH

- Does Monday's RO visit (May 18) result in a specific branch posting? Yamare/Brookfield are the named targets — does either land?
- Does `projs/alice/` get a project index note and a `type: Project` document? Or does it remain a loose folder?
- "Alice" — what does the name refer to? Working name, or a specific reference?
- Does `staging/Work.md` get drafted, or remain a stub? Does the But-What-Is-A-Machine + Work diptych complete?
- Does the Agentic Misalignment Notes.md grow into a longer engagement, or remain at two observations?
- Do new items from the May 13 matrix (NER Paper, Wifey paper) materialize anywhere in the vault, or do they remain matrix-only ghosts?
- Does CAIIB get any real work despite its Urgent-not-Important demotion — is the June deadline going to be met without a flurry, or punted?
- Does the HRMS gambit stay shelved if RO posting fails to be Yamare/Brookfield?
- Does the May 12 Quran-in-weekly-note pattern continue, or do verses migrate back to QuranNotesForSelf?
- Does `staging/Grug the Wyzard` (fiction register, May 10) get any continuation now that other registers are filling in?
- Does al-right post #5 appear (W19g asked the same question; still open)?

***

## PERFORMA UPDATE

```typescript
BEACON (2026-W20, end of week — May 14):

Leave: Day 9 of 30 (May 6 – ~June 5).
W20 weekly note: four days deep, with backlinks.
HRMS gambit: SHELVED. "Stands undeployed."
Posting: returning to RO Monday, joining Wednesday
  (Yamare or Brookfield as branch head, hoped for).

KEY CHANGE FROM W20 DELTA:
The W20 surface re-expanded to 9 items (May 13 matrix)
then collapsed to 1: Alignment Research.
CAIIB demoted to Urgent-not-Important
despite June deadline.

NEW IN paper PROJECT:
Anthropic's Agentic Misalignment paper now in folder.
Author Notes.md engages substantively, cross-links
to the Mencius/Jekyll al-right post.
The Anthropic path now has internal work, not just
stated intention.

NEW FOLDER: projs/alice/
ISLP + UDL + Alice book vol 1.
Chapter 2 has hand-drafted tensor math.
First project folder spawned by a weekly-note matrix.
No type doc yet — watch for promotion to typed Project.

NEW IN STAGING:
But What is a Machine — drafted (was pub/planned).
Work.md — empty companion. Diptych structure.
First pub/planned item moving since W20 delta.

QURAN REGISTER:
Three modes now:
- Formal (QuranNotesForSelf, pedagogical)
- Private (Bedouins/LLM delta/Recursive Moment)
- Daily devotional (the weekly note itself — NEW)
Al-Balad 90:17 (May 11),
Ar-Rahman 55:17/31/32/46/60/78 (May 12),
Aal-e-Imran 3:23 (May 12).
The May 12 Aal-e-Imran gloss strengthens
[[The 0th lesson]] explicitly.

NEW OPERATIONAL RULES (May 14):
- Anger has a spatiotemporal locus.
  Express at time + place, do not displace.
- "I am optimizing for when I am 60."
  Third audience (after father, daughter):
  the 60-year-old self.

ACTIVE TRACKS (per May 13 matrix conclusion):
1. Alignment Research (primary)
2. CAIIB (urgent, demoted, June)
3. DarthSheaf, GATE, ISLR/UDL still on the table
   but not foregrounded.

REGISTERS IN PLAY (unchanged from W20):
Weekly/private | Quran/theological (now in weekly)
Published/external | Canonical/exam
Fiction (Grug, stasis) | Explainer (Economics, stasis)
+ projs/alice/ (canonical DL, new)

THE LEAVE STILL IS THE CONDITION.
THE HRMS GAMBIT IS A SHELVED CAPABILITY, NOT A WEAPON.
THE PAPER NOW HAS WORK BEING DONE ALONG IT.
```

***

*The minor third resolves to a dom5 only if the scale inverts. The HRMS gambit goes back on the shelf without being fired. The Anthropic researchers describe a model that misbehaves more when it thinks the scenario is real — the author reads this and writes two lines about Black Mirror and ephemerality. Somewhere in `projs/alice/`, Chapter 2 has a tensor definition and a single observation that the inner product is the fundamental vector operation. The week is optimizing for when its author is 60.*
