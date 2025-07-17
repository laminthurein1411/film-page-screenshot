## Letterboxd Poster 🎬

This project fetches Letterboxd RSS feeds, processes them through a Cloudflare Worker, and returns the result as a poster-style webpage and image.

---

### Motivation & Challenges

- **Cloudflare Browser Rendering:**  
  My initial approach involved using Cloudflare Browser Rendering, but it requires a paid plan 💸.
- **Cloudflare Worker Puppeteer:**  
  I also tried Cloudflare's forked Puppeteer on their free worker tier, but it was either broken or I couldn’t get it working 🤷‍♂️.

---

### How It Works

1. **Automated Screenshot:**  
   A [GitHub Actions](.github/workflows/screenshot.yml) workflow uses Puppeteer to capture a screenshot of the Letterboxd poster webpage once a day.

2. **Automatic Push:**  
   The screenshot (`film.jpg`) and `index.html` are committed and pushed to this repository by the workflow.

3. **Instant Static Deployment:**  
   [Cloudflare Pages](https://pages.cloudflare.com/) watches this repo and instantly updates the hosted site and image on every push.

---

### 🚀 Live Demo

- **Poster image:**  
  ![Daily Letterboxd Poster](https://letterboxdlrs.pages.dev/film.jpg)

- **Webpage with context:**  
  [https://letterboxdlrs.pages.dev/](https://letterboxdlrs.pages.dev/)

---

### ⚙️ Technology Stack

- **GitHub Actions:** Automates the daily screenshot and git push.
- **Puppeteer:** Headless browser for rendering and capturing screenshots.
- **Cloudflare Pages:** Deploys and serves the static site and image from the edge for fast global access.

---

### ⏱️ Efficiency

- **Build Time:** Each GitHub Actions run takes ~1–2 minutes per day (≈ 60–70 min/month).
- **Hosting:** Using Cloudflare Pages for low-latency, edge-cached static hosting.  
  *(GitHub Pages is also supported, but Cloudflare offers better global performance.)*

---

### 🙏 Achknowledgement

- This project is solely based on [letterboxd-diary-embe](https://github.com/timciep/letterboxd-diary-embed)
- Worker to poster-style webpage avaiable [here](https://github.com/abusayed0206/letterboxd-diary-embed)

### 📂 Files

- `film.jpg` — The latest screenshot, updated daily.
- `index.html` — Webpage displaying the screenshot with metadata.
- `.github/workflows/screenshot.yml` — Automation workflow.
- `package.json` — Puppeteer dependency.

---

### 📜 License

MIT License © 2024 [MD. ABU SAYED](https://github.com/abusayed0206)

---
