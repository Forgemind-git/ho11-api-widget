# Sample 02 — Crypto Price Ticker

## Problem Statement

Build a self-contained HTML widget that fetches live cryptocurrency prices from the CoinGecko API (free tier, no API key required) and displays current USD prices plus 24-hour percentage changes for Bitcoin, Ethereum, and Solana with colour-coded indicators.

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
