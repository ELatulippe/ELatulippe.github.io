# Personal academic website

Plain HTML + CSS. No build step, no Jekyll, no dependencies — GitHub Pages serves it as-is.

```
index.html        Research page (bio, JMP, working papers, publications, WIP)
teaching.html     Teaching page
cv.html           CV page (embeds files/cv.pdf)
assets/style.css  All styling
files/            PDFs and your headshot
```

## Putting it online

1. Create a public repo named exactly `<your-github-username>.github.io`.
2. Drop these files in the repo root (not in a subfolder) and push:

```bash
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/<username>/<username>.github.io.git
git push -u origin main
```

3. Repo → **Settings** → **Pages** → Source: *Deploy from a branch*, Branch: `main`, folder `/ (root)`.
4. Wait a minute or two, then visit `https://<username>.github.io`.

Every later `git push` redeploys automatically.

## Editing

- Replace `Etienne [Last Name]`, the email, and the address — they appear in the header and sidebar of each page.
- Put your headshot at `files/headshot.jpg` (square-ish, ~600px wide is plenty). If you use a `.png`, update the `src` in all three pages.
- Papers are `<div class="paper">` blocks. Copy one, edit the fields, delete the lines you don't need (`.authors`, `.outlet`, `.filelinks`, `<details>`).
- Abstracts are `<details>` elements — they collapse and expand with no JavaScript.
- Colours, fonts, and column widths live in the `:root` block at the top of `assets/style.css`.
- Adding a page: copy `teaching.html`, rename it, and add a link in the `<nav>` of every page.

## Local preview

```bash
python3 -m http.server 8000
```

Then open `http://localhost:8000`.
