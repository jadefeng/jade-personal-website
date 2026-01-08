---
title: Calorie Camera
description: A prototype for estimating calories from food photos, with plans to evolve into a full AI agent.
date: 2025-12-27
overviewImage:
  src: /images/projects/calorie-camera/index.png
  alt: Screenshot of the Calorie Camera interface showing food detection
tags:
  - AI agent
  - health
  - computer vision
  - product
links:
  - label: Live site
    href: https://calorie-camera.jadefeng.com/
  - label: Repo
    href: https://github.com/jadefeng/calorie-camera
---
## Project Overview
**Calorie Camera** started from a simple question: what if I could just snap a photo of my meal and get a smart, instant calorie estimate — no typing, no logging, no searching? I’ve always found calorie tracking tedious, but I still wanted some nutritional awareness in my day-to-day life. So I built a working prototype: you take a picture of your food, the app identifies what’s on the plate, and it estimates calories using real data from nutrition APIs. The current version focuses on simplicity — a fast, no-friction calorie check with as little manual input as possible.

Long-term, I want to evolve this into a full AI agent: something that not only sees what you’re eating but also asks clarifying questions (“Is that brown rice or white?”, “Fried or grilled?”), reasons across multiple data sources, and logs meals automatically if you want it to. But for now, this is step one — proof that the core experience is possible with just a camera, a model, and a bit of reasoning.

<div style="max-width: 720px; margin: 2rem auto;">
  <iframe
    src="https://www.youtube.com/embed/d19yDLP6RY0"
    style="width: 100%; aspect-ratio: 16 / 9;"
    allowfullscreen>
  </iframe>
</div>

--- 
## Project Steps 
I built the current prototype using JavaScript, with a React frontend for the camera interface and a Node.js backend to handle food recognition and calorie estimation. For computer vision, I experimented with TensorFlow.js models and used a pre-trained classifier fine-tuned on Food-101. I also incorporated basic bounding box logic using Roboflow to detect multiple items on a plate — this helped separate foods when the image wasn’t clean.

Once a food was identified, I used both the USDA FoodData Central API and the Nutritionix API to fetch calorie estimates. These were combined and weighted depending on match confidence. For now, portion size estimation is based on rough heuristics (like image dimensions or asking the user), but I plan to refine this with either depth estimation or comparative scaling (e.g., using hand or utensil size in-frame).

Deploying the project was simple: Vercel for the frontend, Render for the backend, and GitHub for version control. I also used Replit during early stages to test ideas quickly without spinning up a full environment. GPT-4 was a huge help — not in the backend yet, but I used it as a development assistant for debugging, writing prompts, API planning, and thinking through edge cases.

**The next step is turning this into a true agent** — a system that not only identifies food but interacts intelligently: asking for clarifications, cross-checking nutritional databases, learning from user feedback, and optionally logging meals to platforms like Apple Health. I want it to feel like a helpful assistant, not a calorie cop. Just a camera, a conversation, and a bit of AI that helps you eat with more awareness.
