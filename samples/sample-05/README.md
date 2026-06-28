# Sample 05 — Daily Inspiration + Joke Feed

## Problem Statement

Build a self-contained HTML widget that fetches a random inspirational quote from ZenQuotes and a random dad joke from icanhazdadjoke, displays them as styled cards, and lets the user refresh for new ones with a button click.

## Use it with your Claude.ai subscription
No API key needed — and no **Anthropic** API key either. The widget calls the free quote and joke APIs straight from the browser; Claude is only used to *build* it.

1. Open **Claude.ai** and start a new chat.
2. Paste **the example prompt** below.
3. Claude writes a complete `index.html`. Copy the code block.
4. Save it as `index.html` and **double-click** it — a quote and a joke appear.
5. To go live, upload the file to a GitHub repo and turn on Pages (see "Deploy to GitHub Pages").

The finished `index.html` in this folder is the answer key — the prompt is how a beginner reproduces it.

## The example prompt
Copy this into Claude.ai:

```
Build me a single self-contained index.html file (HTML, CSS and JavaScript in one file, no build tools) for a "quote of the day + joke" widget.

Requirements:
- Quote API (free, no key): https://zenquotes.io/api/random  — it returns an array like [{ "q": "quote text", "a": "author" }].
- Joke API (free, no key): https://icanhazdadjoke.com/  — send the header Accept: application/json and it returns { "joke": "..." }.
- On page load and on a "Get new ones" button, fetch both at the same time (Promise.all).
- Show the quote in big italic text with the author underneath, and the joke in its own card.
- Important: some quote APIs block browser requests (CORS). If the quote fetch fails, fall back to a small built-in list of quotes baked into the file so the widget never looks broken.
- Dark, modern two-card layout. Handle errors gracefully with a friendly message.
```

## Make it your own
- Replace the built-in fallback quotes with your own favourites.
- Ask Claude to add a "reveal punchline" button or auto-rotate the quote.

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
