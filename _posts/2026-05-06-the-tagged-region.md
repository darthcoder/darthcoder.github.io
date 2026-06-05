---
layout: post
title: "The Tagged Region"
date: 2026-05-06
categories: [al-right, philosophy]
tags: [institutions, haskell, banking, wikipedia, russell, displacement]
---

Three things you already know.

In Haskell, the type system is pure. Write `add :: Int -> Int -> Int` and the compiler can prove this function does nothing but compute. No file read, no screen written, no clock consulted. The promise is total. Then your program does, in fact, read files and write screens and consult clocks. It does this by the trick of declaring such acts to be `IO a` — a type that means *I am the impure region, please don't look here, but rest assured the rest of the language remains clean*. The contradiction — a pure language must do impure things to be useful — is solved by tagging a region for the impurity. The rest of the language stays pure by the simple expedient of looking the other way.

In banking, the books are pure. Every loan performs, every asset earns, every quarter beats the last. The promise is total. Then loans, in fact, go bad — in numbers that would melt the books if the books were honest. So we declare a region: the NPA. The Non-Performing Asset. We tag the bad loan, slide it across the line, eventually pass it to an ARC, and the books regain their purity. The contradiction — a healthy bank must hold sick loans to be useful — is solved by tagging a region for the sickness. The rest of the balance sheet stays clean by looking the other way.

In Wikipedia, the categories are pure. Every event has a clean name and a clean home. The Assassination of Archduke Franz Ferdinand goes here, the October Revolution goes there, no overlap. The promise is total. Then the Sazonov article exists — a single biographical page that touches both narratives, the only collision point in the whole corpus. The contradiction — every event is local; some events are universal — is solved by tagging the article as a biography, neither category proper, just a man who happened to stand near both fires. The rest of the encyclopedia stays clean by looking the other way.

This is the same trick three times. It is the trick of all institutions. You cannot make a system clean; you can only declare a region *dirty* and put the dirt there. Russell could not banish self-reference from set theory; he could only banish *certain* self-references to a stratified universe where they didn't matter. The barber could not be in his own village; the barber had to be in another village, which turned out to be the same village wearing a different hat.

The interesting thing — and here I want to be careful, because the trick itself is everywhere and not interesting — the interesting thing is that *the tagged region is always larger than advertised*. `IO` in Haskell is the most-used type by a wide margin; you spend most of your day there. The NPA pile is where most of the real work of banking happens — the recovery, the restructuring, the haircut negotiation, the actual economy of decisions. The biographies on Wikipedia are where the history sits, after the categories have been cleaned of it.

You declare a small ghetto for the contradictions. The contradictions move in. Then everyone else moves in too, because that is where the action is.

This is not a complaint. It is closer to a description of how things stay in motion.

---

*Companion piece: [The Barber's Village]({% post_url 2026-05-01-the-barbers-village %}) — same thesis, different vector. Where Tagged Region is about containment by label, Barber's Village is about displacement across boundaries. Both are moves in the same game.*

Co-Authored by Sonnet. Mistakes my own.
