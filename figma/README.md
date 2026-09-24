# PIZZA BEAN — Figma mockup (scroll pizza docks per section)

Import-ready for Figma. No plugin needed.

## 1. Import
1. Open Figma → New file → drag in `figma/pizza.svg` (it becomes a component).
2. Create 4 frames, all 1440 × 900, named exactly:
   - `01-Home`
   - `02-Menu`
   - `03-About`
   - `04-Contact`
3. Duplicate the pizza component into each frame (so Smart Animate can match it — keep same layer name `traveler-pizza`).

## 2. Pizza placements (matches live site e9a3759)
Use these X/Y (top-left of pizza layer), size 300 × 300, rotation 0 for mockup base:

| Frame | Pizza X | Pizza Y | Side | Opacity | Note |
|-------|---------|---------|------|---------|------|
| 01-Home | 900 | 250 | right-hero | 100% | big hero version: scale to 540px for hero, centered in right column |
| 02-Menu | 1010 | 300 | right-dock | 92% | 300px, floats over gutter right of menu card |
| 03-About | 130 | 320 | left-dock | 92% | 315px (scale 1.05), floats over left gutter |
| 04-Contact | 1010 | 310 | right-dock | 92% | 300px, floats over right gutter |

Backgrounds to match site:
- Home: #0E0C0A with radial cheese glow right
- Menu: #0E0C0A, card #FFFDF7 centered 980px
- About: gradient #7A1A0E → #B81E0E
- Contact: gradient #121A22 → #0E0C0A, card #FFFDF7

Keep all text/content centered max 980px so side gutters stay clear for pizza.

## 3. Prototype (Smart Animate the travel)
1. Prototype tab → connect `01-Home` → `02-Menu` → `03-About` → `04-Contact` with:
   - Interaction: On scroll / While scrolling is not in Figma — simulate with On click + Smart Animate, or use Scroll To.
   - Better: set Overflow behavior → Vertical scrolling on a single long frame `00-LongPage` (1440 × 3600) stacking all 4 sections vertically, pizza layer Fixed + Manual offset per section stop.
2. For demo: select pizza in 01 → After Delay 0.4s → Navigate to 02 with Smart Animate, Ease In Out 600ms, rotate + move. Repeat per frame.
3. Rotation in Figma: set pizza rotation 0° → 45° → -30° → 30° across frames to fake scroll-spin. Live code does `rotate = scrollY * 0.25` + constant 16s spin.

## 4. Live code mapping
- `figma/pizza.svg` = `#scroll-follower` inner SVG
- Hero big pizza = `#heroPizza` in index.html (540px)
- Travel logic = `computeTargets()` stops: Menu-right, About-left, Contact-right
- Motion = rAF ease 0.07 + bob `sin(t*1.6)*14px` + tilt on direction change

Say `push` and I’ll push this figma/ folder.
