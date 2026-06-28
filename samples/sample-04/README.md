# Sample 04 — Live Currency Converter

## Problem Statement

Build a self-contained HTML currency converter that fetches live exchange rates from the Frankfurter API (free, no API key required). The user enters an amount, picks from/to currencies, clicks Convert, and sees the converted amount. Not realtime — button-triggered fetch only.

## Use it with your Claude.ai subscription
No API key needed — and no **Anthropic** API key either. The converter calls the free Frankfurter API straight from the browser; Claude is only used to *build* it.

1. Open **Claude.ai** and start a new chat.
2. Paste **the example prompt** below.
3. Claude writes a complete `index.html`. Copy the code block.
4. Save it as `index.html` and **double-click** it — pick currencies and convert.
5. To go live, upload the file to a GitHub repo and turn on Pages (see "Deploy to GitHub Pages").

The finished `index.html` in this folder is the answer key — the prompt is how a beginner reproduces it.

## The example prompt
Copy this into Claude.ai:

```
Build me a single self-contained index.html file (HTML, CSS and JavaScript in one file, no build tools) for a live currency converter.

Requirements:
- Use the free Frankfurter API (no key, no sign-up):
  - List of currencies: https://api.frankfurter.app/currencies
  - Convert example: https://api.frankfurter.app/latest?amount=1&from=USD&to=EUR
- On page load, fetch the currency list and fill the "From" and "To" dropdowns (show code + full name, e.g. "USD — United States Dollar"). Default From=USD, To=EUR.
- An amount input and a "Convert" button. When clicked, call the API and show the converted amount, the rate used (1 from = x to), and the rate date.
- Dark, modern card layout. Handle errors with a friendly message.
```

## Make it your own
- Change the default currencies in the dropdowns.
- Ask Claude to add a 7-day rate history chart, or to auto-convert as you type.

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
