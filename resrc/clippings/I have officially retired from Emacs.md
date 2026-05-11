---
title: "I have officially retired from Emacs"
source: "https://nullprogram.com/blog/2026/04/26/"
author:
published: 2026-04-26
created: 2026-04-29
description:
tags:
  - "clippings"
---
nullprogram.com/blog/2026/04/26/

This past Tuesday I typed `C-x C-c` in Emacs for the last time after 20 years of daily use. Though [nearly half that time](https://nullprogram.com/blog/2017/04/01/) was gradually retiring it, switching to modal editing, then to Vim. Emacs is a platform, and I’d grown accustomed to its applications, especially those I built myself. There was no particular hurry, so replacements came slowly. With my [newly-acquired superpowers](https://nullprogram.com/blog/2026/03/29/) I could knock out the last two pieces in a few days’ work, namely [`M-x calc`](https://nullprogram.com/blog/2009/06/23/) with **[stackcalc](https://github.com/skeeto/stackcalc)** and [Elfeed](https://nullprogram.com/blog/2013/09/04/) with **[Elfeed2](https://github.com/skeeto/Elfeed2)**. I’m especially excited about the latter because it already exceeds the original. Both are multi-platform, native C++ GUI applications using native UI components.

![](https://nullprogram.com/img/elfeed2.png)

These [actively-in-use](https://melpa.org/#/?q=skeeto) packages require new maintainers (apply on the project’s issues/discussion):

No wonder it took so long for me to move on! I’m not handing these off to just anyone, and you’ll need to establish your reputation. Having already made contributions is a good sign, even if never merged. I’m willing to transfer them off my namespace, though you’ll need to manage the Melpa hand-off (on which I’ll sign-off). If there are no takers, these projects will be archived but not deleted.

### Trying out wxWidgets

The Emacs Calculator is amazing and the best calculator I’ve ever used, which is why nothing I could find was going to replace it. My clone uses GMP and MPFR for multi-precision, so it’s far faster, as to be expected, but it’s not nearly at feature parity. It’s missing esoteric features including symbolic processing. Though it’s enough to cover all of my own usage. I can add more features later. The Emacs Calculator manual served as a specification when building stackcalc.

Elfeed has been a cornerstone of my daily routines for the past 13 years. Nothing else I’ve found scratches that itch for me, so I’ve always known it would require a rewrite someday. Knowing it would take a few weeks of work, and that I *already had the feed reader I wanted*, made motivation difficult to find. Though now that I can accomplish ~3 weeks of old-way work in a new-way day, this sort of project becomes that much easier to start and finish. Though it’s not yet at a 1.0 release, after a couple days Elfeed2 was working well enough to replace the original Elfeed.

While [Dear ImGui](https://github.com/ocornut/imgui) was the right choice for [dcmake](https://github.com/skeeto/dcmake), it would not be so for these two applications. Active rendering doesn’t suit a feed reader left running all day, and I needed a richer toolkit. Professionally I work in Qt, but I wanted something lighter-weight for my projects, accessible via CMake `FetchContent`. That naturally led to [wxWidgets](https://wxwidgets.org/). While it has issues — mitigatable character encoding problems, accidental quadratic time in many places — it’s worked better than I anticipated, letting me rapidly produce native-looking applications on Windows, macOS, and Linux.

Unlike Dear ImGui, wxWidgets is a platform, including [sane](https://nullprogram.com/blog/2021/12/30/) I/O and path handling. I *mostly* don’t need platform layers when building applications like these. I can simply rely on wxWidgets’ utilities.

Both of these projects build out-of-the-box on [w64devkit](https://github.com/skeeto/w64devkit) thanks to the dependencies being `FetchContent` -compatible. On all platforms you just need a C++ toolchain and CMake:

```
$ cmake -B build
$ cmake --build build
```

Now that I have experience with wxWidgets, learning its limitations and capabilities, it’s likely to be a foundation of most of my GUI projects to come, except where something like Dear ImGui is a better git.