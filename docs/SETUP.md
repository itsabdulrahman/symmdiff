# Deploying the SymmDiff project page

This folder is the **website only** — designed to drop into your existing
[`itsabdulrahman/symmdiff`](https://github.com/itsabdulrahman/symmdiff) repository
alongside your existing README and code.

```
.
├── index.html                       # the project page
└── static/
    ├── css/index.css                # styling
    ├── js/index.js                  # BibTeX copy button
    └── figures/
        ├── pipeline.svg             # Figure 1
        └── qualitative.svg          # Figure 2
```

The page is a single self-contained HTML file with no build step. Fonts come from Google
Fonts (Fraunces + Manrope + JetBrains Mono); no other external dependencies.

---

## 1. Drop into your existing repo

Recommended layout: put the page in a `docs/` subfolder so it lives next to (not on top of)
your README and code:

```bash
# from the root of your symmdiff repo
mkdir -p docs
# copy the contents of this folder INTO docs/
cp index.html docs/
cp -r static docs/

git add docs/
git commit -m "Add MICCAI 2026 project page"
git push
```

Then on GitHub: **Settings → Pages → Source = Deploy from a branch → Branch = `main` /
`docs`** → Save. Wait ~1 minute. Your site goes live at:

> **https://itsabdulrahman.github.io/symmdiff/**

> If you'd rather have the page at the repo root, just copy `index.html` and `static/` to
> the repo root (not `docs/`) and set Pages source to `/(root)`. Either works — `docs/` is
> just tidier because it doesn't pollute the root listing.

---

## 2. Things you need to edit before going live

Open `index.html` and search for these placeholders:

| Where                                  | What to put there                                          |
| -------------------------------------- | ---------------------------------------------------------- |
| `<!-- AUTHORS — fill in once de-anonymized -->` | Real author list + superscript affiliations       |
| `.affiliations`                        | Real affiliations + corresponding-author email             |
| `.actions` → 1st `<a href="#">` (Paper) | arXiv or MICCAI proceedings URL                           |
| `.actions` → 3rd `<a href="#">` (Dataset) | Dataset URL, or remove the button if not releasing data  |
| `#bibtex-block`                        | Final BibTeX once proceedings are out                      |
| `<meta name="author">`                 | Real author string (for SEO / sharing)                     |

The **Code** button and footer **GitHub** link are already pointing at
`https://github.com/itsabdulrahman/symmdiff` so you don't need to touch those.

**Favicon** — drop a 32 × 32 or 64 × 64 PNG at `static/figures/favicon.png` and add
inside `<head>` of `index.html`:

```html
<link rel="icon" type="image/png" href="static/figures/favicon.png" />
```

---

## 3. Preview locally

```bash
# From inside this folder (or docs/ once you've moved it)
python -m http.server 8000
# then open http://localhost:8000 in a browser
```

---

## 4. Customizing the design

All design tokens live at the top of `static/css/index.css`:

```css
:root {
  --paper:   #FAF7F2;   /* page background          */
  --ink:     #14181F;   /* primary text             */
  --accent:  #C04A3C;   /* coral accent (heatmap red) */
  --teal:    #1F5862;   /* secondary accent         */
  /* ... */
}
```

- **Dark theme?** Swap `--paper` for `#0E1116` and `--ink` for `#EFE9DA`.
- **Different accent?** Change `--accent` and `--accent-soft` only — everything else cascades.
- **Add a section?** Copy any `<section class="section">` block and bump the `.num` badge.
- **Hide the symmetry axis?** Set `display: none;` on `.symmetry-axis` in CSS.

---

## 5. Pre-launch checklist

- [ ] Author names and affiliations replaced
- [ ] Paper URL filled in (the first `<a>` in `.actions`)
- [ ] Dataset URL filled in, or that button removed
- [ ] Final BibTeX inside `#bibtex-block`
- [ ] Favicon dropped and linked in `<head>`
- [ ] Open Graph `<meta>` reviewed (for link previews on Twitter / Slack / LinkedIn)
- [ ] Tested on mobile (everything stacks below 900 px / 640 px)
- [ ] Pages enabled in repo Settings, site loads at `https://itsabdulrahman.github.io/symmdiff/`
