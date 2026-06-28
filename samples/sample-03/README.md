# HO11 Sample 3 — GitHub Stats Card

## What you'll build
A neat card that shows a GitHub repo's health at a glance — stars, forks, open issues, main language and when it was last updated — so you don't have to keep opening GitHub. It uses the **GitHub REST API**, which is **free and needs no key** for public repositories.

## Use it with your Claude.ai subscription
No API key needed. Just your normal Claude.ai login.

1. Open **Claude.ai** and start a new chat.
2. Paste **the example prompt** below. (Point it at whatever repo you care about.)
3. Claude writes a complete `index.html`. Copy the code block.
4. Save it as `index.html` and **double-click** to open it — the live numbers load straight away.
5. Optionally host it free on GitHub Pages (see "Put it online").

This folder already has a finished `index.html` you can open right now — the prompt is how you'd build your own version.

## The example prompt
Copy this into Claude.ai:

```
Build me a single self-contained index.html file (HTML, CSS and JavaScript in one file, no build tools) for a GitHub repository stats card.

Requirements:
- Use the free GitHub REST API (no key needed for public repos):
  https://api.github.com/repos/facebook/react
- Put OWNER and REPO in a clearly-labelled CONFIG block at the top (default to facebook / react) so I can change the repo easily.
- Fetch the repo on page load and on a "Refresh" button.
- Show: full repo name, description, stars, forks, open issues, the main language with a coloured dot, and the last-updated date (formatted nicely from pushed_at).
- Format big numbers with commas (e.g. 228,000).
- Dark, modern card layout. If the repo isn't found or the rate limit is hit, show a friendly error message.
```

## Make it your own
- Change `OWNER` and `REPO` in the `CONFIG` block to your own repo.
- Ask Claude to add the top contributor (from `/repos/OWNER/REPO/contributors?per_page=1`).
- Ask for a list of the latest 5 commits or open issues.

## Put it online (optional, free)
1. Upload your `index.html` to a new GitHub repository.
2. **Settings → Pages → Source → Deploy from branch → main / root**.
3. Live at `https://your-username.github.io/your-repo/`.

## Note on limits
The GitHub API allows about 60 unprivileged requests per hour per IP — plenty for a personal card. No key is required for public repos.

## Optional — automate it with the API (advanced)
You do **not** need this for the course. The card calls GitHub directly from your browser; Claude isn't involved at runtime. Any Claude automation would use the separate paid Anthropic API key (different from your Claude.ai subscription) and is entirely optional.
