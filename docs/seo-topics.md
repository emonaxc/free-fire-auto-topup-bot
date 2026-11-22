# SEO Topics and Keyword Map

This file maps the search phrases the public documentation should cover, so every page targets one clear cluster instead of repeating the same words. Canonical site: **https://fftopup.emonaxc.com**

---

## Keyword clusters

### 1. Free Fire auto top-up bot (primary)

- free fire topup bot
- free fire auto topup bot
- ff auto top up bot
- free fire auto top up
- free fire diamond top up bot
- free fire top up in seconds
- automatic free fire topup
- fast free fire diamond topup

**Landing page:** https://fftopup.emonaxc.com

**Suggested title:** `FF Auto Topup Bot — Free Fire Diamonds in Seconds`

**Suggested description:** `Automated Free Fire diamond top-up with a Shell wallet or UniPin voucher. Orders finish in seconds, every result shows its processing time, and an API is included.`

### 2. shop.garena.my / shop.garena.sg top-up bot

- shop.garena.my topup bot
- shop garena my top up
- shop.garena.sg topup bot
- garena shop topup bot
- garena shell topup bot
- garena shell wallet topup
- free fire shell topup
- garena malaysia topup
- garena singapore topup

**Landing page:** https://fftopup.emonaxc.com/topup (Shell tab) and the docs section https://fftopup.emonaxc.com/docs#order-shell

### 3. UniPin top-up bot

- unipin topup bot
- unipin free fire topup
- unipin voucher redeem free fire
- unipin gift card free fire
- upbd voucher redeem
- bdmb voucher redeem
- free fire voucher topup
- unipin 50 diamond voucher
- unipin weekly membership voucher

**Landing page:** https://fftopup.emonaxc.com/topup (UniPin tab, default) and https://fftopup.emonaxc.com/docs#order-unipin

### 4. Indonesian shops

- bdgamesbazar topup
- bdgamesbazar free fire topup
- kiosgamer topup
- kiosgamer free fire topup
- free fire topup indonesia
- free fire level up package topup
- free fire weekly membership topup

**Landing page:** https://fftopup.emonaxc.com/docs#packages

### 5. Package and voucher long tail

- free fire 25 diamond topup
- free fire 50 diamond topup
- free fire 115 diamond topup
- free fire 240 diamond topup
- free fire 610 diamond topup
- free fire 1240 diamond topup
- free fire 2530 diamond topup
- free fire 7290 diamond topup
- free fire 36500 diamond topup
- free fire weekly lite topup
- free fire monthly membership topup

**Landing page:** the package tables in [shell-topup-bot.md](shell-topup-bot.md) and [unipin-topup-bot.md](unipin-topup-bot.md), mirrored on https://fftopup.emonaxc.com/docs#packages

### 6. Developer and API intent

- free fire topup api
- free fire topup api bangladesh
- free fire diamond api
- unipin api
- garena topup api
- free fire topup script api
- bulk free fire topup

**Landing page:** https://fftopup.emonaxc.com/docs

---

## Suggested page titles and descriptions

| Page | Title (≤ 60 chars) | Description (≤ 155 chars) |
|---|---|---|
| `/` | FF Auto Topup Bot — Free Fire Diamonds in Seconds | Automated Free Fire top-ups with a Shell wallet or UniPin voucher. Results in seconds with the exact processing time stored on every order. |
| `/topup` | Run a Free Fire Top-Up — Shell or UniPin | Enter a player ID and top up with a Garena Shell wallet or a UniPin voucher. Both bots finish in seconds. |
| `/docs` | Free Fire Top-Up API — Fields, Codes, Examples | Full request and response reference for Shell and UniPin top-ups, including status codes, error messages and example payloads. |
| `/buy-limits` | Free Fire Top-Up Pricing and Request Packs | One price per processed item, request packs of 50, 200 and 500, and direct WhatsApp contact. |

## Content angles for the repository pages

1. **"How a Free Fire auto top-up bot works"** — the four steps from player ID to credited diamonds, with no technical internals.
2. **"Shop.garena.my vs shop.garena.sg top-up"** — which shop a wallet uses and which packages each catalogue sells.
3. **"UniPin voucher prefix list for Free Fire"** — the UPBD and BDMB prefix table, explained as a reference rather than a sales page.
4. **"Free Fire top-up speed: what 0–3 seconds means"** — how processing time is measured and stored on every order.
5. **"Level Up Packages on bdgamesbazar"** — the six level packages and why they only show for a signed-in player.
6. **"Redeeming several vouchers at once"** — comma separated vouchers, per-item results.
7. **"Free Fire top-up API for sellers"** — one endpoint, JSON in and out, link to the full docs.

## Internal linking rules

- Every document links to the homepage **https://fftopup.emonaxc.com** and the docs **https://fftopup.emonaxc.com/docs** at least once.
- Link package tables to `https://fftopup.emonaxc.com/docs#packages`.
- Link Shell process text to `https://fftopup.emonaxc.com/docs#order-shell`.
- Link UniPin process text to `https://fftopup.emonaxc.com/docs#order-unipin`.
- Keep the WhatsApp link (https://wa.me/8801788623829) on pages that discuss pricing or custom plans.

## Copy rules

- One H1 per page, and the H1 contains the main phrase of that page's cluster.
- Write package names exactly as the shop lists them (`Diamond 1,060`, `Weekly Lite`, `Level Up Package — Level 6`).
- State speed as a range (`0–3 seconds`, `1–2 seconds`) and point to the stored processing time instead of promising a fixed number.
- No technical stack details, no infrastructure names, no internal automation details.
- Always add the independence disclaimer: not affiliated with Garena, Free Fire or UniPin.
