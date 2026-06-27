# Sample 03 — GitHub Repo Stats Card

## Problem Statement

Build a self-contained HTML widget that fetches public repository statistics from the GitHub REST API (no authentication required for public repos) and displays stars, forks, open issues, last push date, and primary language in a clean stat card layout.

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
