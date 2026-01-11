---
title: Shepherd Learning
description: A mobile-first safety training MVP for construction workers, focused on OSHA education, progress accountability, and multilingual access.
date: 2026-01-10
overviewImage:
  src: /images/projects/shepherd-learning/index.png
  alt: Screenshot of the Shepherd Learning safety training interface
tags:
  - product
  - safety
  - insurtech
  - LMS
  - AI
links:
  - label: Live demo
    href: https://shepherd-learning.jadefeng.com/
  - label: Repo
    href: https://github.com/jadefeng/shepherd-learning
---
## Project Overview
**Shepherd Learning** is a mobile-first safety training platform designed to help construction workers complete OSHA-aligned education. The project was built as a product demo for Shepherd Insurance to explore how a learning management system could complement their existing Insights and Savings products by reducing jobsite risk upstream.

The MVP focuses on a narrow but high-impact use case: fixed OSHA video courses with enforced progression, lightweight assessment, and clear proof of completion. The experience is optimized for workers on-site using their phones, not administrators sitting at desks.

<div style="max-width: 720px; margin: 2rem auto;">
  <iframe
    src="https://www.youtube.com/embed/9QI5m1ZpLsI"
    style="width: 100%; aspect-ratio: 16 / 9;"
    allowfullscreen>
  </iframe>
</div>

---

## What I Built
The current demo is scoped as a **P0–P1 MVP**, emphasizing speed to value.

### Core Features
- **Multi-step learning flow** with embedded YouTube OSHA lessons  
- **Progressive locking**: users must complete each step and achieve a perfect quiz score to advance  
- **Persistent progress bar** to make completion status obvious and motivating  
- **Transcript library** loaded from markdown files for fast iteration and localization  
- **LLM-powered quiz generation** using OpenAI `gpt-4o-mini`, tailored to lesson content and language  
- **Course reset and completion review dashboard**  
- **Supabase Auth** (email/password) with password reset support  
- **Full English/Spanish toggle**, including UI copy and quiz content  

To move quickly, course progress is stored in **browser localStorage** rather than a backend database. This allowed me to validate the learning flow and enforcement mechanics without standing up Postgres or designing a full data model.

---

## Technical Approach
I built Shepherd Learning using:
- **Next.js** and **TypeScript** for the application framework  
- **Tailwind CSS** for fast, consistent UI development  
- **Supabase Auth** for authentication and session handling  
- **Vercel and Cloudflare** for hosting and DNS
- **YouTube embeds** for pre-existing OSHA content  
- **Markdown-based transcripts** to keep content editable and version-controlled  
- **OpenAI LLMs** to dynamically generate quizzes based on lesson transcripts and selected language  

---

## What I’d Build Next
If this moved beyond demo stage, the next phase would focus on:
- Server-side persistence (worker-level tracking)
- Admin views for brokers and safety managers
- Risk-based course recommendations tied to Insights data
- Certification records and exportable compliance reports

