# Jade’s Personal Website

Built with Astro. Sections: home, projects, thoughts, books, and about. Posts are Markdown-based.

## Project structure

- `src/pages` — route files for pages and posts
- `src/content` — Markdown sources for `thoughts`, `books`, and `projects`
- `src/layouts` and `src/components` — layout + nav
- `public` — static assets (favicon, etc.)

## Run locally

```sh
npm install
npm run dev
```

Visit `http://localhost:4321`.

## Build for deployment

```sh
npm run build
npm run preview   # optional sanity check of the production build
```

The built site lives in `dist/`.

## Adding a new post

1. Add a Markdown file to `src/content/thoughts/`, `src/content/books/`, or `src/content/projects/`.
2. Include frontmatter:

```md
---
title: Post title
description: Short summary for feeds and listing cards
date: 2024-01-05
tags:
  - optional
---

Your content here.
```

For book notes, add `author: Author Name` to the frontmatter.

For projects, add optional links:

```md
links:
  - label: Live site
    href: https://jadefeng.com
```

The slug comes from the filename, e.g. `src/content/thoughts/new-idea.md` becomes `/thoughts/new-idea/`. Posts
automatically appear in listings.
