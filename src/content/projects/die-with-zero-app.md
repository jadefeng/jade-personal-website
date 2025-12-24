---
title: Cooking Tempo
description: A cooking planning app that turns recipes into a unified, timed execution plan so everything is ready at the same time.
date: 2025-12-24
overviewImage:
  src: /images/projects/cooking-tempo/index.png
  alt: Screenshot of the Cooking Tempo app interface
tags:
  - product
  - ai
  - cooking
links:
  - label: App demo
    href: https://youtu.be/Sk960NdMICo
  - label: Live site
    href: https://cooking-tempo.jadefeng.com
  - label: Repo
    href: https://github.com/jadefeng/cooking-tempo 

---
## Project Overview
I’ve been building small, useful products using ChatGPT and Codex, and Cooking Tempo is one of those projects. The idea came from planning holiday dinner parties for friends. I kept running into the same frustration: deciding what to make, finding recipes that worked well together, and turning them into a plan I could actually execute so everything was ready at the same time, not cold when guests arrived.

Most recipes tell you what to do, but not when to do it, especially when you’re juggling multiple dishes. Cooking Tempo was my attempt to solve that gap by turning recipes into a coordinated, time-aware cooking plan that keeps you focused on one simple question: **what should I be doing now?**

<div style="max-width: 720px; margin: 2rem auto;">
  <iframe
    src="https://www.youtube.com/embed/Sk960NdMICo"
    style="width: 100%; aspect-ratio: 16 / 9;"
    allowfullscreen>
  </iframe>
</div>


--- 
## Key Use Cases

Cooking Tempo is designed around a few core workflows:

- Generate recipes from a prompt or import them from an existing recipe URL
- Break each recipe into timed, sequential steps
- Combine multiple recipes into a single, cohesive meal
- Consolidate all ingredients into one shopping list, stored locally in the browser
- Organize the entire meal into a unified, interactive cooking timeline
- Provide step-level timing guidance so execution stays smooth and stress-free

The goal is to reduce cognitive load while cooking, especially when hosting.

## Project Steps

### 1. Product ideation and scoping with ChatGPT

I used ChatGPT as a product thinking partner from the very beginning. It helped me clarify the problem, scope the MVP, reason through edge cases, and design the initial data model. It was especially critical in the first step, where I asked it to help me design the prompt I would later give to Codex to scaffold the app.

### 2. Scaffolding and iteration with Codex

Codex handled most of the heavy lifting on the engineering side. I used it to scaffold the app, write boilerplate code, and iterate quickly on features. Running Codex directly in the terminal made it easy to build inside the project directory and debug issues by pasting in error messages as they came up.

### 3. Core app logic with the OpenAI API

The heart of Cooking Tempo uses the OpenAI API to generate recipes and transform them into structured, timed steps. This allows the app to go from a simple prompt or URL to an actionable cooking plan that can be coordinated across multiple dishes.

### 4. Database design with Postgres

I used Postgres to store recipes and meals, where a meal is a collection of recipes. Spending time upfront on a clear schema made development much smoother as features evolved.

### 5. Deployment and hosting with Vercel

Vercel made it easy to deploy quickly and manage environment variables. Every push triggers a new deployment, which kept iteration fast and low-friction.

### 6. DNS and reliability with Cloudflare

Cloudflare handled DNS and domain management, giving me an easy way to point the domain and add a layer of reliability without much overhead.

### 7. Lightweight branding with AI image generation

To avoid getting blocked on design, I used AI image generation for thumbnails and icons. This made it much faster to land on something cohesive and presentable while keeping the focus on product functionality.