## Letterboxd Poster 🎬

This project fetches Letterboxd RSS feeds, processes them through a worker, and returns the result as a webpage.

Initially, I tried using Cloudflare Browser Rendering, but it requires a paid plan 💸. I also faced issues with Cloudflare's forked Puppeteer on their free worker—either it wasn’t working correctly or I couldn’t get it to function properly 🤷‍♂️.

Instead, I use GitHub Actions with Puppeteer to capture a screenshot of the Letterboxd poster and push it to the GitHub repository once a day 📸. This process takes approximately 1 to 2 minutes of build time daily, totaling around 60 to 70 minutes per month 🕒.

Cloudflare Pages then deploys the screenshot automatically and serves it at: [https://letterboxdlrs.pages.dev/film.jpg](https://letterboxdlrs.pages.dev/film.jpg) 🌐.

While you can use GitHub Pages for hosting, Cloudflare offers better performance from their edge servers 🚀.