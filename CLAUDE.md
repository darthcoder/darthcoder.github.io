# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

A Jekyll-based personal blog hosted on GitHub Pages (`darthcoder.github.io`). The site uses the `github-pages` gem, kramdown for Markdown rendering, and Rouge for syntax highlighting.

## Commands

```bash
# Install dependencies
bundle install

# Serve locally with live reload
bundle exec jekyll serve

# Build static site
bundle exec jekyll build
```

## Site structure

- `_posts/` — Blog posts in Markdown, named `YYYY-MM-DD-title.md`
- `_layouts/` — Three layouts: `default.html` (base), `post.html` (single post), `page.html` (static page)
- `_includes/` — Partials: `head.html`, `sidebar.html`, `lib/`
- `public/` — Static assets (CSS, fonts, etc.)
- `_config.yml` — Site metadata (title, author, URL, pagination)
- `index.html` — Home page using `paginator` (10 posts per page)

## Post format

Posts require Jekyll front matter. Minimal example:

```markdown
---
layout: post
title: "Post Title"
date: YYYY-MM-DD
---

Content here.
```

Jekyll requires the filename to match the date in front matter. The permalink is set to `pretty` style (`/year/month/day/title/`).

## Notes

- The `baseurl` in `_config.yml` is `/` — keep this when testing locally.
- Post filenames must use hyphens and be lowercase to work with Jekyll's `pretty` permalink style. Underscores or non-lowercase characters in filenames can break routing (see commit `ff8777d`).
