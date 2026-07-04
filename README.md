# Demo Apps

Two small single-page apps (plain HTML/CSS/JS, no build step) built for demonstration purposes.

- **`/weather-app`** — "Skyward", a weather lookup app using [WeatherAPI.com](https://www.weatherapi.com/)
- **`/news-app`** — "The Signal", a news search app using [NewsAPI.org](https://newsapi.org/)

## Live demo

Once GitHub Pages is enabled on this repo (Settings → Pages → Deploy from branch → `main` → `/root`), it will be live at:

```
https://Shubhamcs074.github.io/Api-Apps/
```

## ⚠️ Known limitations of this demo

**API keys are visible in the page source.** Both apps call their APIs directly from the browser, so the keys are exposed to anyone who views source. This is fine for a personal demo, but for anything beyond that, the fix is a small backend/serverless proxy that holds the key server-side.

**The news app will not work once hosted live.** NewsAPI's free-tier key is restricted to requests from `localhost` only. Once this repo is live on GitHub Pages (a real domain, not `localhost`), NewsAPI will reject requests with a `corsNotAllowed` error — the app is built to display that error clearly rather than fail silently. Options to actually fix this for a live demo:

1. Upgrade to a paid NewsAPI plan (lifts the localhost restriction), or
2. Add a small serverless proxy (e.g. a Cloudflare Worker or Vercel function) that holds the key server-side and forwards requests — this also solves the key-exposure issue for both apps in one shot.

The weather app does **not** have this restriction and should work live as-is.
