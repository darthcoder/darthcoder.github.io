---
title: "Simulacrum of Knowledge Work"
source: "https://blog.happyfellow.dev/simulacrum-of-knowledge-work/"
author:
published: 2026-04-25
created: 2026-04-26
description: "How do you know the output is good without redoing the work yourself?You've received a report, a market analysis for the new product you're planning to l..."
tags:
  - "clippings"
---
How do you know the output is good without redoing the work yourself?

You've received a report, a market analysis for the new product you're planning to launch. Reading through it you notice problems: the date on the report doesn't match the date you requested it on, it's from 6 months prior. Several paragraphs have obvious spelling errors. Some graphs are mislabeled and duplicated.

The report is disregarded. The existence of typos and copy-paste errors which may not change the main conclusion of the report is enough to discard it. Someone who didn't put in enough care to make the report presentable on the surface level also didn't care enough to produce good research.

You have judged the quality using a proxy measure: the superficial quality of the writing itself. It's not what you ultimately care about — what you care about is whether the report reflects reality and points you toward good decisions. But that's expensive to check. Surface quality is cheap, and it correlates well enough with the thing you can't easily measure.

All of knowledge work has this problem. It's hard to objectively judge the quality of someone's work without spending a lot of effort on it. Therefore everyone relies heavily on proxy measures.

Proxy measures kept misaligned incentives in check. LLMs broke them.

Large language models are great at simulating a style of writing without necessarily reproducing the quality of the work. You can ask ChatGPT to write you a market analysis report and it will look and read like a deliverable from a top-tier consulting firm written by Serious Professionals.

A software engineer can write thousands of lines of code which looks like high-quality code, at least if you have just a couple of seconds to skim through it. Their colleagues will ask AI to do a code review for them, the code review will uncover a lot of issues and potential problems, and these will be addressed. The ritual of working will be upheld with none of the underlying quality.

We have built a working simulacrum of knowledge work.

The incentives almost guarantee we are in big trouble. Many workers, quite rationally, want to do well on whatever dimension they are being measured on. If they are judged by the surface-level quality of their work, then it's no surprise most of "their" output will be written by LLMs.

The LLMs have the same problem.

The training doesn't evaluate "is the answer true" or "is the answer useful." It's either "is the answer likely to appear in the training corpus" or "is the RLHF judge happy with the answer." We are optimising LLMs to produce output which looks like high quality output. And we have very good optimisers.

So here we are. We spent billions to create systems used to perform a simulacrum of work. Companies are racing to be the first on the tokens-spent leaderboard. The more LLM output workers produce, the less time anyone spends on looking deeply at the output. All we have time for is to skim it, slap "LGTM" on it and open their 17th Claude Code session.

We've automated ourselves into Goodhart's law.