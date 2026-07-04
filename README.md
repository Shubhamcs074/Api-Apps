# Demo Apps

Two small single-page apps (plain HTML/CSS/JS, no build step) built for demonstration purposes.

- **[`/weather-app`](https://shubhamcs074.github.io/Api-Apps/weather-app/)** — "Skyward", a weather lookup app using [WeatherAPI.com](https://www.weatherapi.com/)
- **[`/news-app`](https://shubhamcs074.github.io/Api-Apps/news-app/)** — "The Signal", a news search app using [NewsAPI.org](https://newsapi.org/)

## Live demo

- Landing page: https://shubhamcs074.github.io/Api-Apps/
- Weather app: https://shubhamcs074.github.io/Api-Apps/weather-app/
- News app: https://shubhamcs074.github.io/Api-Apps/news-app/

## ⚠️ Known limitations of this demo

**API keys are visible in the page source.** Both apps call their APIs directly from the browser, so the keys are exposed to anyone who views source. This is fine for a personal demo, but for anything beyond that, the fix is a small backend/serverless proxy that holds the key server-side.

**The news app does not work once hosted live.** NewsAPI's free-tier key is restricted to requests from `localhost` only. Since this repo is live on GitHub Pages (a real domain, not `localhost`), NewsAPI rejects requests with a `corsNotAllowed` error — the app is built to display that error clearly rather than fail silently. Options to actually fix this:

1. Upgrade to a paid NewsAPI plan (lifts the localhost restriction), or
2. Add a small serverless proxy (e.g. a Cloudflare Worker or Vercel function) that holds the key server-side and forwards requests — this also solves the key-exposure issue for both apps in one shot.

The weather app does **not** have this restriction and works live as-is.