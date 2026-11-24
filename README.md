# HackHarbor — HackVerse 2026

A responsive React/Vite hackathon portal and hackathon-operations MVP, based on the supplied HackOps Live brief.

## What's included

- `static-phase/index.html` + `static-phase/styles.css`: standalone HTML/CSS landing page for Modules 1–2, including CSS custom properties, a CSS-only theme toggle, animated hero, tracks, prize pool and FAQ. Open `static-phase/index.html` directly in a browser.

- Responsive landing page with five challenge tracks, prize tiers, FAQ accordion, event countdown, CSS custom properties, animations and dark/light mode.
- Team registration with a team lead and up to three additional members (four people total).
- Project submission form with GitHub repository validation, demo/video links and comma-separated tech-stack tags.
- Judge console with a demo passcode and four weighted judging criteria: Innovation 30%, Technical Complexity 30%, UI/UX 20%, Presentation 20%.
- Weighted score aggregation and animated/filterable live leaderboard.
- Starter dataset: 12 teams, 8 projects and 4 judge profiles, so the demo is populated on first launch.
- Browser `localStorage` persistence and cross-tab synchronization.

## Requirements

- Node.js 20.19+ or 22.12+
- npm

## Run locally

```bash
npm install
npm run dev
```

Open the local URL printed by Vite (usually `http://localhost:5173`).

## Production build

```bash
npm run build
npm run preview
```

The generated static website is written to `dist/`.

## Demo walkthrough

1. Open the landing page and explore the tracks and prize pool.
2. Open **Register** and create a team. The sample team data is already present, so use a unique team name and email address.
3. Open **Submit idea** and attach a project to your new team.
4. Open **Judges** and use the demo passcode `HARBOR2026`.
5. Choose a judge profile and project, score all four criteria, then save the evaluation.
6. Open **Leaderboard** to see the aggregated score and rank.

The sample dataset includes the CardioScan / QuantumCoders demo project and other teams/projects to make the leaderboard useful immediately.

## Customize event details

Edit `src/data/eventConfig.js` to change the event name, countdown target, prize pool and demo judge passcode. The current countdown date is a placeholder for the prototype; replace it with your confirmed event date.

Edit `src/data/seed.js` to change the sample teams, projects and scores. User changes are kept in browser storage. To reset the current browser to the starter dataset, open DevTools → Application → Local Storage and remove `hackharbor-v1` and `hackharbor-theme`, then reload the page.

## Important prototype / production notes

This version is a front-end MVP. It uses browser storage instead of a shared database. Changes persist in the current browser and synchronize between tabs in that browser, but not between different users' devices. The judge passcode is a client-side demo gate and is **not secure authentication**. For a real event, add a backend (for example Node.js + Express), a database (SQLite or PostgreSQL), server-side role-based authentication, email invitations, input validation, rate limiting and server-authoritative score calculations. Do not use the demo passcode for a real judging event.

## Main project structure

```text
src/
  components/Layout.jsx
  context/HackathonContext.jsx
  data/eventConfig.js
  data/seed.js
  pages/Home.jsx
  pages/Register.jsx
  pages/Submit.jsx
  pages/Judge.jsx
  pages/Leaderboard.jsx
  utils/scoring.js
  App.jsx
  main.jsx
  styles.css
```
