# Sample 01 — Weather & Air Quality Widget

## Problem Statement

Build a self-contained HTML widget that fetches live weather and air quality data for any location using **two free public APIs** (no API key required) and displays temperature, weather conditions, wind speed, PM2.5 particulate matter, and AQI with colour-coded health ratings.

## Use it with your Claude.ai subscription
No API key needed — and no **Anthropic** API key either. This widget calls a free public weather API directly from the browser; Claude is only used to *build* it.

1. Open **Claude.ai** in your browser and start a new chat.
2. Copy **the example prompt** below and paste it in (change the city if you want).
3. Claude writes a complete `index.html`. Copy the code block it gives you.
4. Save it as `index.html` and **double-click** it — it opens in your browser and loads live data.
5. To go live, upload that one file to a GitHub repo and turn on Pages (see "Deploy to GitHub Pages" below).

The finished `index.html` in this folder is the answer key — the prompt is how a beginner reproduces it.

## The example prompt
Copy this into Claude.ai:

```
Build me a single self-contained index.html file (HTML, CSS and JavaScript all in one file, no build tools) for a weather and air-quality widget.

Requirements:
- Use the free Open-Meteo APIs (no API key, no sign-up):
  - Weather: https://api.open-meteo.com/v1/forecast?latitude=28.6139&longitude=77.2090&current=temperature_2m,relative_humidity_2m,wind_speed_10m,weather_code
  - Air quality: https://air-quality-api.open-meteo.com/v1/air-quality?latitude=28.6139&longitude=77.2090&current=pm2_5,us_aqi
- Default location is New Delhi (latitude 28.6139, longitude 77.2090). Put the latitude, longitude and city name in a clearly-labelled CONFIG block at the top of the script so I can change my city easily.
- Fetch both APIs when the page loads, and again when a "Refresh" button is clicked.
- Show: temperature in °C, a plain-English weather condition (translate the Open-Meteo weather_code), wind speed in km/h, humidity %, the US AQI number and PM2.5.
- Colour the AQI as a coloured pill: green Good (0–50), yellow Moderate (51–100), orange (101–150), red (151–200), purple (201–300), maroon (300+).
- Dark, modern card layout. Show a "Last updated" time. Handle errors gracefully with a friendly message.
```

## Make it your own
- Change the latitude/longitude/city in the `CONFIG` block to your own town (find coords at latlong.net).
- Ask Claude to add a 3-day forecast or switch temperature to °F.

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
