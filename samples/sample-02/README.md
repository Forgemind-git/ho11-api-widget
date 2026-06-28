# Sample 02 — Crypto Price Ticker

## Problem Statement

Build a self-contained HTML widget that fetches live cryptocurrency prices from the CoinGecko API (free tier, no API key required) and displays current USD prices plus 24-hour percentage changes for Bitcoin, Ethereum, and Solana with colour-coded indicators.

## Use it with your Claude.ai subscription
No API key needed — and no **Anthropic** API key either. The widget calls the free CoinGecko API straight from the browser; Claude is only used to *build* it.

1. Open **Claude.ai** and start a new chat.
2. Paste **the example prompt** below (swap in the coins you follow).
3. Claude writes a complete `index.html`. Copy the code block.
4. Save it as `index.html` and **double-click** it — live prices appear.
5. To go live, upload the file to a GitHub repo and turn on Pages (see "Deploy to GitHub Pages").

The finished `index.html` in this folder is the answer key — the prompt is how a beginner reproduces it.

## The example prompt
Copy this into Claude.ai:

```
Build me a single self-contained index.html file (HTML, CSS and JavaScript in one file, no build tools) for a live crypto price ticker.

Requirements:
- Use the free CoinGecko API (no key, no sign-up):
  https://api.coingecko.com/api/v3/simple/price?ids=bitcoin,ethereum,solana&vs_currencies=usd&include_24hr_change=true&include_market_cap=true
- Show one card per coin (Bitcoin, Ethereum, Solana) with: current USD price, 24h change % coloured green if up and red if down, and market cap in billions.
- Refresh automatically every 60 seconds and on a manual "Refresh" button, and show a "Last updated" time.
- Put the list of coin ids in a clearly-labelled CONFIG block at the top so I can change which coins are shown.
- Dark, modern card layout. Handle errors with a friendly message instead of crashing.
```

## Make it your own
- Change the coin ids in the `CONFIG` block (find them at https://api.coingecko.com/api/v3/coins/list).
- Ask Claude to switch the currency from USD to EUR or INR.

## API Used

| API | Endpoint | Key Required? |
|-----|----------|--------------|
| CoinGecko Simple Price | `https://api.coingecko.com/api/v3/simple/price` | No (free tier) |

## What It Shows

- Current USD price for BTC, ETH, and SOL
- 24-hour price change percentage for each coin
- Colour coding: green for positive change, red for negative change
- Auto-refresh every 60 seconds
- Manual refresh button

## How to Use

1. Open `index.html` in any modern browser — no server needed.
2. Data loads automatically on page open.
3. To add more coins, edit the `CONFIG` block in the `<script>` tag:

```js
const CONFIG = {
  COINS: ["bitcoin", "ethereum", "solana"],  // CoinGecko coin IDs
  VS_CURRENCY: "usd",                         // Target currency
  AUTO_REFRESH_SECONDS: 60                    // 0 to disable
};
```

Find CoinGecko coin IDs at: https://api.coingecko.com/api/v3/coins/list

## No API Key Setup

CoinGecko's free public API works without any key. Rate limit is ~30 requests/minute — the auto-refresh interval is set to 60s to stay well within limits.

## Deploy to GitHub Pages

1. Push `index.html` to a GitHub repo (e.g. `username/crypto-ticker`).
2. Go to **Settings → Pages → Source → Deploy from branch → main / root**.
3. Your ticker will be live at `https://username.github.io/crypto-ticker/`.
