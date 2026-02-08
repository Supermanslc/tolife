# 🥂 ToLife! v1.0 — Setup Guide

## Quick Start: GitHub Pages

1. **Create a new repo** on GitHub called `tolife` (or any name)
2. **Upload these files** to the repo:
   - `index.html`
   - `app.js`
   - `styles.css`
   - `sw.js`
   - `manifest.json`
   - `icons/` folder (all .png files)
3. **Enable GitHub Pages**: Settings → Pages → Source: "main" branch → Save
4. **Visit** `https://your-username.github.io/tolife/`

## AI Calorie Estimator (Optional but Recommended)

The AI feature uses Claude to estimate calories from natural language. Two options:

### Option A: Cloudflare Worker (Recommended)
Since you already have a Cloudflare account:

1. Go to **Cloudflare Dashboard** → Workers & Pages → Create
2. Name it `tolife-ai`
3. Paste the code from `cloudflare-worker-ai.js`
4. Go to **Settings** → Variables → Add:
   - Name: `ANTHROPIC_API_KEY`
   - Value: Your Anthropic API key (get one at console.anthropic.com)
   - Click "Encrypt"
5. **Deploy**
6. Copy your worker URL (e.g., `https://tolife-ai.shawn-cohenmd.workers.dev`)
7. In `app.js`, update: `workerUrl: 'https://tolife-ai.your-subdomain.workers.dev'`
8. Push to GitHub

### Option B: Direct API (Works in Claude Artifacts)
If you preview the app as a Claude artifact, it can call Claude's API directly — no worker needed.

## Files Included

| File | Purpose |
|------|---------|
| `index.html` | Main app structure (6 pages) |
| `app.js` | All app logic, AI calorie estimation, data management |
| `styles.css` | Complete styling with dark/light themes |
| `sw.js` | Service worker for offline PWA |
| `manifest.json` | PWA manifest for install-to-homescreen |
| `icons/` | App icons (16px to 512px) |
| `cloudflare-worker-ai.js` | Cloudflare Worker for AI calorie proxy |

## Features (v1.0)

- 📊 **Dashboard** — Progress ring, weekly grid, weight chart, smart nudges
- 🌅 **Daily Check-In** — Stress, sleep, energy, calorie budget by activity level
- 🍽 **AI Nutrition** — Natural language calorie entry, My Foods recall system
- 🏋️ **Workout Logger** — RPE 1-10, cardio duration/focus, optional HR
- ⚖️ **Weight Tracker** — BMR/TDEE calculator, 7-day rolling average
- 🧠 **Insights** — Stress-behavior correlations, adaptive suggestions, streaks
- 🌙 **Dark/Light mode** — Dark default with toggle
- 💾 **Data** — localStorage + JSON export/import

## Your Settings

- Height: 5'8" (68 inches)
- Start Weight: 179 lbs
- Goal: 158 lbs in 8 weeks
- Calorie adjustment: +5% intake / -5% expenditure
- Deficit: 750 cal/day (~1.5 lbs/week)

*L'Chaim!* 🥂
