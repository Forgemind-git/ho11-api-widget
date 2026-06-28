# HO11 Sample 5 — Quote & Joke Feed

## What you'll build
A friendly little widget for your personal page that shows an inspiring quote of the day plus a programming/dad joke, with a button to fetch fresh ones. It uses two free public APIs (**ZenQuotes** for quotes, **icanhazdadjoke** for jokes) — **no sign-up, no key**.

## Use it with your Claude.ai subscription
No API key needed. Just your normal Claude.ai login.

1. Open **Claude.ai** and start a new chat.
2. Paste **the example prompt** below.
3. Claude writes a complete `index.html`. Copy the code block.
4. Save it as `index.html` and **double-click** it — a quote and a joke appear.
5. Optionally host it free on GitHub Pages (see "Put it online").

This folder already has a finished `index.html` you can open right now — the prompt is how you'd build your own version.

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
- Ask Claude to swap the joke API for a different one, or add a "reveal punchline" button.
- Ask it to auto-rotate to a new quote every 30 seconds.

## Put it online (optional, free)
1. Upload your `index.html` to a new GitHub repository.
2. **Settings → Pages → Source → Deploy from branch → main / root**.
3. Live at `https://your-username.github.io/your-repo/`.

## Note on browser limits
Some public APIs (like ZenQuotes) restrict requests made directly from a browser (CORS). The example prompt asks Claude to include a small built-in fallback list so your widget always shows something, even if the live quote can't load.

## Optional — automate it with the API (advanced)
You do **not** need this for the course. The widget calls the quote and joke APIs directly from your browser; Claude isn't involved at runtime. If you later wanted Claude to *write* original quotes or jokes, that would use the separate paid Anthropic API key (different from your Claude.ai subscription) and is entirely optional.
