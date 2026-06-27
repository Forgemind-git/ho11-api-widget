# Sample 05 — Daily Inspiration + Joke Feed

## Problem Statement

Build a self-contained HTML widget that fetches a random inspirational quote from ZenQuotes and a random dad joke from icanhazdadjoke, displays them as styled cards, and lets the user refresh for new ones with a button click.

## APIs Used

| API | Endpoint | Key Required? |
|-----|----------|--------------|
| ZenQuotes | `https://zenquotes.io/api/random` | No |
| icanhazdadjoke | `https://icanhazdadjoke.com/` | No (send `Accept: application/json`) |

## What It Shows

- A "Quote of the Day" card with the quote text and author name
- A "Dad Joke" card with a random joke
- Refresh button that fetches both new content simultaneously
- Loading and error states for each card independently

## How to Use

1. Open `index.html` in any modern browser — no server needed.
2. A quote and joke load automatically on page open.
3. Click **Get New Ones** to refresh both cards.

## API Key / CORS Note

**ZenQuotes CORS:** ZenQuotes does not allow direct browser requests from non-localhost origins in some environments. The widget falls back to their `allquotes` endpoint if needed, or you can open the file locally (file://) where CORS is not enforced.

**icanhazdadjoke:** Works directly from the browser — just requires the `Accept: application/json` header.

## No API Key Setup

Both APIs are completely free and require no registration or API key.

## Deploy to GitHub Pages

1. Push `index.html` to a GitHub repo (e.g. `username/joke-quote-feed`).
2. Go to **Settings → Pages → Source → Deploy from branch → main / root**.
3. Your feed will be live at `https://username.github.io/joke-quote-feed/`.

**Note on ZenQuotes CORS:** When deployed to GitHub Pages (or any non-localhost HTTPS origin), ZenQuotes may block requests due to CORS policy. In that case, the quote card will show a fallback quote. The joke card always works.
