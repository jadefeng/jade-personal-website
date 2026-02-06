---
title: Camp Management App for Burning Man
description: A custom platform built to manage 300+ campers, shift scheduling, and logistics for Opulent Temple at Burning Man.
date: 2026-02-05
overviewImage:
  src: /images/projects/campmaker/index.png
  alt: Screenshot of the Camp Maker map interface showing tent and RV placements
tags:
  - community
  - logistics
  - product
  - burning man
links:
  - label: Live site
    href: https://demo.playalead.com/map
  - label: GitHub
    href: https://github.com/matidomingues/camp-maker 
---

## Project Overview

For the past few years, I've been a camp lead at Opulent Temple, one of Burning Man's oldest theme camps with over 300 members annually. Managing logistics for that many people in the middle of the desert, entirely volunteer-run, is equal parts operational chaos and pure magic.

This year, I built a custom camp management platform to replace the pen-and-paper, ad-hoc systems we'd been juggling for years. The challenge? Coordinating 20+ volunteer core members to manage tent/RV placements with individual customizations (tent sizes, power needs, RV hookups) within limited square footage, tracking 300+ members each with 2-4 shift assignments, and handling camp support requests that were previously scattered across clipboards and word of mouth.

**The solution is a centralized management app with:**
- **Interactive map view** – drag-and-drop placement for tents/RVs, sized to individual specifications
- **Member dashboard** – searchable directory of all campers
- **Dwelling management** – track who's in each tent/RV and where they're located
- **Shift system** – assign shifts, check-ins, and flag no-shows
- **Ticketing system** – tag, assign, and track camp issues (power, water, lost items) with accountability
- **Permission controls** – role-based access for camp leadership

Since wifi is limited on playa, we're running a local network server alongside Starlink to ensure multiple camp leads can access the app simultaneously.

---

## Project Steps

I built the platform using React for the frontend with an interactive drag-and-drop map interface powered by a custom grid system. The backend uses Node.js with a PostgreSQL database to handle member data, shift assignments, dwelling placements, and ticketing workflows. Authentication and permissions are managed through role-based access control so only camp leads can make critical edits.

The map view was the trickiest piece. I needed to account for different tent and RV sizes, power requirements, and physical constraints from Burning Man's allocated space. I built a visual grid system where each dwelling can be dragged, resized, and configured with custom attributes. The shift management system pulls from the member database and allows leads to assign, check in, and track no-shows in real-time.

For deployment, I used Vercel for the frontend and Railway for the backend, with GitHub for version control. Since internet connectivity on playa is unreliable, I also set up a local network server that syncs with the cloud when connectivity is available but can run independently during outages.

**The most rewarding part** of rapid prototyping is building for problems you live with daily. We built this to solve our own operational headaches, but we're excited to test it at Burning Man this year and potentially make it available to other camps facing similar logistical challenges.

The next iteration will focus on mobile optimization (since most camp leads are walking around with phones, not laptops), offline-first architecture for better playa resilience, and potentially integrating with Burning Man's official placement systems if we can get API access.
```