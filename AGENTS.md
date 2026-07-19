# Repository Guide

## Overview

This repository contains the source for [kampersanda.github.io](https://kampersanda.github.io/), a Jekyll site using the remote `sighingnow/jekyll-gitbook` theme. The default and deployment branch is `deploy`.

## Content locations

- `README.md`: homepage content (rendered at `/`).
- `_pages/`: standalone pages, including research and software pages.
- `_posts/`: dated blog posts named `YYYY-MM-DD-title.md`.
- `_includes/` and `_layouts/`: Liquid templates and page structure.
- `assets/gitbook/custom-local.css`: local styling overrides. Research-link badges are documented in `GUIDE.md`.
- `assets/images/` and `pdf/`: site assets.
- `_config.yml`: site-wide Jekyll configuration.

## Editing conventions

- Write page content in Markdown with YAML front matter where needed.
- Preserve existing Japanese and English wording unless the requested change calls for an edit.
- Prefer changes in `custom-local.css` over edits to theme-derived assets under `assets/gitbook/`.
- Keep links and local asset paths valid for the site's root URL (`https://kampersanda.github.io/`).
- Do not commit generated output such as `_site/`.

## Local preview

Use Docker Compose for a local build and preview:

```console
docker compose build
docker compose up
```

Then open `http://localhost:4000/`. Stop the server with `docker compose down` when finished.

For content-only changes, review the Markdown and affected links even when a container runtime is unavailable.

## Change workflow

1. Branch from the latest `deploy`.
2. Make focused changes and avoid unrelated formatting churn.
3. Preview the site when practical.
4. Commit with a concise, imperative message and open a PR targeting `deploy`.
