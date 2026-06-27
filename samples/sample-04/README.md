# Sample 04 — Live Currency Converter

## Problem Statement

Build a self-contained HTML currency converter that fetches live exchange rates from the Frankfurter API (free, no API key required). The user enters an amount, picks from/to currencies, clicks Convert, and sees the converted amount. Not realtime — button-triggered fetch only.

## API Used

| API | Endpoint | Key Required? |
|-----|----------|--------------|
| Frankfurter | `https://api.frankfurter.app/latest?from=USD` | No |

## What It Shows

- Amount input field
- From-currency dropdown (populated from live API)
- To-currency dropdown (populated from live API)
- Converted amount displayed prominently after clicking Convert
- Exchange rate used (e.g. "1 USD = 0.9234 EUR")
- Date of the rate

## How to Use

1. Open `index.html` in any modern browser — no server needed.
2. Enter an amount (default: 1).
3. Select your source and target currencies from the dropdowns.
4. Click **Convert** to fetch the live rate and calculate.

## No API Key Setup

Frankfurter is entirely free with no registration. It uses ECB (European Central Bank) rates updated daily on business days.

## Deploy to GitHub Pages

1. Push `index.html` to a GitHub repo (e.g. `username/currency-converter`).
2. Go to **Settings → Pages → Source → Deploy from branch → main / root**.
3. Your converter will be live at `https://username.github.io/currency-converter/`.
