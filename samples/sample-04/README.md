# HO11 Sample 4 — Currency Converter

## What you'll build
A little converter where you type an amount, pick "from" and "to" currencies, and instantly see the live converted value using real exchange rates — handy when you're buying from overseas. It uses the free **Frankfurter** API (European Central Bank rates) — **no sign-up, no key**.

## Use it with your Claude.ai subscription
No API key needed. Just your normal Claude.ai login.

1. Open **Claude.ai** and start a new chat.
2. Paste **the example prompt** below.
3. Claude writes a complete `index.html`. Copy the code block.
4. Save it as `index.html` and **double-click** it — pick currencies and convert.
5. Optionally host it free on GitHub Pages (see "Put it online").

This folder already has a finished `index.html` you can open right now — the prompt is how you'd build your own version.

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
- Ask Claude to add a small 7-day rate history chart (Frankfurter supports `https://api.frankfurter.app/2024-01-01..?from=USD&to=EUR`).
- Ask it to auto-convert as you type, without needing the button.

## Put it online (optional, free)
1. Upload your `index.html` to a new GitHub repository.
2. **Settings → Pages → Source → Deploy from branch → main / root**.
3. Live at `https://your-username.github.io/your-repo/`.

## Optional — automate it with the API (advanced)
You do **not** need this for the course. The converter calls Frankfurter directly from your browser; Claude isn't involved at runtime. Any Claude automation would use the separate paid Anthropic API key (different from your Claude.ai subscription) and is entirely optional.
