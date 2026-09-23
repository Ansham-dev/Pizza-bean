# PIZZA BEAN 🍕

Static sample restaurant website (client demo). No backend needed — open and show.

Live file: `index.html`

## Files
- `index.html` — main site (menu rendered from `MENU_DATA` in-page, edit data not HTML)
- `Style.css` — custom styles (w3.css + font via CDN)
- `homescreen.png` — hero/header background
- `Menu.jpg` — chef image
- `header.png` — logo / restaurant image

## How clients customize (3 minutes)
1. `SITE_CONFIG` at bottom of `index.html` — email, phone, restaurant name.
2. `MENU_DATA` — pizza/pasta/starter items, prices, tags.
3. Images — replace `homescreen.png` / `Menu.jpg` / `header.png`, keep names.

## Contact form (static demo)
No server. Submit shows a booking summary, then the visitor taps to send via email app (or calls).
Paid upgrade path is commented in code: POST to Formspree/Google Form.

## Cart (static demo)
Every dish has ADD +. Navbar CART (desktop + mobile menu) opens a slide-in drawer:
quantities, totals in ₹, saved in `localStorage`, checkout via name/phone,
order sent through email app. No backend.

## Excluded (not pushed)
- `PIZZA BEAN.zip` — backup archive
- `언어/` — unrelated files
- `OUTPUT.jpeg` — unused image

## Run locally
Open `index.html` in a browser, or: `python -m http.server` in this folder.

## GitHub Pages
Settings → Pages → Deploy from branch → `main` → `/ (root)`. Site serves `index.html`.
