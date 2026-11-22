# FF Auto Top-Up Bot — Free Fire Diamonds in Seconds

**FF Top-Up** is an automated Free Fire top-up service with two bots: a **Shell wallet bot** that buys diamonds directly on the Garena shop, and a **UniPin bot** that redeems a gift card or voucher you already own. Both finish a normal order in seconds and show the exact processing time on every result.

- Website: **https://fftopup.emonaxc.com**
- Run a top-up: **https://fftopup.emonaxc.com/topup**
- API and usage docs: **https://fftopup.emonaxc.com/docs**
- Request packs and pricing: **https://fftopup.emonaxc.com/buy-limits**
- WhatsApp: **https://wa.me/8801788623829**

This repository is a public documentation mirror. It explains the process, the supported shops and packages, and the top-up speed, so players and sellers can find the service when searching for a Free Fire auto top-up bot.

---

## Contents

1. [What it does](#what-it-does)
2. [Two bots, one account](#two-bots-one-account)
3. [Top-up speed](#top-up-speed)
4. [Supported shops and servers](#supported-shops-and-servers)
5. [Supported packages](#supported-packages)
6. [How a top-up works](#how-a-top-up-works)
7. [Website and account features](#website-and-account-features)
8. [Pricing and request limits](#pricing-and-request-limits)
9. [Frequently asked questions](#frequently-asked-questions)
10. [Links](#links)

---

## What it does

You send a Free Fire player ID. The bot handles the rest:

- **Shell bot** — signs into a Garena Shell wallet, checks out the diamond or membership package you picked on the shop, and pays from that wallet. No voucher needed.
- **UniPin bot** — redeems a UniPin gift card or voucher you own. The serial prefix tells the bot which package to deliver, so there is nothing to choose.

Every order returns the package, region, in-game nickname, status and the exact processing time. The raw response is stored with the order, so a failed attempt can be checked instead of disappearing.

No game password is ever needed. The bot tops up by player ID only.

## Two bots, one account

| | Shell top-up | UniPin top-up |
|---|---|---|
| What it spends | A Garena Shell wallet | A UniPin gift card or voucher you own |
| Package choice | Pick any diamond or membership package | Detected automatically from the voucher serial |
| Batch support | Up to 10 copies of the same package per request | A comma separated list of vouchers per request |
| Typical time | 0–3 seconds | 1–2 seconds |
| Best for | On-demand top-ups, any package, no stock needed | Players who already hold UniPin vouchers |

Both bots share one login, one API key and one order history.

More detail: [Shell top-up bot](docs/shell-topup-bot.md) · [UniPin top-up bot](docs/unipin-topup-bot.md)

## Top-up speed

| Order type | Normal time | Notes |
|---|---|---|
| Shell top-up | **0–3 seconds** | Warm orders usually land in 1–2 seconds. A first order after a long idle can take a little longer while the wallet session is prepared. |
| UniPin top-up | **1–2 seconds** | Sessions are kept warm in the background, so an idle gap does not turn a 2 second redemption into a 6 second one. |

Speed is measured from the request to the final answer and is written into every order record. Several orders can run at the same time, so a batch does not wait behind one queue item.

## Supported shops and servers

Shell top-ups are paid on the shop the wallet belongs to. Every shop below lists the same kind of Free Fire diamonds and memberships.

| Code | Shop | Market | Notes |
|---|---|---|---|
| SG | **shop.garena.sg** | Singapore (default) | The standard Garena shop catalogue, 25 up to 11,500 diamonds |
| MY | **shop.garena.my** | Malaysia | Same Garena catalogue as SG |
| ID | **bdgamesbazar.com** | Indonesia | Adds the Level Up Packages and 115–2,530 diamond tiers |
| IDKG | **kiosgamer.co.id** | Indonesia | Small 5-diamond tier up to 73,100 diamonds |
| PH | **shop.garena.ph** | Philippines | Same Garena catalogue as SG |
| TH | **shop.garena.th** | Thailand | Same Garena catalogue as SG |

A Garena Shell wallet can pay on these shops; the bot picks the one that matches the wallet's region, and SG is the default.

UniPin redemptions are not tied to a shop — the voucher itself carries the package.

## Supported packages

### Shell — Garena shop catalogue (SG, MY, PH, TH)

| Package | Shell price (GS) |
|---|---|
| Diamond 25 | 13 |
| Diamond 100 | 50 |
| Diamond 310 | 150 |
| Diamond 520 | 250 |
| Diamond 1,060 | 500 |
| Diamond 2,180 | 1,000 |
| Diamond 5,600 | 2,500 |
| Diamond 11,500 | 5,000 |
| Weekly Membership | 85 |
| Monthly Membership | 399 |
| Weekly Lite | 14 |

### Shell — bdgamesbazar.com (ID)

| Package | Shell price (GS) |
|---|---|
| Diamond 115 | 45 |
| Diamond 240 | 90 |
| Diamond 610 | 225 |
| Diamond 1,240 | 450 |
| Diamond 2,530 | 900 |
| Weekly Membership | 90 |
| Monthly Membership | 450 |
| Weekly Lite | 18 |
| Level Up Package — Level 6 | 16 |
| Level Up Package — Level 10 | 28 |
| Level Up Package — Level 15 | 28 |
| Level Up Package — Level 20 | 28 |
| Level Up Package — Level 25 | 28 |
| Level Up Package — Level 30 | 40 |

### Shell — kiosgamer.co.id (IDKG)

| Package | Shell price (GS) |
|---|---|
| Diamond 5 | 3 |
| Diamond 50 | 24 |
| Diamond 70 | 33 |
| Diamond 140 | 66 |
| Diamond 355 | 165 |
| Diamond 720 | 330 |
| Diamond 7,290 | 3,300 |
| Diamond 36,500 | 16,500 |
| Diamond 73,100 | 33,000 |
| Weekly Membership | 100 |
| Monthly Membership | 300 |
| Weekly Lite | 150 |

### UniPin packages

| Voucher serial prefix (gift card) | Voucher serial prefix (voucher) | Package |
|---|---|---|
| UPBD-Q | BDMB-T | 25 diamonds |
| UPBD-R | BDMB-U | 50 diamonds |
| UPBD-G | BDMB-J | 115 diamonds |
| UPBD-F | BDMB-I | 240 diamonds |
| UPBD-H | BDMB-K | 610 diamonds |
| UPBD-I | BDMB-L | 1,240 diamonds |
| UPBD-J | BDMB-M | 2,530 diamonds |
| UPBD-N | BDMB-Q | Weekly Membership |
| UPBD-P | BDMB-S | Monthly Membership |

## How a top-up works

1. **Pick a bot.** Shell buys with a wallet; UniPin redeems your voucher. UniPin is the default tab on the top-up page.
2. **Enter the player ID.** For Shell, also choose a package and how many copies. For UniPin, paste one voucher or several separated by commas.
3. **The bot does the work.** It prepares a payment, matches the package on the shop or voucher, completes the purchase and credits the diamonds to that player ID.
4. **Read the result.** The order page shows the package, region, nickname, status, processing time and raw response.

Nothing about the game account is stored beyond the player ID, the package and the result.

## Website and account features

- **Google sign-in** with an API key generated for every account.
- **Free starter requests** for new accounts, set by the operator.
- **Dashboard** with order history, credit ledger and usage stats.
- **API access** for sellers: one endpoint, JSON in and JSON out, documented at [/docs](https://fftopup.emonaxc.com/docs).
- **Raw response per order**, so a failure can be diagnosed instead of guessed.
- **Search, filter, sort and pagination** across orders, users and transactions in the admin panel.
- **Buy limits page** with request packs and direct WhatsApp contact.

## Pricing and request limits

Each processed item has one price, set by the operator; the bot and the package do not change it. Request packs of 50, 200 and 500 are offered on the [buy limits page](https://fftopup.emonaxc.com/buy-limits). New accounts get a small number of free requests so the service can be tested before paying.

Questions about price, balance or a custom plan go to WhatsApp: **https://wa.me/8801788623829**.

## Frequently asked questions

**Is this an official Garena or UniPin service?**
No. FF Top-Up is an independent top-up service. It is not affiliated with Garena, Free Fire or UniPin.

**Do I need the game password?**
No. A numeric Free Fire player ID is enough. The Shell wallet is the only account the bot signs into, and it belongs to the operator.

**What happens if a voucher was already used?**
The order returns `error` with the message `Consumed Voucher`, and no purchase is made. A voucher can only be redeemed once.

**Can I top up several vouchers at once?**
Yes. Paste them separated by commas, for example `UPBD-R-... , BDMB-U-...`, and each voucher becomes its own order.

**Can I buy several copies of one Shell package?**
Yes, up to ten copies in a single request.

**Why does a first order after a long idle take longer?**
The wallet or voucher session has to be prepared again. The bots keep their sessions warm in the background, so this is rare and only affects the first order after a restart or a long quiet period.

**Which regions are supported?**
Shell wallets from the SG/MY/PH/TH shops and the Indonesian shops bdgamesbazar.com and kiosgamer.co.id are supported. UniPin vouchers carry their own region.

**Is there an API?**
Yes. Every account gets an API key after sign-in, and the full request and response shape, error codes and example payloads are on the [docs page](https://fftopup.emonaxc.com/docs).

## Links

- Homepage: https://fftopup.emonaxc.com
- Top-up: https://fftopup.emonaxc.com/topup
- Docs: https://fftopup.emonaxc.com/docs
- Buy limits: https://fftopup.emonaxc.com/buy-limits
- WhatsApp: https://wa.me/8801788623829
- Shell bot details: [docs/shell-topup-bot.md](docs/shell-topup-bot.md)
- UniPin bot details: [docs/unipin-topup-bot.md](docs/unipin-topup-bot.md)
- SEO topics and keyword map: [docs/seo-topics.md](docs/seo-topics.md)

---

*FF Top-Up is an independent service. Garena, Free Fire, Shell and UniPin are trademarks of their respective owners.*
