### Repo overview

- This is a content-driven personal website built with Astro. Primary source content lives under `src/content` and routes are in `src/pages`.
- Key UI primitives live in `src/components` and the main layout is `src/layouts/BaseLayout.astro`.

### How to run

- Install dependencies: `npm install`
- Local dev: `npm run dev` (site served at http://localhost:4321 per README)
- Build: `npm run build`
- Preview production build: `npm run preview`

These scripts are defined in `package.json`.

### Content model and conventions (important)

- Content collections are defined with Astro Content and Zod in `src/content/config.ts`. Do not change the Zod schemas without also updating all Markdown frontmatter that depends on them.
- Collections: `thoughts`, `books`, `projects`. Each expects these frontmatter fields:
  - `title` (string)
  - `description` (string)
  - `date` (parsed as a Date — use ISO date or `YYYY-MM-DD` in frontmatter)
  - `tags` (optional array of strings)
- `books` adds `author: string` in frontmatter.
- `projects` supports `overviewImage` (object with `src` and optional `alt`) and `links` (array of `{ label, href }`). See `src/content/config.ts` for exact shapes.

Example frontmatter (projects):

---
title: Example Project
description: Short summary
date: 2025-12-24
overviewImage:
  src: /images/projects/example/index.png
  alt: Screenshot
links:
  - label: Live site
    href: https://example.com
---

### File & asset locations to use

- Markdown content: `src/content/{thoughts,books,projects}`
- Route files: `src/pages` (Astro auto-routes by filename)
- Layouts: `src/layouts` (use `BaseLayout.astro` for new pages)
- Components: `src/components` (pass props via Astro.props; example: `Card.astro`)
- Static assets: `public/` (images referenced from frontmatter should live under `public/images/...`)

### Patterns and small gotchas

- Slugs derive from filenames; adding `src/content/thoughts/new-post.md` creates `/thoughts/new-post/`.
- Dates in frontmatter must parse to JS Date objects. Prefer `YYYY-MM-DD` or full ISO timestamps.
- When adding images referenced in frontmatter, place them under `public/images` and use absolute paths (`/images/...`).
- The site is largely static — avoid introducing server-only code unless you also add build/runtime configuration (this repo currently has no server framework beyond Astro).
- Keep schema changes coordinated with content changes: mismatched frontmatter → build-time errors from the content schema.

### Example edits an AI agent might be asked to do

- Add a new project post: create `src/content/projects/<slug>.md` with the required frontmatter and an image in `public/images/projects/<slug>/`.
- Update layout header: edit `src/layouts/BaseLayout.astro` and `src/components/Nav.astro` together to preserve layout integrity.
- Add a small UI component: place it in `src/components`, import in pages or layouts, and keep styles in `src/styles/global.css`.

### Tests, linters, and CI

- This repo does not include an automated test suite or linter config in source control. Follow existing code style (simple, unopinionated Astro + plain CSS) when adding changes.

### Deployment notes

- The README mentions Vercel and Cloudflare — deployments are likely handled via Vercel. The static output directory is `dist/` after `npm run build`.

### When to ask for human help

- If frontmatter schema changes are required (Zod schema edits), request a human to update existing Markdown posts or confirm a migration.
- For new runtime services (databases, server functions), get explicit instructions and credentials; this site is currently static.

---
If anything here is unclear or you want more examples (e.g., a sample new post or a small component), tell me what to add and I will update this file.
