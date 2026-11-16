# scottbrickner.github.io

Public-facing nursing education tools, served by GitHub Pages at
**https://scottbrickner.github.io/**

Each artifact is a self-contained HTML page in its own folder. Nothing is built,
bundled or compiled — what is in the repo is what is served.

## Layout

```
.
├── .nojekyll            ← stops Jekyll processing. Do not delete.
├── index.html           ← the landing page people see first
├── credits.html         ← third-party attribution
├── LICENSE
├── ecg-elements-rn/
│   └── index.html       ← ECG Element Library (RN), unbranded build
├── afrvr/
│   └── index.html       ← Microlearning example: AF with RVR
└── poaf/
    └── index.html       ← Microlearning example: preventing post-op AF (RN-PAF-03)
```

## Adding a new artifact

1. Make a folder at the repo root with a short, URL-safe, lowercase name —
   `acls-megacode`, not `ACLS Megacode (v2)`. The folder name *is* the URL.
2. Put the page inside it as **`index.html`**. That is what makes the clean URL
   `…/acls-megacode/` work instead of `…/acls-megacode/whatever.html`.
3. Open `index.html` at the repo root and copy the block between
   `<!-- ===== ARTIFACT CARD — copy from here ===== -->` and `<!-- ===== to here ===== -->`.
   Paste it below the existing card and edit the `href`, tag, title, description and date.
4. Commit. The site updates in about a minute.

## Rules that are load-bearing

- **Self-contained pages only.** Inline the CSS and JS, embed images as `data:` URIs.
  No CDN links, no Google Fonts. These pages are also used offline from a laptop at
  conferences and inside Microsoft Teams tabs, where external requests fail silently.
- **No `localStorage` or `sessionStorage`.** Same reason — a Teams tab renders the page
  in a sandboxed iframe with an opaque origin, and browser storage throws there.
- **Never rename a folder once you have shared the link.** Printed slides and QR codes do
  not update. Add a new folder instead and leave the old one in place.
- **Keep `.nojekyll`.** Without it GitHub Pages runs Jekyll and silently ignores any file
  or folder whose name starts with an underscore.
- **Check `credits.html` when adding anything with third-party content.** If a new artifact
  carries someone else's images, data or instrument, it gets an entry there before it goes up.

## Settings

GitHub Pages: **Settings → Pages → Source: Deploy from a branch → `main` / `/ (root)`**.
