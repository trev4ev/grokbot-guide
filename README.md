# The Grok Bot Starter Guide

Static marketing site for an independent PDF by Trevor Aquino. Hosted on GitHub Pages at [https://trev4ev.github.io/grokbot-guide/](https://trev4ev.github.io/grokbot-guide/).

Not affiliated with, endorsed by, or sponsored by SpaceX, xAI, or the makers of Grok Bot.

## Run locally

No build step. From the repo root:

```bash
python3 -m http.server 47391
```

Open `http://127.0.0.1:47391/`.

## Edit the few things that change

| Thing | Where |
| --- | --- |
| Price | `--price` in `styles.css` (and the comment at the top of `index.html`) |
| Support email | `taquino-inbox@agentmail.to` (search-replace) |
| Buy URL | Live Stripe Payment Link in `index.html` ($24, card only for now; see `CHECKLIST.md` to swap providers) |
| Chapter list | `#contents-list` in `index.html` |

## Files

See `CHECKLIST.md` for launch status and what still needs a human.
