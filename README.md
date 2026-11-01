# The Unofficial Grok Bot Starter Guide

Static marketing site for an independent PDF by Trevor Aquino. Hosted on GitHub Pages.
Canonical URLs in this repo point at `https://trevoraquino.me/grokbot-guide/` (the custom
domain). **Verify that is the live address once Pages is deployed**: see "Canonical URL"
in `CHECKLIST.md`. If the live site is actually
`https://trev4ev.github.io/grokbot-guide/`, swap every canonical/`og:url`/JSON-LD URL and
`sitemap.xml`/`robots.txt` entry to that address instead.

Not affiliated with, endorsed by, or sponsored by SpaceX, xAI, or the makers of Grok Bot.

## Pages

| Page | Purpose |
| --- | --- |
| `index.html` | Home page: pitch, chapters, pricing, FAQ, buy button |
| `get-started.html` | Free SEO page: how to get started with Grok Bot |
| `pricing-explained.html` | Free SEO page: which plan includes Grok Bot, usage limits |
| `what-can-grok-bot-do.html` | Free SEO page: realistic use cases and tips |
| `terms.html` | Terms of sale |
| `privacy.html` | Privacy policy |
| `sales-policy.html` | All-sales-final policy and what to do if delivery fails |
| `404.html` | Not-found page |

## Run locally

No build step. From the repo root:

```bash
python3 -m http.server 47391
```

Open `http://127.0.0.1:47391/`.

## Edit the few things that change

| Thing | Where |
| --- | --- |
| Price | `--price` in `styles.css` (and the comment at the top of `index.html`); it also appears literally in `terms.html` and `sales-policy.html` via `<span class="price-value">` |
| Support email | `taquino-inbox@agentmail.to` (search-replace across all HTML files) |
| Buy URL | Live Stripe Payment Link, identical on every buy button across every page; see `CHECKLIST.md` to swap providers |
| Chapter list | `#contents-list` in `index.html` |
| Pricing table (tier names, prices, usage multiples) | `pricing-explained.html` (`.pricing-table`) and the "Which plan do I need" copy in `index.html`; both are labeled with the date they were checked |
| Canonical / OG / sitemap base URL | `https://trevoraquino.me/grokbot-guide/`, used in every page's `<link rel="canonical">`, `og:url`, JSON-LD, and in `sitemap.xml` |

## SEO

- Every page has a unique `<title>`, meta description, canonical URL, Open Graph tags, and
  a Twitter card.
- `index.html` carries `Product` and `FAQPage` JSON-LD (the FAQ JSON-LD mirrors the visible
  FAQ `<details>` content). The subpages carry `BreadcrumbList` JSON-LD matching their
  visible breadcrumb.
- `sitemap.xml` lists every indexable page. `robots.txt` allows everything except
  `assets/og-card.html` (an internal OG-image template, not a real page) and points at the
  sitemap.
- `assets/og-image.png` is a 1200x630 PNG rendered from `assets/og-card.html`. If you change
  the title/price text in `og-card.html`, re-render it (for example with headless Chrome:
  `google-chrome --headless --disable-gpu --no-sandbox --window-size=1200,630
  --screenshot=assets/og-image.png file://$(pwd)/assets/og-card.html`) and replace the PNG.

## Files

See `CHECKLIST.md` for launch status and what still needs a human.
