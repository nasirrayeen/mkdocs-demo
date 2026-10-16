# DevOps Fieldnotes

A blog about modern software delivery and operations, built with [MkDocs](https://www.mkdocs.org/) and [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/).

**Live site:** <https://nasirrayeen.github.io/mkdocs-demo/>

## Run locally

Requires Python 3.12 or later.

```powershell
python -m venv .venv
.\.venv\Scripts\python -m pip install -r requirements.txt
.\.venv\Scripts\mkdocs serve
```

Open <http://127.0.0.1:8000> to preview the site. Build it with:

```powershell
.\.venv\Scripts\mkdocs build --strict
```

## Write a blog post

Create a Markdown file under `docs/blog/posts/`. Add metadata at the top:

```yaml
---
date: 2026-10-11
categories:
  - DevOps
description: A short summary displayed with the post preview.
---
```

Add a title and an introductory excerpt, followed by `<!-- more -->` to mark where the preview ends. Use an ISO date (`YYYY-MM-DD`) and one or more categories such as DevOps, CI/CD, Platform Engineering, Reliability, or Security.

## Deployment

Pushing to `main` runs the GitHub Actions workflow in `.github/workflows/deploy.yml`. It builds the site and deploys it to GitHub Pages. The repository's Pages source should be set to **GitHub Actions**.

## PAT expiry reminders

The `PAT Expiry Reminder` workflow checks the configured personal access token's expiry once a day and sends a Slack reminder when it is within seven days of expiry (and daily after expiry until its date is updated).

Configure these under the repository's **Settings → Secrets and variables → Actions**:

- Add the repository variable `PAT_EXPIRY_DATE` with the token's expiry date in `YYYY-MM-DD` format.
- Add the repository secret `SLACK_WEBHOOK_URL` with a Slack incoming webhook URL.

The expiry date is not available from a GitHub Actions repository secret, so update `PAT_EXPIRY_DATE` whenever the PAT is rotated. Use **Actions → PAT Expiry Reminder → Run workflow** to test the configuration; a Slack message is sent only when the expiry is within seven days.
