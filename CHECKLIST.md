# Launch checklist

Plain-English terms and privacy on this site are **template-level basics, not legal advice**. Get a lawyer to review before you take payment.

## Done

- [x] One-page static site at the repo root (`index.html`, `styles.css`)
- [x] Relative asset paths only (safe for GitHub Pages project URL)
- [x] `.nojekyll`, `404.html`, `assets/`
- [x] Terms, privacy, and refund pages
- [x] Independent / unofficial notice in the banner and footer (no official logos)
- [x] No fake testimonials, ratings, sales counts, or urgency timers
- [x] Price is a CSS custom property: `--price` in `styles.css` (currently `$24`)
- [x] Support email used consistently: `taquino-inbox@agentmail.to`
- [x] Buy button is `BUY_URL_PLACEHOLDER` (`href="#buy"` + `is-soon` class)
- [x] Contents outline is one ordered list in `index.html` (`#contents-list`)
- [x] Sample-pages placeholder (no invented screenshots)
- [x] Original SVG handoff diagram (`assets/handoff.svg`)
- [x] Open Graph tags, meta description, SVG favicon
- [x] Semantic HTML, skip link, visible focus, system fonts, no trackers

## One-line checkout swap

When you have a Stripe Payment Link, Gumroad URL, or Lemon Squeezy URL:

1. In `index.html`, find both `BUY_URL_PLACEHOLDER` comments.
2. Set `href` to the live URL (example: `https://buy.stripe.com/...`).
3. Remove the `is-soon` class and the `aria-disabled="true"` attribute.
4. Change the button label from `Checkout opening soon` to `Buy the guide`.

That is the whole swap. Keep `#buy` as the section id so in-page links still work.

## Placeholders to fill

- [ ] Live `BUY_URL` (see swap above)
- [ ] Sample PDF page previews in the dashed placeholder on the home page
- [ ] Confirm PDF page count in copy once the manuscript is locked (now: “about 20 to 30 pages”)
- [ ] Date-stamp the “plans and pricing” chapter when those figures are checked
- [ ] `assets/og-image.png` is a generated 1200×630 card; replace if you want a tighter layout
- [ ] Optional: real PDF filename / version string once it exists

## Needs Trevor

- [ ] Create or confirm the GitHub repo and push this branch
- [ ] Enable GitHub Pages: Settings → Pages → Deploy from branch `main` (or `docs` / GitHub Actions, your choice), site URL `https://trev4ev.github.io/grokbot-guide/`
- [ ] Choose and verify the payment provider identity (Stripe / Gumroad / Lemon Squeezy) and bank payout details
- [ ] Approve the $24 price (change `--price` in `styles.css` and the SITE CONFIG comment in `index.html` if it moves)
- [ ] Confirm support email `taquino-inbox@agentmail.to` (search-replace that string if you swap)
- [ ] Legal review of terms, privacy, and refunds before charging cards
- [ ] Finish writing the PDF
