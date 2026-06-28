# HO11 Sample 1 — Weather & AQI Widget

## What you'll build
A single web page that shows today's weather **and** air quality for your city in one tidy card — temperature, conditions, wind, humidity, the AQI number and a colour band for how clean the air is. No more flicking between three apps every morning. It uses a free public weather API (Open-Meteo) that needs **no sign-up and no key**.

## Use it with your Claude.ai subscription
No API key needed. Just your normal Claude.ai login.

1. Open **Claude.ai** in your browser and start a new chat.
2. Copy **the example prompt** below and paste it in. (Change the city if you like.)
3. Claude writes you a complete `index.html`. Copy the code block it gives you.
4. Paste it into a new file called `index.html` on your computer and **double-click** it — it opens in your browser and loads live data straight away.
5. Want it online? Drop that one file into a GitHub repo and turn on **Pages** (see "Put it online" below).

This folder already contains a finished `index.html` you can open right now — the prompt is how you'd build (and re-style) your own.

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
- Ask Claude to add a 3-day forecast, or to switch temperature to °F.
- Ask for a "rain chance" line, or a sunrise/sunset row.

## Put it online (optional, free)
1. Create a new GitHub repository and upload your `index.html`.
2. Go to **Settings → Pages → Source → Deploy from branch → main / root**.
3. Your widget goes live at `https://your-username.github.io/your-repo/`.

## Optional — automate it with the API (advanced)
You do **not** need this for the course. The widget above never calls Claude at all — it talks directly to the free weather API from your browser. If you later want Claude to summarise the weather in a sentence automatically, that would use the separate Anthropic API (a paid key, different from your Claude.ai subscription). It is entirely optional.
