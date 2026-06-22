# 🌸 FloraClaw — Ovulation & Fertility Calculator

A clean, private, single-file ovulation and fertile window calculator. Zero backend, zero data collection, zero tracking. Built by FloraClaw.

---

## Live Preview

Deploy `index.html` to any static host. Suggested domains:

| Domain | Notes |
|---|---|
| `ovulationcalc.com` | Canonical target (set in `<link rel="canonical">`) |
| `fertilitytracker.app` | App-style positioning |
| `mycycletracker.com` | Broad cycle-tracking angle |
| `ovulationwindow.com` | Keyword-rich, descriptive |
| `fertiledays.co` | Short, modern, niche |

---

## Features

| Feature | Details |
|---|---|
| **LMP date picker** | Defaults to today; fully editable |
| **Cycle length slider** | 21–35 days, default 28 |
| **2-month visual calendar** | LMP month + following month |
| **Period days** | Days 1–5 highlighted in rose red |
| **Fertile window** | 5 days before ovulation in light green |
| **Peak ovulation** | Bright emerald + ★ star badge |
| **Next period** | First day highlighted with pink border |
| **Today indicator** | Purple ring outline |
| **Summary panel** | Plain-language fertile window, ovulation, and next-period dates |
| **Calendar legend** | Color key always visible |
| **Privacy banner** | Persistent top-of-page notice |
| **Medical disclaimer** | Amber callout |
| **Privacy policy** | Full section at page bottom |
| **Affiliate section** | 3 Amazon Associates placeholder links |
| **AdSense placeholders** | 2 commented-out ad slots (top + mid) |

---

## Fertility Calculation Method

Standard **luteal-phase** formula (used by most OB/GYN references):

```
Ovulation Date   = LMP + (cycle_length − 14) days
Fertile Window   = Ovulation − 5 days  →  Ovulation day (inclusive)
Period Days      = LMP day 1 through day 5
Next Period      = LMP + cycle_length
```

Example — 28-day cycle starting June 1:
- Ovulation: June 15 (June 1 + 14)
- Fertile window: June 10–15
- Next period: June 29

---

## Monetization Setup

### AdSense
Two commented-out `<ins class="adsbygoogle">` slots exist in the HTML:
1. **Top banner** — above the input card
2. **Mid content** — between the legend and affiliate section

To activate:
1. Uncomment the `<!-- ... -->` blocks
2. Replace `ca-pub-XXXXXXXXXXXXXXXX` with your publisher ID
3. Replace slot IDs `1111111111` / `2222222222` with real slot numbers
4. Add the AdSense `<script>` loader in `<head>`

### Amazon Associates
Three affiliate `<a>` tags in the "Fertility Essentials" section. To activate:
1. Replace `YOUR-AFFILIATE-TAG-20` with your Associates tracking ID in all three links
2. Optionally replace the `dp/BXXXXXXX` ASINs with specific products you've verified

Current placeholder ASINs (verify before going live):
| Product | Placeholder ASIN |
|---|---|
| Ovulation test strips | B07D3YJLK6 |
| Prenatal vitamins | B002RL8FCU |
| BBT thermometer | B004ZFUK5G |

---

## Deployment

### Netlify Drop
1. Drag `index.html` to [netlify.com/drop](https://app.netlify.com/drop)
2. Custom domain → point `ovulationcalc.com` DNS to Netlify

### GitHub Pages
```bash
git init
git add index.html
git commit -m "Initial FloraClaw build"
gh repo create ovulationcalc --public
git push -u origin main
# Enable Pages in repo Settings → Pages → main / root
```

### Cloudflare Pages
```bash
npx wrangler pages deploy . --project-name ovulationcalc
```

---

## SEO Notes

- `<title>` and `<meta description>` are pre-filled with target keywords
- `<link rel="canonical">` points to `https://ovulationcalc.com` — update if deploying elsewhere
- No JS frameworks = fast FCP/LCP scores
- Semantic HTML5 headings (`h1` → `h2` → `h3`) for crawlability
- All page content renders without JavaScript (inputs only need JS for calculation)

---

## Privacy

This tool intentionally:
- Makes **zero network requests** after page load
- Sets **no cookies**
- Loads **no analytics**
- Stores **no data** (no `localStorage`, no `sessionStorage`)
- Works **fully offline** once cached

Suitable for posting a HIPAA-adjacent "no PHI collected" disclosure.

---

## File Structure

```
floraclaw/
├── index.html   ← entire app (HTML + CSS + JS, single file)
└── README.md    ← this file
```

---

## Tech Stack

| Layer | Choice |
|---|---|
| HTML | Semantic HTML5 |
| CSS | Custom properties + Tailwind CDN utility helpers |
| JS | Vanilla ES6+ (no frameworks, no bundler) |
| Fonts | System font stack (no Google Fonts request) |
| Icons | Emoji (no icon library CDN) |

---

*Built by FloraClaw — privacy-first web tools for health.*
