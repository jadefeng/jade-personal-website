---
title: Personal Website
description: Building a personal website from scratch to showcase my thoughts and building experience with AI tools.
date: 2025-12-16
overviewImage:
  src: /images/projects/personal-website/index.png
  alt: Screenshot of the personal website homepage
tags:
  - product
  - finance
links:
  - label: Live site
    href: https://jadefeng.com/
  - label: Repo
    href: https://github.com/jadefeng/jade-personal-website

---
## Project Overview
I started this site as a home for the things I’m thinking about and building. I wanted a place to document projects I’m experimenting with, capture what I’m learning as I explore AI, and keep a personal record of the books and ideas that have shaped how I see the world. It’s part notebook, part portfolio, and part memory.

<img
  src="/images/projects/personal-website/index.png"
  alt="Screenshot"
  style="max-width: 500px; width: 100%;"
/>

--- 
## Project Steps 
1. Installed Codex and set up my environment
I started by installing OpenAI Codex and using it directly in my editor/browser as a coding copilot. My hands-on coding experience was from 10 years ago (!!), so my goal was to rely on Codex for scaffolding, while I focused on intent and structure.

2. Used a starter prompt to scaffold the site
Rather than starting from a blank repo, I gave Codex a  prompt to generate a simple personal site using Astro. The prompt focused on:

- a lightweight static setup
- sections for projects, thoughts, and book notes
- Markdown-based content so I could write without friction

Starter prompt I used (simplified):

> _"Create a clean, minimal personal website using Astro.
Include sections for projects, thoughts, and book notes. 
Include an "About" section that highlights an overview about me. 
Use Markdown for content, add simple navigation, and keep the design minimal and readable.
Include a footer that includes my social media links: LinkedIn, Github, X."_

This gave me a working foundation without needing to understand every decision upfront.

3. Explored Astro to understand the structure
Once the site was generated, I spent time digging around Astro’s file structure:

- src/pages to understand routing
- src/content to see how posts were organized
- public/ for static assets like images

This helped me build a mental model of how content flows into pages.

4. Iterated on design and layout with Codex
After the basics were in place, I used Codex to restyle the site based on a mood board that I grabbed from Pinterest — focusing on typography, spacing, color, and overall tone. 

I treated Codex more like a design translator than a code generator, describing how I wanted the site to feel rather than how it should be implemented.

5. Set up hosting and deployment
I connected the project to GitHub and deployed it using a static hosting provider (Vercel), which automatically builds and publishes the site on every push. This made updates low-effort and removed the need to manage servers.

6. Established a simple content workflow
Finally, I set up a repeatable workflow:

- write posts in Markdown
- store images alongside content or in public/images
- commit and push to publish via Git

This keeps the site easy to maintain and encourages me to actually use it as a living archive.
