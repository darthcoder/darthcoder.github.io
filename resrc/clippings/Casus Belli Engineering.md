---
title: "Casus Belli Engineering"
source: "https://marcosmagueta.com/blog/casus-belli-engineering/"
author:
published:
created: 2026-04-18
description:
tags:
  - "clippings"
---
Few things in a professional environment are more important than a lasting impression; be it for building trust or conveying unappreciated quality, it is often what kills any system: people lose confidence in it. Imagine seeing something always faulty; a stakeholder sees a failed commitment. They do not see, and cannot see, the distinction between the feature that failed and the foundation it rests upon. To them, the system is monolithic; if any part fails, the whole is suspect. This perception, though technically naive, creates social stress that technical accuracy cannot dispel.

As failures accumulate, pressure builds; someone must be responsible, and something must be done. The organization demands resolution, not in the form of root cause analysis or targeted fixes, but in the form of visible action, decisive change and ritual purification. The tension must be released.

What follows is as old as human society itself: the stressed group selects a victim, to which the guilt is assigned, and finally, the victim is destroyed. Through its destruction, social cohesion is restored. The Aztecs sacrificed captives atop pyramids to ensure the sun would rise. We sacrifice codebases in conference rooms to ensure projects will ship. The mechanism is identical; only the altar has changed.

