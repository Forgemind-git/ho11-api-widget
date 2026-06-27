# Sample 01 — Weather & Air Quality Widget

## Problem Statement

Build a self-contained HTML widget that fetches live weather and air quality data for any location using **two free public APIs** (no API key required) and displays temperature, weather conditions, wind speed, PM2.5 particulate matter, and AQI with colour-coded health ratings.

## APIs Used

| API | Endpoint | Key Required? |
|-----|----------|--------------|
| Open-Meteo Weather | `https://api.open-meteo.com/v1/forecast` | No |
| Open-Meteo Air Quality | `https://air-quality-api.open-meteo.com/v1/air-quality` | No |

## What It Shows

- Current temperature (°C)
- Weather description (derived from WMO weather code)
- Wind speed (km/h)
- PM2.5 particulate concentration (μg/m³)
- US AQI value with colour-coded health category:
  - **Green** — Good (0–50)
  - **Yellow** — Moderate (51–100)
  - **Orange** — Unhealthy for Sensitive Groups (101–150)
  - **Red** — Unhealthy (151–200)
  - **Purple** — Very Unhealthy (201–300)
  - **Maroon** — Hazardous (300+)

## How to Use

1. Open `index.html` in any modern browser — no server needed.
2. The widget defaults to **New Delhi, India** (lat 28.6139, lon 77.2090).
3. To change location, edit the `CONFIG` block near the top of the `<script>` tag:

```js
const CONFIG = {
  LATITUDE: 28.6139,
  LONGITUDE: 77.2090,
  CITY_NAME: "New Delhi, India"
};
```

4. Save and refresh — data loads automatically on page open.

## No API Key Setup

Both APIs are completely free with no registration. Just open the file and it works.

## Deploy to GitHub Pages

1. Push `index.html` to a GitHub repo (e.g. `username/weather-widget`).
2. Go to **Settings → Pages → Source → Deploy from branch → main / root**.
3. Your widget will be live at `https://username.github.io/weather-widget/`.
