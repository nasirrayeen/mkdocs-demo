---
date: 2026-10-11
categories:
  - Tutorials
  - MkDocs
description: A simple, maintainable way to publish a fast static blog with Markdown.
---

# Starting a blog with MkDocs

Sometimes the best publishing setup is the one that stays out of your way. MkDocs turns plain Markdown files into a polished static site, and Material for MkDocs adds search, navigation, and a flexible theme.

<!-- more -->

## Write in Markdown

Each post is a text file. That makes it easy to draft in any editor, review changes with Git, and keep the source portable.

Add a post under `docs/blog/posts/` with a date and a short description:

```yaml
---
date: 2026-10-11
categories:
  - Tutorials
description: A short summary shown with the post preview.
---
```

Give each post a clear heading, then write naturally. The blog plugin uses the metadata to organize posts and build archive and category pages.

## Preview before publishing

Run `mkdocs serve` while writing to preview changes locally. When the site is ready, `mkdocs build --strict` checks the project and generates the static files.

## Keep publishing simple

With the source in Git and a GitHub Actions workflow, each push to the main branch can build and publish the site. The result is quick to load, easy to back up, and does not need a server to run.

The most important part is not the tooling: it is having a small, repeatable path from an idea to a published post.
