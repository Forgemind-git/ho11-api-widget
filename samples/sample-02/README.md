# HO11 Sample 2 — Crypto Ticker

## What you'll build
A clean price ticker that shows the live price, 24-hour change (green for up, red for down) and market cap of a few coins on one page, and quietly refreshes itself every 30 seconds. No more flicking between tabs. It uses the free **CoinGecko** public API — **no sign-up, no key**.

## Use it with your Claude.ai subscription
No API key needed. Just your normal Claude.ai login.

1. Open **Claude.ai** and start a new chat.
2. Paste **the example prompt** below. (Swap in the coins you actually follow.)
3. Claude writes a complete `index.html`. Copy the code block.
4. Save it as `index.html` and **double-click** it — live prices appear in your browser.
5. Optionally host it free on GitHub Pages (see "Put it online").

This folder already has a finished `index.html` you can open right now — the prompt is how you'd build your own version.

## The example prompt
Copy this into Claude.ai:

```
Build me a single self-contained index.html file (HTML, CSS and JavaScript in one file, no build tools) for a live crypto price ticker.

Requirements:
- Use the free CoinGecko API (no key, no sign-up):
  https://api.coingecko.com/api/v3/simple/price?ids=bitcoin,ethereum,solana&vs_currencies=usd&include_24hr_change=true&include_market_cap=true
- Show one card per coin (Bitcoin, Ethereum, Solana) with: current USD price, 24h change % coloured green if up and red if down, and market cap in billions.
- Refresh automatically every 30 seconds and on a manual "Refresh" button, and show a "Last updated" time.
- Put the list of coin ids in a clearly-labelled CONFIG block at the top so I can change which coins are shown.
- Dark, modern card layout. Handle errors with a friendly message instead of crashing.
```

## Make it your own
- Change the coin ids in the `CONFIG` block (e.g. `cardano`, `dogecoin`) — use the coin's CoinGecko id.
- Ask Claude to switch the currency from USD to EUR or INR (`vs_currencies=inr`).
- Ask for a tiny 7-day sparkline chart per coin.

## Put it online (optional, free)
1. Upload your `index.html` to a new GitHub repository.
2. **Settings → Pages → Source → Deploy from branch → main / root**.
3. Live at `https://your-username.github.io/your-repo/`.

## Optional — automate it with the API (advanced)
You do **not** need this for the course. The widget talks straight to the free CoinGecko API from your browser — Claude is not involved at runtime. Any Claude automation would use the separate paid Anthropic API key, which is different from your Claude.ai subscription and entirely optional.