![A Jewish High Priest offering sacrifice from Henry Davenport Northrop's "Treasures of the Bible," 1894](https://mmagueta.capivaras.dev/images/8949c761.jpeg)

René Girard observed that human communities in crisis often resolve internal conflict through scapegoating: the selection of a victim to bear collective guilt, whose expulsion restores order. The scapegoat need not be guilty; it need only be acceptable as a target. Its guilt is constructed through narrative, not discovered through investigation (see \[5\], \[6\]).

Some dangerous individuals, however, institutionalize such ritualistic practices into what I call Casus Belli Engineering: the use of perceived failure as pretext to replace working systems with one's preferred worldview. The broken feature is the crisis that demands resolution. The foundation becomes the scapegoat, selected not for its vulnerability and the convenience of its replacement. And in most cases, this unfolds organically, driven by genuine belief in the narrative. These individuals are truly alchemists at heart; they have the power to manipulate the phantoms of lasting impressions to their favor \[14\]. They do not wait for crisis, they nourish it. They do not stumble into scapegoating, they engineer it. They fabricate casus belli deliberately, using the ancient machinery of collective violence to remake systems in their own image. These are not confused engineers making honest mistakes in attribution. These are political operators who have discovered that technical failure can be converted into organizational power.

The danger here is not the scapegoating itself; humans will scapegoat at all times. The danger is those who have learned to trigger the mechanism strategically, who can reliably convert any failure into an opportunity to destroy what exists and build what they prefer. They are the high priests of a secular religion, and their rituals shape our technological landscape more than any technical merit.

### The Scapegoat Mechanism

In software organizations the pattern obeys the same liturgy. What follows is my perception of its unfolding.

When failures generate tension, demand explanation, and threaten careers, the organization selects a scapegoat rather than confront the actual causes, which might implicate recent decisions, current leadership, or systemic dysfunction. It must be plausibly proximate to the failure (a dependency, a framework, an architectural pattern), unable to defend itself (because it is old, unfashionable, or championed by people who have departed), and replaceable with something the accusers prefer. This last criterion is the essential one: the scapegoat's destruction must clear the ground for the accuser's alternative.

Once selected, the scapegoat is ritually condemned. Its guilt is established through repetition ("We keep having problems because of X") while the actual causes (error handling, testing, operational neglect) recede into the background. X becomes the problem, and X must be destroyed. The war's stated objective has nothing to do with its actual aim: replacing one paradigm with another, under the cover of failure.

### The Pattern

The progression is predictable. A feature breaks repeatedly, whether from poor integration with external systems, inadequate error handling, or environmental fragility, and it happens to depend on some foundational component that functions correctly and has always functioned correctly. The failures are not caused by the foundation, but the foundation exists in the dependency chain, and that adjacency is sufficient for indictment.

Someone decides the foundational component is "the problem." Not the actual source of breakage, but the architecture, the paradigm, the way things are done. The real failures become ammunition: "We keep having issues with X" mutates into "X is built on Y, and Y is the problem," while the actual causes (external dependencies, testing deficits, error handling gaps) are eclipsed by a narrative that indicts the foundation wholesale.

A replacement is proposed, and it aligns with suspicious precision to the proposer's preferred technologies, methodologies, or architectural convictions. Both the broken feature and its working foundation are then scrapped together; the broken feature retroactively "proves" the foundation was wrong all along, and the fact that the foundation functioned correctly is dismissed as irrelevant, as "the wrong approach."

### The Psychology of the Hunt

Girard identified three preconditions for scapegoating: crisis, undifferentiated rivalry, and collective mimesis. Software organizations furnish all three (see \[5\], \[6\]). The crisis is the broken feature, the production incident, the customer escalation; something that has failed visibly and demands accountability. The undifferentiated rivalry is the familiar condition of multiple engineers or teams of comparable status competing for influence, where no settled authority governs technical direction and many opinions coexist without decisive power. And the collective mimesis is the propagation of framing: once someone declares the foundation "the problem," others imitate the judgment, doubt hardens into consensus, and what began as one person's opinion calcifies into organizational truth.

Into this environment steps a personality profile that Hogan, Kaiser, and colleagues have documented extensively in the dark-side leadership literature (see \[7\], \[8\], \[9\], \[10\]). These individuals substitute narrative coherence for causal analysis; they do not trace failure to its mechanism but accept the most rhetorically satisfying explanation, treating correlation as causation not because the distinction is unknown to them but because the rigor it demands is neither possessed nor valued. They are simultaneously highly engaged, deeply invested in outcomes, vocal, and tenacious, lending the narrative a force that ensures it will be pressed until it becomes orthodoxy. And they are technically insecure in a way that demands external validation: they cannot propose their preferred solution on its merits alone but must first delegitimize the existing approach, converting advocacy into prosecution.

This profile is ideally suited to initiating the scapegoat mechanism, combining the motivation to identify a target, the rhetorical facility to construct a narrative, and the psychological compulsion to see the sacrifice through to completion. The insecurity is what transforms mere advocacy into destruction: the scapegoat must die so that the accuser's worldview can be consecrated as the remedy.

### The Case of Agile: Industrial-Scale Scapegoating

To be precise, the problem is not iterative or incremental development itself. Those ideas are older than Agile, well-established, and technically sound; explicit advocacy for IID appears decades before Agile branding, in mainstream software engineering literature arguing that large-program design must proceed incrementally because requirements are never complete up front (see \[1\], \[2\]).

The problem is what happened at movement scale: Agile discourse became one of the most accomplished instances of Casus Belli Development in software history, Girardian scapegoating performed at industrial scale.

The crisis was real enough: software projects failing, over budget, over schedule, wrong requirements, poor quality. The scapegoat was "Waterfall," "Heavyweight processes," "Big upfront design," "Comprehensive documentation," a constellation of practices bundled together and assigned a collective name so they could be ritually condemned.

The brilliance was in the selection. "Waterfall" as a term was largely a straw man; few organizations practiced pure sequential development as described in the caricature. Even the 1970 Royce paper, routinely cited as the origin of waterfall, includes explicit iteration and feedback loops rather than strict one-pass sequencing (see \[3\]). But the label was plausible enough (projects did fail, documentation standards existed, phase gates existed) and that plausibility was sufficient. Context mattered less than rhetorical utility. Social pressure had already accumulated; what the narrative required was a guilty name and a cleansing alternative.

Ron Garret illustrates the same dynamic in a different domain. In his account of Lisp at JPL, the word itself had become unspeakable regardless of the technical merits it designated, a case where terms, not ideas, are the true casualties of the scapegoat mechanism:

> "It is incredibly frustrating watching all this happen. My job today (I am now working on software verification and validation) is to solve problems that can be traced directly back to the use of purely imperative languages with poorly defined semantics like C and C++. (The situation is a little better with Java, but not much.) But, of course, the obvious solution (to use non-imperative languages with well defined semantics like Lisp) is not an option. I can't even say the word Lisp without cementing my reputation as a crazy lunatic who thinks Lisp is the Answer to Everything. So I keep my mouth shut (mostly) and watch helplessly as millions of tax dollars get wasted. (I would pin some hope on a wave of grass-roots outrage over this blatant waste of money coming to the rescue, but, alas, on the scale of outrageous waste that happens routinely in government endeavors this is barely a blip.)"
> 
> Ron Garret, "Lisping at JPL," 2002

The Agile Manifesto provided the ritual language for this sacrifice. To be fair, the document includes an explicit caveat: there is value on both sides, but more on the left. Read literally, this is not an absolute rejection of process, documentation, contracts, or plans. The problem is how this language functioned socially.

In practice, the caveat is what evaporates. What persists are slogans built on asymmetry:

**"Individuals and interactions over processes and tools"** becomes a standing suspicion of process itself.

**"Working software over comprehensive documentation"** becomes a durable excuse to underinvest in documentation until knowledge collapses into oral tradition.

**"Customer collaboration over contract negotiation"** becomes a way to frame governance and contractual discipline as anti-customer bureaucracy.

**"Responding to change over following a plan"** becomes rhetorical permission to treat planning as naive, even when disciplined planning is precisely what makes adaptation coherent.

The issue is not that the manifesto text is verbatim absurd. The issue is that it is rhetorically engineered for movement politics: morally legible, easily memetic, and difficult to oppose without sounding regressive. Each pair supplies a reusable villain class ("processes," "documentation," "contracts," "plans") and a ready moral identity for the alternative. That is why it scales as narrative power even when the underlying engineering ideas were already known (see \[1\], \[2\], \[4\]).

The manifesto did not invent iterative thinking. It furnished a casus belli, permission to replace existing processes by framing those processes as the source of failure. The actual problems (poor requirements gathering, lack of customer access, inadequate testing, unrealistic schedules, management dysfunction) went unaddressed. "Waterfall" became the scapegoat, and its destruction became the solution.

Agile succeeded at movement scale not because it introduced unprecedented engineering ideas, but because it performed the scapegoat mechanism with extraordinary fidelity: a plausible enemy identified, its guilt constructed, salvation offered in the same gesture. That the "new" core was largely a rebranding of existing iterative practices was immaterial (see \[1\], \[2\], \[4\]). The ritual was completed, the scapegoat consumed, the narrative triumphant.

### Why It Works

Casus Belli Development exploits cognitive biases and organizational dynamics with particular efficacy. The recent failure is vivid and salient while the years of the foundation functioning correctly are abstract and unremembered; availability bias turns the incident into "proof" of systemic deficiency. Once someone concludes the foundation is flawed, confirmation bias ensures that every subsequent issue becomes corroboration; successes are dismissed as having occurred "despite" the foundation, and failures are treated as evidence of inherent defect. The status quo bias, ordinarily a conservative force, inverts the moment the status quo is framed as "failed": the incident demonstrates failure, therefore the foundation must go. In low-trust environments, authority compounds the effect: repeated assertion that the foundation is at fault supplants independent investigation, and consensus is mistaken for truth (see \[11\], \[12\]). And finally, replacement offers an escape from the sunk cost confrontation that repair would demand; one is not "fixing mistakes" but "adopting better practices," reframing retreat as progress.

### The Damage

The consequences are substantial and compounding. Proven foundations, systems that functioned reliably and embodied years of institutional refinement, are dismantled because they were adjacent to a failure, and the organization forfeits accumulated knowledge and battle-tested solutions in the process. The root causes persist: the actual sources of breakage (poor error handling, insufficient testing, environmental fragility) survive the transition intact and will resurface in the replacement, because they were never confronted.

Every few years a new incident furnishes a new casus belli, and the cycle iterates: foundations replaced, then replaced again, nothing stabilizing because stability is indistinguishable from stagnation to those who profit from upheaval. When replacements fail to resolve the problems they claimed to address, confidence deteriorates further, but rather than recognize the pattern, organizations indict the new foundation and begin searching for the next one. Meanwhile, engineers who understand causation, who can distinguish correlation from mechanism, grow frustrated and leave. What remains are those who excel at political maneuvering dressed as technical leadership.

### Recognition and Resistance

Casus Belli Development betrays itself through several signatures. The scope of the proposed solution exceeds the scope of the problem: a feature that fails due to external API timeouts does not necessitate rewriting the entire service layer in a different language, and when the remedy dwarfs the ailment, ulterior motives deserve scrutiny. The failure is used to indict a paradigm rather than a specific implementation ("This OOP code is hard to maintain" becomes "OOP is the problem," "This microservice is hard to debug" becomes "microservices were a mistake"), and this leap from the particular to the general is precisely where the casus belli operates. The proposed replacement aligns with suspicious precision to the proposer's preferences; if the person who has been advocating for GraphQL suddenly determines that a REST API failure proves REST fundamentally flawed, skepticism is warranted. The actual root causes are not analyzed with rigor: the investigation terminates at "X is built on Y, therefore Y is wrong" rather than continuing to "X fails because of Z, which is unrelated to Y." And the rhetoric emphasizes revolution over evolution, "We need to completely rethink how we do X" rather than "we need to fix this specific defect in X." Revolutionary rhetoric is diagnostic; it signals that the objective is replacement, not repair.

Resistance demands its own discipline. Insist on root cause analysis: not "the system is deficient" but "this specific invocation fails under this specific condition"; causation, not correlation. Separate the failure from the foundation and ask whether the failure can be remedied without replacing the foundation; if so, the replacement discussion is premature. Demand that proposals address the identified causes rather than merely relocate them to a different stratum. Evaluate proposed alternatives on intrinsic merit, not as saviors from a "failed" predecessor, for a new approach must stand on its own value, not derive legitimacy from the demolition of what came before. And attend to the psychological patterns at work: is this person seeking to validate their worldview rather than solve a problem? Motivation matters (see \[8\], \[9\], \[10\]).

### The Agile Postscript

What would honest advocacy for iterative development have looked like? It would have said: "We have found that iterative development with frequent customer feedback reduces requirement mismatches. Here are case studies. Here are measured outcomes. We propose adopting these practices." Instead, we received: "Traditional development is broken. It values processes over people. It produces documentation instead of working software. We propose a new paradigm."

The first is an engineering argument. The second is a casus belli. The first might have led to measured adoption of practices already known in substance. The second led to wholesale replacement of development methodologies with "Agile" frameworks that often preserved the worst attributes of what they claimed to supplant (rigid processes, now called "ceremonies"; comprehensive documentation, now called "backlogs"; detailed planning, now called "sprint planning").

Agile succeeded not because iterative development was deficient before its arrival, but because Agile branding furnished a casus belli for those who desired paradigm change and required politically acceptable justification. The manifesto supplied that justification, the failing projects supplied the evidence, "Waterfall" supplied the scapegoat, and once the narrative was established the replacement became inevitable. This is how Casus Belli Development operates at scale.

### A Final Observation

Girard noted that scapegoating requires collective blindness; the community must not recognize the mechanism while it operates. Once the scapegoat is perceived for what it is, an innocent bearer of projected guilt, the ritual loses its power. But so long as the community believes the scapegoat genuinely culpable, the mechanism functions perfectly (see \[6\]).

This is why Casus Belli Development endures. Its participants do not perceive themselves as performing a ritual. They believe they are solving problems, making sound technical decisions, improving the system. The narrative feels true because everyone around them concurs. The scapegoat's guilt feels self-evident because it has been asserted beyond counting.

The pattern persists because it succeeds at what it actually accomplishes: the discharge of organizational tension, the validation of preferred worldviews, the enablement of political change under technical cover. That it fails to resolve the underlying technical problems is immaterial to its efficacy as a social mechanism (see \[11\], \[12\], \[13\]).

But once you perceive it, the perception is irreversible. The next time an incident provokes calls to replace the foundation, you will recognize the anatomy: the crisis, the scapegoat, the spurious causation, the preferred alternative waiting in the wings, the ritual language of condemnation.

And you will face a choice: participate in the ritual, or refuse it.

Refusal is arduous. It demands insisting on causation when narrative is more compelling, defending systems that have been marked for destruction, accepting the role of the person who "doesn't get it," who "resists change," who "clings to the status quo."

But refusal is engineering. Casus Belli Development is not. It is politics costumed as engineering, ritual costumed as analysis, scapegoating costumed as problem-solving. Engineering is the commitment to understanding what actually causes what, to targeted remediation grounded in evidence, to the disciplined separation of correlation from causation, especially when the narrative is seductive.

We should choose engineering. Especially when everyone else has already chosen the narrative.

### References

1. Peter Van Roy and Seif Haridi, *Concepts, Techniques, and Models of Computer Programming* (MIT Press, 2004), ch. 6 "Program design in the large," sec. 6.7.1 "Design methodology" (explicit IID advocacy; notes successful use since at least the 1950s).
2. Craig Larman and Victor R. Basili, "Iterative and Incremental Development: A Brief History," *IEEE Computer* 36, no. 6 (2003): 47-56.
3. Winston W. Royce, "Managing the Development of Large Software Systems," in *Proceedings of IEEE WESCON* (1970).
4. Manifesto for Agile Software Development (2001), [https://agilemanifesto.org/](https://agilemanifesto.org/)
5. René Girard, *Violence and the Sacred* (Johns Hopkins University Press, 1977 \[orig. 1972\]).
6. René Girard, *The Scapegoat* (Johns Hopkins University Press, 1986 \[orig. 1982\]).
7. Robert Hogan, Gordon J. Curphy, and Joyce Hogan, "What We Know About Leadership: Effectiveness and Personality," *American Psychologist* 49, no. 6 (1994): 493-504.
8. Robert Hogan and Joyce Hogan, "Assessing Leadership: A View from the Dark Side," *International Journal of Selection and Assessment* 9, no. 1-2 (2001): 40-51.
9. Robert Hogan and Robert B. Kaiser, "What We Know About Leadership," *Review of General Psychology* 9, no. 2 (2005): 169-180.
10. Robert B. Kaiser, Jarrett M. LeBreton, and Joyce Hogan, "The Dark Side of Personality and Extreme Leader Behavior," *Applied Psychology* 64, no. 1 (2015): 55-92.
11. Irving L. Janis, *Victims of Groupthink* (Houghton Mifflin, 1972).
12. Amy C. Edmondson, "Psychological Safety and Learning Behavior in Work Teams," *Administrative Science Quarterly* 44, no. 2 (1999): 350-383.
13. Sidney Dekker, *The Field Guide to Understanding Human Error*, 3rd ed. (Ashgate, 2014).
14. Ioan P. Couliano, *Eros and Magic in the Renaissance* (University of Chicago Press, 1987 \[orig. 1984\])