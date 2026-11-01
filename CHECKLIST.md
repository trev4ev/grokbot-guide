# Launch checklist

Plain-English terms and privacy on this site are **template-level basics, not legal advice**. Get a lawyer to review before you take payment.

## Done

- [x] Home page plus three free SEO pages at the repo root (`get-started.html`,
      `pricing-explained.html`, `what-can-grok-bot-do.html`)
- [x] Relative asset paths only (safe for GitHub Pages project URL)
- [x] `.nojekyll`, `404.html`, `assets/`, `sitemap.xml`, `robots.txt`
- [x] Terms, privacy, and sales-policy pages (`sales-policy.html` replaces the old
      `refund.html`; it states all sales are final and covers delivery problems only)
- [x] Independent / unofficial notice in the banner and footer on every page (no official
      logos)
- [x] No fake testimonials, ratings, sales counts, or urgency timers
- [x] No refund or money-back wording anywhere on the site; every buy button has the price
      and an "all sales are final" line next to it (`.sales-final`)
- [x] Price is a CSS custom property: `--price` in `styles.css` (currently `$24`)
- [x] Support email used consistently: `taquino-inbox@agentmail.to`
- [x] Buy button is wired to a live Stripe Payment Link ($24, card only for now), identical
      `href` on every instance across every page
- [x] Delivery copy matches the real flow everywhere: redirect straight to the PDF download
      page, plus a separate automatic email from `taquino-inbox@agentmail.to` with the same
      link. Nowhere claims Stripe's confirmation/receipt carries the download link.
- [x] Contents outline is one ordered list in `index.html` (`#contents-list`), matching the
      guide's real five chapters
- [x] Sample-pages placeholder (no invented screenshots); `assets/handoff.svg` left
      untouched per the designer's request
- [x] Original SVG handoff diagram (`assets/handoff.svg`)
- [x] Unique `<title>` and meta description per page, canonical URLs, Open Graph tags,
      Twitter cards, `Product` + `FAQPage` JSON-LD on the home page, `BreadcrumbList`
      JSON-LD on every subpage, `sitemap.xml`, `robots.txt`
- [x] Semantic HTML, skip link, visible focus, system fonts, no trackers
- [x] `assets/og-image.png` regenerated (1200x630) to match the current title and price
- [x] Chapter 2 is titled "Using more than one bot" and chapter 4 "Pricing, usage and what
      'included' means" everywhere they are named (contents list, SITE CONFIG comment, and
      the two subpages that reference them); chapter scope is unchanged
- [x] `Product` JSON-LD `description` on `index.html` uses the longer product description
      provided for that field specifically; page `<meta name="description">`/OG/Twitter
      tags keep their own short, page-specific, SEO-length copy
- [x] Final PDF page count (26) stated in hero, home meta/OG/Twitter, Product JSON-LD,
      FAQ (visible + JSON-LD), price notes, and other beginner-facing product copy

## Canonical URL: verify once Pages is live

Canonical links, `og:url`, JSON-LD `url`/`item` fields, and `sitemap.xml` all currently use
`https://trevoraquino.me/grokbot-guide/` because the brief says the live site will use that
custom domain. **This has not been verified against an actual deployed GitHub Pages site.**

Once GitHub Pages is live:

1. Load the real site and confirm its address.
2. If it is `https://trevoraquino.me/grokbot-guide/`, no change needed.
3. If it is instead `https://trev4ev.github.io/grokbot-guide/` (no custom domain
   configured), replace every `https://trevoraquino.me/grokbot-guide/` occurrence with
   `https://trev4ev.github.io/grokbot-guide/` in: every page's `<link rel="canonical">`,
   every `og:url` and `og:image` meta tag, every JSON-LD `url`/`image`/`item` field, and
   every `<loc>` in `sitemap.xml`.
4. If a custom domain is configured, add a `CNAME` file at the repo root with the domain
   name, per GitHub Pages' custom-domain setup. This repo does not currently include one.

## One-line checkout swap

Current status: wired to a live Stripe Payment Link, $24, card only for now
(`https://buy.stripe.com/14A6oI05U7hmfUZ0LU9EI00`), identical on every buy button on every
page (`index.html`, `get-started.html`, `pricing-explained.html`,
`what-can-grok-bot-do.html`).

To point the buy buttons at a different Stripe Payment Link, Gumroad URL, or Lemon
Squeezy URL later:

1. In each of the four pages above, find the buy-button comment right above each
   `<a class="btn btn-primary">` link, and the `BUY_URL` line in `index.html`'s SITE CONFIG
   comment.
2. Set each `href` (and the SITE CONFIG comment) to the new URL.
3. Keep the `target="_blank"` and `rel="noopener"` attributes, and keep the label
   `Buy the guide`.
4. Update this checklist and `README.md` with the new provider and price if either
   changes.

That is the whole swap. Keep `#buy` as the section id on `index.html` so in-page links
still work.

## New markup hooks for the designer (this PR)

Added at the designer's request so styling can be layered on without further structural
changes. Full list, with where each one lives:

