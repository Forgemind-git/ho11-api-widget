# Sample 03 — GitHub Repo Stats Card

## Problem Statement

Build a self-contained HTML widget that fetches public repository statistics from the GitHub REST API (no authentication required for public repos) and displays stars, forks, open issues, last push date, and primary language in a clean stat card layout.

## Use it with your Claude.ai subscription
No API key needed — and no **Anthropic** API key either. The card calls the free GitHub API straight from the browser; Claude is only used to *build* it.

1. Open **Claude.ai** and start a new chat.
2. Paste **the example prompt** below (point it at whatever repo you care about).
3. Claude writes a complete `index.html`. Copy the code block.
4. Save it as `index.html` and **double-click** it — the live numbers load.
5. To go live, upload the file to a GitHub repo and turn on Pages (see "Deploy to GitHub Pages").

The finished `index.html` in this folder is the answer key — the prompt is how a beginner reproduces it.

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
- Ask Claude to add the top contributor or the latest commits.

## API Used

| API | Endpoint | Key Required? |
|-----|----------|--------------|
| GitHub REST API | `https://api.github.com/repos/{owner}/{repo}` | No (public repos) |

## What It Shows

- Repository name and description
- Star count
- Fork count
- Open issues count
- Primary programming language (colour-coded dot)
- Date of last push (formatted as relative time)
- Repository topics/tags
- Link to the repo on GitHub

## How to Use

1. Open `index.html` in any modern browser — no server needed.
2. The widget defaults to **facebook/react**.
3. To show a different repo, edit the `CONFIG` block in the `<script>` tag:

```js
const CONFIG = {
  GITHUB_OWNER: "facebook",  // GitHub username or org
  GITHUB_REPO:  "react"      // Repository name
};
```

4. Save and refresh — data loads automatically.

## API Key Setup

No API key required for public repositories. The unauthenticated rate limit is **60 requests/hour per IP**. If you need more, create a GitHub personal access token and add it:

```js
const CONFIG = {
  GITHUB_OWNER: "facebook",
  GITHUB_REPO:  "react",
  GITHUB_TOKEN: "ghp_yourTokenHere"  // Optional — raises limit to 5000 req/hr
};
```

## Deploy to GitHub Pages

1. Push `index.html` to a GitHub repo (e.g. `username/github-stats-card`).
2. Go to **Settings → Pages → Source → Deploy from branch → main / root**.
3. Your card will be live at `https://username.github.io/github-stats-card/`.
