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
- [x] Buy button is wired to a live Stripe Payment Link ($24, card only for now)
- [x] Contents outline is one ordered list in `index.html` (`#contents-list`)
- [x] Sample-pages placeholder (no invented screenshots)
- [x] Original SVG handoff diagram (`assets/handoff.svg`)
- [x] Open Graph tags, meta description, SVG favicon
- [x] Semantic HTML, skip link, visible focus, system fonts, no trackers

## One-line checkout swap

Current status: wired to a live Stripe Payment Link, $24, card only for now
(`https://buy.stripe.com/14A6oI05U7hmfUZ0LU9EI00`).

To point the buy buttons at a different Stripe Payment Link, Gumroad URL, or Lemon
Squeezy URL later:

1. In `index.html`, find the `BUY_URL` line in the SITE CONFIG comment and the two
   buy-button comments right above each `<a class="btn btn-primary">` link.
2. Set each `href` (and the SITE CONFIG comment) to the new URL.
3. Keep the `target="_blank"` and `rel="noopener"` attributes, and keep the label
   `Buy the guide`.
4. Update this checklist and `README.md` with the new provider and price if either
   changes.

That is the whole swap. Keep `#buy` as the section id so in-page links still work.

## Placeholders to fill

- [ ] Sample PDF page previews in the dashed placeholder on the home page
- [ ] Confirm PDF page count in copy once the manuscript is locked (now: “about 20 to 30 pages”)
- [ ] Date-stamp the “plans and pricing” chapter when those figures are checked
- [ ] `assets/og-image.png` is a generated 1200×630 card; replace if you want a tighter layout
- [ ] Optional: real PDF filename / version string once it exists

## Needs Trevor

- [ ] Create or confirm the GitHub repo and push this branch
- [ ] Enable GitHub Pages: Settings → Pages → Deploy from branch `main` (or `docs` / GitHub Actions, your choice), site URL `https://trev4ev.github.io/grokbot-guide/`
- [ ] Confirm the Stripe account's bank payout details (provider is already chosen and live: Stripe)
- [ ] Approve the $24 price (change `--price` in `styles.css` and the SITE CONFIG comment in `index.html` if it moves)
- [ ] Confirm support email `taquino-inbox@agentmail.to` (search-replace that string if you swap)
- [ ] Legal review of terms, privacy, and refunds before charging cards
- [ ] Finish writing the PDF