| Hook | Where | Purpose |
| --- | --- | --- |
| `.sales-final` | Next to/under every buy button, on `index.html` and the three new pages | The all-sales-final line required next to every buy button |
| `<strong class="disclosure-label">` | Inside the existing `.notice` banner, every page that has one | Labels the disclosure banner |
| `.section-head` | Wraps each `<section>`'s `h2` (plus its intro paragraph, if any) on `index.html` and the three new pages. Not used on the legal pages (`terms.html`, `privacy.html`, `sales-policy.html`), which use a flat heading structure with no discrete `<section>` per topic | Groups a section's heading and lede for styling |
| `.prompt` (on `<pre class="prompt"><code>...</code></pre>`) | `get-started.html`, `what-can-grok-bot-do.html` | Example prompt blocks |
| `.price-note` | Under each price display, on `index.html`'s Price section and the `.cta-buy` block on the three new pages | The note line under a price figure |
| `.meta` (also used as a class on `<time>` elements with a `datetime` attribute) | Every "checked on [date]" note, including the footer disclaimer and the pricing page | Date-stamped facts |
| `.breadcrumbs` / `.breadcrumb-list` | Below the notice banner on every subpage (`privacy.html`, `terms.html`, `sales-policy.html`, `get-started.html`, `pricing-explained.html`, `what-can-grok-bot-do.html`) | Breadcrumb nav |
| `.outcomes` | `index.html`, the "What you'll be able to do" list | The outcomes/benefits list |
| `.related-links` | Internal "keep reading" link lists on `index.html` and the three new pages | Cross-page link lists |
| `.cta-buy` | Wraps the condensed buy block (price, price-note, sales-final, button) at the bottom of the three new pages | Soft-CTA container |
| `.pricing-table` | The plan comparison `<table>` on `pricing-explained.html` | Pricing table |

Also per the designer's request:

- The `.mark-icon` `<img>` was removed from the header on every page; the wordmark is text
  only now (`<a class="mark">The Unofficial Grok Bot Starter Guide</a>`).
- Every page now uses a single `.wrap` container; the `.wrap.narrow` variant was dropped
  everywhere (it was only ever used on two sections of `index.html`). No page currently
  needs a narrower wrapper, since the legal pages already relied on `.legal-page p`/`.legal-page li`
  CSS max-width instead of the wrapper class.
- `assets/handoff.svg` and its `<img>`/`<figure>` reference in `index.html` were left
  completely untouched.

## Page count: 26 (final)

The guide is locked at **26 pages**. That number is stated in beginner-facing product
copy, and the visible FAQ text matches the FAQ JSON-LD.

Where it appears:

- Home hero kicker and byline (`index.html`)
- Home `<meta name="description">`, `og:description`, and `twitter:description`
- `Product` JSON-LD `description` on `index.html`
- FAQ "What format is it?" (visible `<details>` and matching JSON-LD answer)
- `.price-note` under every price display (`index.html` and the three SEO pages)
- "What you get" on the home page
- CTA intros on `get-started.html`, `pricing-explained.html`, and
  `what-can-grok-bot-do.html`
- Terms product paragraph (`terms.html`)

Where it does not appear (on purpose):

- Chapter titles and chapter list (unchanged)
- Price, buy URL, the "all sales are final" line, and the independent/unofficial
  disclosure
- `assets/og-image.png` / `assets/og-card.html` (the card has no page count; leave it)
- SEO-page meta/OG/Twitter tags (those describe the free articles, not the PDF length)
- The "one-page checklist" phrase in chapter 5 (that is a chapter feature, not the PDF
  length)

## Placeholders to fill

- [ ] Sample PDF page previews in the dashed placeholder on the home page
- [x] Final PDF page count: 26 pages (see "Page count: 26 (final)" above)
- [ ] Optional: real PDF filename / version string once it exists
- [ ] If the Grok Bot pricing figures change before launch, update the tier table in
      `pricing-explained.html`, the "Which plan do I need" FAQ answer and JSON-LD in
      `index.html`, and the date stamp (currently October 31, 2026) in all of the above plus
      every footer

## Needs Trevor

- [ ] Create or confirm the GitHub repo and push this branch
- [ ] Enable GitHub Pages: Settings → Pages → Deploy from branch `main` (or `docs` /
      GitHub Actions, your choice)
- [ ] Confirm the live site address and do the canonical-URL check above
- [ ] If using the custom domain, add a `CNAME` file and configure DNS per GitHub's docs
- [ ] Confirm the Stripe account's bank payout details (provider is already chosen and
      live: Stripe)
- [ ] Approve the $24 price (change `--price` in `styles.css` if it moves, and the other
      spots listed in the README's "Edit the few things that change" table)
- [ ] Confirm support email `taquino-inbox@agentmail.to` (search-replace that string if you
      swap)
- [ ] Legal review of terms, privacy, and the sales policy before charging cards
- [ ] Finish writing the PDF

## Verification run for this change (local)

- Served the site with `python3 -m http.server` and confirmed all eight pages return 200:
  `index.html`, `get-started.html`, `pricing-explained.html`, `what-can-grok-bot-do.html`,
  `terms.html`, `privacy.html`, `sales-policy.html`, `404.html`.
- Checked every internal `href`/`src` resolves to a real file; no links to the deleted
  `refund.html` remain.
- Confirmed `sitemap.xml` lists every indexable page and no others.
- Validated both JSON-LD blocks on `index.html` as JSON and diffed the FAQ JSON-LD text
  against the visible `<details>` content (including the 26-page format answer); confirmed
  each subpage's `BreadcrumbList` JSON-LD matches its visible breadcrumb.
- Ran axe-core against all eight pages.
- Grepped the whole repo for em dashes, en dashes, "refund", "money back", "guarantee",
  "10x", and `BUY_URL_PLACEHOLDER`: no unexpected matches.
- Confirmed the buy button `href` is byte-identical
  (`https://buy.stripe.com/14A6oI05U7hmfUZ0LU9EI00`) on every instance across every page.
- Confirmed "26-page" / "26 pages" appears only in the copy listed under "Page count: 26
  (final)", and that price, buy URL, sales-final lines, and the unofficial disclosure
  were not changed.
