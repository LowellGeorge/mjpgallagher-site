---
name: add-bookshelf-book
description: Add a book to a topic category on bookshelf.html (mjpgallagher.com). Use when Mike wants to add a recommendation to his bookshelf, e.g. "add The Model Thinker by Scott Page to my Thinking Tools bookshelf category".
---

# Add a book to the bookshelf

Adds a correctly formatted `<li>` to a topic category in `bookshelf.html`. Read `CLAUDE.md` for the canonical entry format before editing.

## Inputs
- **Title** (required)
- **Author** (optional — some bookshelf entries are title-only)
- **Category** (required — which topic section, e.g. "Thinking Tools / Learning How to Learn")

If the category isn't given or is ambiguous, list the existing `<h2>` category headings and ask Mike which one (or whether to create a new category).

## Entry format
Bookshelf entries are **not** linked (unlike reading.html).
- With author:
  ```html
                <li>Title, <em>Author</em></li>
  ```
  Title plain text, author in `<em>` italics, `, ` separator.
- Title only (no author):
  ```html
                <li>Title</li>
  ```
- Indentation is 16 spaces (matches surrounding `<li>` lines).

## Steps
1. Categories are `<div class="category-section">` blocks, each with a numbered `<h2>` (e.g. `2. America & Growth`) and an `<ol>`. Find the one matching the requested category.
2. Append the new `<li>` to the **end** of that category's `<ol>` (the bookshelf is a curated collection, not chronological).
3. If creating a new category, add a new `<div class="category-section">` with the next sequential number in its `<h2>`, placed in a sensible spot, and ask Mike where if unsure.
4. After editing, confirm the change to Mike, then ask whether to commit & push (push to `main` auto-deploys via GitHub Pages — see `CLAUDE.md`). Use a commit message like `Add <Title> to <category> bookshelf`.

## Don't
- Don't add an Amazon link (bookshelf entries are plain text).
- Don't reorder or reformat other entries, and don't touch the footer.
