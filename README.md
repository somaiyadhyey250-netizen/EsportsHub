# Esport Hub — Gaming Tournament Management Portal

Vanilla HTML/CSS/JS + Bootstrap 5. No build step, but it needs a local web server (ES modules don't load from `file://`).

## Run
    python3 -m http.server 8000      # then open http://localhost:8000
or use the VS Code "Live Server" extension on `index.html`.

## Demo accounts (frontend prototype — localStorage auth is NOT secure)
- Admin:  admin@esporthub.demo / Admin@123
- Player: use "Fill player" on the login page (password Player@123)

## Data flow
`js/data.js` (seed) → `initializeData()` → localStorage → every page reads/writes via `js/storage.js`.
Reset everything: Admin → Settings → "Reset demo data" (or clear the `esporthub_*` keys).

## Where things live
- `js/scoring.js` — ALL scoring rules + point maths (placeholder values until final rules are set)
- `js/storage.js` — only file that touches localStorage
- `js/paths.js` — site-root aware links, so nested folders just work
- `js/layout.js` — navbar, footer, dashboard sidebar
- `js/pages/*.js` — one renderer per page (`home`, `public`, `shell`)
- `tools/build_pages.py` regenerates the HTML wrappers · `tools/make_assets.py` regenerates demo SVGs
