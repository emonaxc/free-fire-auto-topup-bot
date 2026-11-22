# UniPin Top-Up Bot — Redeem a Free Fire Voucher in Seconds

The UniPin bot redeems a **UniPin gift card or voucher** for Free Fire diamonds and memberships. Paste the serial, enter the player ID, and the package is detected from the serial prefix.

- Run it: **https://fftopup.emonaxc.com/topup** (UniPin tab, selected by default)
- Full API request and response: **https://fftopup.emonaxc.com/docs#order-unipin**
- Voucher format: **https://fftopup.emonaxc.com/docs#voucher**
- UniPin package list: **https://fftopup.emonaxc.com/docs#packages**

---

## What the UniPin bot does

1. Reads the voucher serial and matches its prefix to a package.
2. Creates a UniPin payment for that package.
3. Chooses the exact denomination the voucher is worth.
4. Submits the card serial and PIN to redeem it.
5. Credits the diamonds or membership to the player ID you entered.
6. Stores the region, nickname, package, status, processing time and raw response with the order.

There is no package picker: the serial prefix decides what is delivered, so a 50-diamond voucher can never be redeemed as a 115-diamond package by mistake.

## Voucher prefixes and packages

| Gift card prefix | Voucher prefix | Package |
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

The serial is matched on the first four characters and the letter after the dash, so spaces and dashes in the rest of the code do not matter.

## Speed

| Situation | Normal time |
|---|---|
| Normal redemption | **1–2 seconds** |
| First order after a restart or long idle | A few seconds more while a voucher session is prepared |
| Several vouchers in one request | Each voucher is redeemed in turn; the result lists every item |

Voucher sessions are kept warm in the background, so an idle gap does not turn a 2 second redemption into a 6 second one.

## Redeeming several vouchers

Send a comma separated list:

```
UPBD-R-03025051 1262-7745-9162-6335, BDMB-U-12345678 1111-2222-3333-4444
```

Each voucher becomes its own order with its own status, time and message.

## Error messages you may see

| Message | Meaning |
|---|---|
| `Consumed Voucher` | The voucher was already redeemed. A voucher can only be used once. |
| `Amount unavailable` | UniPin did not recognise the requested amount for this voucher. |
| `Unrecognised voucher serial prefix` | The first characters do not match any supported package; the error lists the valid prefixes. |
| `Invalid uid` | The player ID is not a number. |
| `Package '...' not available` | The voucher's package is not in the current UniPin catalogue. |

The raw response is stored with every order, so the exact wording is always visible.

## FAQ

**Where do I buy UniPin vouchers?**
From any UniPin retailer. This service redeems the voucher; it does not sell the voucher itself.

**Can I check a voucher before paying for a top-up?**
Yes — submit it with the player ID and read the result. A consumed or invalid voucher returns an error before any diamonds are sent.

**Does the bot need my Garena password?**
No. UniPin redemptions only need the numeric player ID.

**Can two vouchers of the same package be redeemed together?**
Yes. Separate them with commas; each becomes its own order.

**Which region does the voucher work in?**
The voucher carries its own region. The UPBD prefixes are Bangladesh gift cards and the BDMB prefixes are vouchers for the same market.

**How fast is a redemption?**
1–2 seconds in normal operation, with the measured time saved on every order.

**Where is the API reference?**
https://fftopup.emonaxc.com/docs#order-unipin — fields, example payloads, status codes and error messages.

---

*FF Top-Up is an independent service and is not affiliated with Garena, Free Fire or UniPin.*
