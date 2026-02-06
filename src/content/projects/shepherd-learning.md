---
title:  Learning Platform
description: A mobile-first learning app that tracks, progress accountability, and Spanish localization.
date: 2026-01-10
overviewImage:
  src: /images/projects/shepherd-learning/index.png
  alt: Screenshot of the Learning training interface
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
**Learning App** is a mobile-first training platform designed to try and make learning from videos on YouTube more bite-sized. It grabs videos from YouTube and turns them into lessons that a learner can use from their mobile phone. 

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

