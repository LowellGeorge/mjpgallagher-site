---
name: add-reading-book
description: Add a book to the reading list on reading.html (mjpgallagher.com). Use when Mike wants to log a book he's read, e.g. "add Leviathan Wakes by James S. A. Corey to my 2026 reading list" or "log that I just finished X by Y".
---

# Add a book to the reading list

Adds a correctly formatted `<li>` to `reading.html`. Read `CLAUDE.md` for the canonical entry format before editing.

## Inputs
- **Title** (required)
- **Author** (required)
- **Year** (optional — default to the current year)
- **Reread?** (optional — if yes, the entry gets a trailing ` (rr)`)

If the title or author is ambiguous, confirm with Mike before writing. Do not invent an author.

## Entry format
```html
                <li><a href="AMAZON_URL">Title</a>, <em>Author</em></li>
```
- Title is **plain text** inside the link; author is in **`<em>` italics**; separator is `, ` (comma, no dash).
- Reread → put ` (rr)` immediately before `</li>`, **outside** the `<em>`: `…<em>Author</em> (rr)</li>`.
- Indentation is 16 spaces (matches surrounding `<li>` lines).

## Building the Amazon URL
Base: `https://www.amazon.co.uk/s?k=`
Then append the title words followed by the author words, all joined by `+`:
1. Take `"Title Author"`.
2. Strip punctuation (`. ? : , ! ' " & ( )` etc.) — keep only letters, digits, spaces.
3. Collapse whitespace and replace each space with `+`.

Examples (from the live site):
- *What Is Life?* by Addy Pross → `…s?k=What+is+Life+Addy+Pross`
- *Leviathan Wakes* by James S. A. Corey → `…s?k=Leviathan+Wakes+James+S+A+Corey`

## Steps
1. Determine the target year (default current year). In `reading.html`, find the `<div class="year-section">` whose `<h3>` is that year.
2. **If that year section exists:** insert the new `<li>` as the **first** entry in that section's `<ol>` (newest-first ordering — the most recently read book sits at the top).
3. **If the year does not exist yet** (new year): add a new `<div class="year-section">` with `<h3>YEAR</h3>` and an `<ol>` containing the entry, placed **above** the most recent existing year section (years run newest → oldest down the page).
4. After editing, confirm the change to Mike, then ask whether to commit & push (push to `main` auto-deploys via GitHub Pages — see `CLAUDE.md`). Use a commit message like `Add <Title> to <year> reading list`.

## Don't
- Don't reorder or reformat other entries.
- Don't add a copyright line or alter the footer.
