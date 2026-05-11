---
title: "Welcome to the world of Statecharts"
source: "https://statecharts.dev/"
author:
published:
created: 2026-04-26
description: "The world of statecharts describes what statecharts are, their benefits and drawbacks, how they differ from state machines, and practical examples on how to use them."
tags:
  - "clippings"
---
What is a statechart?

A statechart can be explained in many ways, and we’ll get to those explanations, but essentially, a statechart is a drawing. Here’s a simple statechart:

![A simple statechart](https://statecharts.dev/on-off.svg)

However, this drawing isn’t very useful for software engineers who want to reap the benefits outlined elsewhere on this site, so let’s dive into some other ways of describing what a statechart is. The original paper that defines statecharts bills them as “A visual formalism for complex systems” (Harel, 1987). With that out of the way, let’s try to explain statecharts.

### Introduction to statecharts

Put simply, a statechart is a beefed up [state machine](https://statecharts.dev/what-is-a-state-machine.html). The beefing up solves a lot of the problems that state machines have, especially [state explosion](https://statecharts.dev/state-machine-state-explosion.html) that happens as state machines grow. One of the goals of this site is to help explain what statecharts are and how they are useful.

- [What is a state machine?](https://statecharts.dev/what-is-a-state-machine.html)
- [What is a statechart?](https://statecharts.dev/what-is-a-statechart.html)

### Why should you use statecharts?

Statecharts offer a surprising array of benefits

- It’s [easier to understand a statechart](https://statecharts.dev/benefit-easy-to-understand.html) than many other forms of code.
- The [behaviour is decoupled](https://statecharts.dev/benefit-decoupled-behaviour-component.html) from the component in question.
	- This makes it [easier to make changes to the behaviour](https://statecharts.dev/benefit-make-changes-to-the-behaviour.html).
		- It also makes it [easier to reason about the code](https://statecharts.dev/benefit-reason-about-code.html).
		- And the behaviour can be [tested independently](https://statecharts.dev/benefit-testable-behaviour.html) of the component.
- The process of building a statechart causes [all the states to be explored](https://statecharts.dev/benefit-all-states-explored.html).
- Studies have shown that statechart based code has [lower bug counts](https://statecharts.dev/benefit-low-bug-count.html) than traditional code.
- Statecharts lends itself to dealing with [exceptional situations](https://statecharts.dev/benefit-handle-anomalies.html) that might otherwise be overlooked.
- As complexity grows, statecharts [scale well](https://statecharts.dev/benefit-scales-with-complexity.html).
- A statechart is a great communicator: Non-developers can [understand the statecharts](https://statecharts.dev/benefit-non-developers-understanding.html), while QA can [use a statecharts as an exploratory tool](https://statecharts.dev/benefit-qa-exploration-tool.html).

It’s worth noting that you’re [already coding state machines](https://statecharts.dev/benefit-explicit.html), except that they’re hidden in the code.

### Why should you not use statecharts?

There are a few downsides to using statecharts that you should be aware of.

- Programmers typically [need to learn something new](https://statecharts.dev/drawback-learn-new-technique.html), although the underpinnings (state machines) would be something that most programmers are familiar with.
- [It’s usually a very foreign way of coding](https://statecharts.dev/drawback-foreign-paradigm.html), so teams might experience pushback based on how very different it is.
- There is an overhead to extracting the behaviour in that the [number of lines of code might increase](https://statecharts.dev/drawback-lines-of-code.html) with smaller statecharts.

### Why are they not used?

- [People don’t know about them, and YAGNI](https://statecharts.dev/faq/why-statecharts-are-not-used.html).

### What are the main arguments against statecharts?

There are a few common arguments against statecharts in addition to the ones listed above:

- It’s [simply not needed](https://statecharts.dev/faq/an-event-always-has-one-action.html).
- It [goes against the grain](https://statecharts.dev/faq/goes-against-grain.html) of *\[insert name of technology\]*.
- It [increases the number of libraries](https://statecharts.dev/faq/increases-number-of-libraries.html), for web applications this means increased load time.

The benefits outlined above should make it clear that the introduction of statecharts is generally a *net positive*.

### How do you use statecharts?

First of all, know that a W3C committee spent 10+ years (2005 to 2015) standardizing something called *SCXML* (yes, Statechart XML), and that it defines a lot of the semantics and specifies how to deal with certain edge cases. There are tools to read, author and even execute statecharts written in SCXML, in various languages. There are also some derivatives that support the same *model* as SCXML, but using a different syntax.

Additionally, there are statechart libaries for a variety of platforms, that in varying degrees support the semantics described by SCXML. You should consider using these libraries just to get those edge cases taken care of. The libraries generally perform entry and exit actions *in the right order* and so on.

With that out of the way, [read on](https://statecharts.dev/how-to-use-statecharts.html)!

## Executable statecharts

In addition to just using statecharts to model the behaviour in documents separate from the actual running code, it’s possible to use one of various machine formats, both to design the behaviour, and at run-time to actually *be* the behaviour. The idea is to have a single source of truth that describes the behaviour of a component, and that this single source drives both the actual run-time code, but that it can also be used to generate a precise diagram that visualises the statechart.

This carries along some different pros and cons:

### Why should you use executable statecharts?

- No need to translate diagrams into code
- No bugs introduced by hand translation of diagrams
- The diagrams are always in sync
- The diagrams are more precise

### Why should you not use executable statecharts?

- The diagrams may become quite complex
- The format and tools for executable statecharts is limited
- Type safety between statechart and the component is hard to enforce

### How do you use executable statecharts?

In essence, if you have any definition of a statechart in your code, all you need to do is to take that representation and automate the generation of the visual statechart. This is of course simpler when the definition is in a separate file, e.g. in a JSON or XML file.

This is all explained on the page on [how to use statecharts](https://statecharts.dev/how-to-use-statecharts.html)!

## Reach out to the community

If you feel like chatting to someone about statecharts, you can go to [gitter.im](https://gitter.im/statecharts/statecharts) (no login required to see the chat), where you’ll find a community of like minded developers that can help you understand and reap the benefits of using Statecharts. For a more Q&A-type site, head on over to the [statecharts GitHub discussions](https://github.com/statecharts/statecharts/discussions), where we’ll do your best to answer your question.

Quite a few people have written books or held presentations that deal with statecharts in various ways, and they’re included in our [resources](https://statecharts.dev/resources.html) page. If you’ve written something, please share it by posting it to [GitHub Discussions](https://github.com/statecharts/statecharts/discussions).

There are some pages that haven’t found any place in the web of documents, so they’re honourably mentioned here:

- [Use case: Statecharts in User Interfaces](https://statecharts.dev/use-case-statecharts-in-user-interfaces.html)
- [Concepts](https://statecharts.dev/concepts.html) — The most important concepts in a statechart and what they look like in a diagram.
- [Glossary](https://statecharts.dev/glossary/) — A list of terms that get thrown around when talking about statecharts, with their definitions.
- [FizzBuzz](https://statecharts.dev/fizzbuzz.html) — FizzBuzz is a well known problem, and it’s been used as a backdrop to explain various statechart concepts.

[Acknowledgements](https://statecharts.dev/acknowledgements.html)