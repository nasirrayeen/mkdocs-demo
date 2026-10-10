# Fieldnotes

A lightweight blog built with [MkDocs](https://www.mkdocs.org/) and [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/).

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
  - Tutorials
description: A short summary displayed with the post preview.
---
```

Add a title and an introductory excerpt, followed by `<!-- more -->` to mark where the preview ends. Use an ISO date (`YYYY-MM-DD`) and one or more categories.

## Deployment

Pushing to `main` runs the GitHub Actions workflow in `.github/workflows/deploy.yml`. It builds the site and deploys it to GitHub Pages. The repository's Pages source should be set to **GitHub Actions**.
