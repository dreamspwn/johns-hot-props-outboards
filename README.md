# John's Hot Props & Outboards — Website

Simple static site. No build tools, no server required — just HTML, CSS, and
placeholder SVG images. Open `index.html` in a browser, or serve it locally
with `python3 -m http.server 8000`.

## Structure

```
index.html                 Homepage: hero, listings grid, about, contact
style.css                  Shared styles for every page
images/                    Logo, hero art, listing placeholders (all SVG placeholders — swap for real photos)
listings/                  One HTML file per outboard, e.g. yamaha-150-2023.html
```

## Adding a new listing

1. Copy an existing file in `listings/` (e.g. `listings/yamaha-150-2023.html`)
   and rename it to match the new motor, e.g. `listings/mercury-115-2020.html`.
2. Inside the new file, update:
   - `<title>` and the price in it
   - the `<h1>`, `.detail-hp`, `.desc`, and the three rows in `.spec-table`
   - the price in `.detail-card .price`
3. Add a matching card to `index.html` inside `<div class="listing-grid">` —
   copy one `<article class="listing-card">...</article>` block, update its
   text, and point `href` at your new file in `listings/`.
4. Swap `images/listing-placeholder.svg` for a real photo when you have one —
   just point the `<img src="...">` in both the card and the detail page at
   the new image file.

## Replacing placeholders

- **Logo**: replace `images/logo.svg` with a real logo (any image format —
  update the `src` in the `<header>` on every page if you change the filename).
- **Hero photo**: replace `images/hero-dock.svg` with a real dock photo.
- **Email**: currently `placeholder@johnshotprops.com` — find/replace across
  all files once you have a real one.
- **Facebook link**: currently a placeholder `#` — update the `href` in the
  contact section of `index.html` once you have a real page.

## Git workflow

```bash
git init
git add .
git commit -m "Initial site"
# create a private repo on GitHub, then:
git remote add origin <your-repo-url>
git branch -M main
git push -u origin main
```

After that, the usual loop for changes:

```bash
git add .
git commit -m "Describe the change"
git push
```
