# mjpgallagher.com

Personal website hosted on GitHub Pages via the `LowellGeorge/mjpgallagher-site` repo. Custom domain: mjpgallagher.com.

## Structure

- `index.html` — About page
- `reading.html` — Reading list by year (2026 back to 2019). Each book is an `<li>` with an Amazon UK search link, italicised title, and author.
- `bookshelf.html` — Bookshelf page
- `lists-sources.html` — Lists / Sources page
- `ai-101.html` — AI 101 page
- `styles.css` — Shared stylesheet (system font stack, 800px max-width, minimal design)
- `CNAME` — Custom domain config

## Conventions

- All pages share the same `<header>` with nav links; the current page gets `class="active"`.
- Book links on reading.html use Amazon UK search URLs: `https://www.amazon.co.uk/s?k=Title+Author`
- Books are listed in numbered `<ol>` lists inside `<div class="year-section">` blocks.
- Rereads are marked with `(rr)` after the entry.

## Deployment

Push to `main` and GitHub Pages deploys automatically. Allow a minute or two for changes to go live.
