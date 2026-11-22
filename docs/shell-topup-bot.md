# Shell Top-Up Bot — shop.garena.my, shop.garena.sg and Indonesian Shell shops

The Shell bot buys Free Fire diamonds and memberships directly on the Garena shop and pays from a **Garena Shell wallet**. There is no voucher to buy first: pick a package, enter the player ID, and the bot completes the checkout.

- Run it: **https://fftopup.emonaxc.com/topup** (Shell tab)
- Full API request and response: **https://fftopup.emonaxc.com/docs#order-shell**
- Package list in the docs: **https://fftopup.emonaxc.com/docs#packages**

---

## What the Shell bot does

1. Signs into a Garena Shell wallet.
2. Opens the shop that matches the wallet's region.
3. Adds the chosen package — diamonds, Weekly, Monthly or Weekly Lite — to the checkout.
4. Pays from the Shell wallet.
5. Credits the diamonds to the player ID you entered.
6. Stores the region, nickname, package, status, processing time and raw response with the order.

The Free Fire account password is never involved. The bot only needs the numeric player ID.

## Supported shops

| Code | Shop | Market | Catalogue |
|---|---|---|---|
| SG | https://shop.garena.sg | Singapore — **default** | 25 to 11,500 diamonds plus memberships |
| MY | https://shop.garena.my | Malaysia | Same Garena catalogue as SG |
| ID | https://bdgamesbazar.com | Indonesia | 115 to 2,530 diamonds, memberships and Level Up Packages |
| IDKG | https://kiosgamer.co.id | Indonesia (app 100067) | 5 to 73,100 diamonds plus memberships |
| PH | https://shop.garena.ph | Philippines | Same Garena catalogue as SG |
| TH | https://shop.garena.th | Thailand | Same Garena catalogue as SG |

A Shell wallet can pay on these shops. SG is used when no server is chosen, so a request that does not name a server always works.

## Packages per shop

### shop.garena.sg, shop.garena.my, shop.garena.ph, shop.garena.th

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

### bdgamesbazar.com (ID)

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

Level Up Packages are one-time offers that the shop only lists for a signed-in player, which is why they appear with the Indonesian catalogue and not with an anonymous shop read.

### kiosgamer.co.id (IDKG)

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

## Speed

| Situation | Normal time |
|---|---|
| Warm wallet, standard package | **1–3 seconds** |
| First order after a long idle or restart | A few seconds more while the wallet session is prepared |
| Batch of several copies of one package | Each copy is processed in turn; the result lists every item |

The order record always shows the measured processing time, so the number is checkable rather than a claim.

## Batch and concurrency

- Up to **10 copies of the same package** in one request, each with its own result.
- Different wallets and different orders can run **in parallel**, so two customers do not queue behind each other.
- If the shop temporarily refuses traffic, the request returns a clear retry time instead of a silent failure.

## Order statuses

| Status | Meaning |
|---|---|
| `success` | The shop accepted the payment and the package was delivered |
| `error` | The order did not complete — the message names the reason (for example not enough wallet balance, package unavailable, shop refused the request) |
| `duplicate` | The same order ID was sent before and the stored answer is replayed; nothing is bought twice and nothing is charged twice |

A failed order ID can be retried with a new order ID.

## FAQ

**Do I need to own a Shell wallet?**
No. The service runs the wallet; you only pay for the processed request.

**Which shop is used by default?**
shop.garena.sg. Choose MY, ID or IDKG in the request or on the dashboard to use a different shop.

**Can a Malaysian or Indonesian wallet pay on the SG shop?**
Wallets are matched to the shop for their region — MY uses shop.garena.my and the Indonesian shops use bdgamesbazar.com or kiosgamer.co.id. SG is the fallback.

**Is a voucher needed for Shell?**
No. The Shell bot buys on demand. If you already own a UniPin voucher, use the UniPin bot instead.

**How fast is it?**
Warm orders finish in 1–3 seconds, often around 2 seconds. The exact time is stored with every order.

**Where is the API reference?**
https://fftopup.emonaxc.com/docs#order-shell — fields, examples, status codes and error messages.

---

*FF Top-Up is an independent service and is not affiliated with Garena, Free Fire or Shell.*
