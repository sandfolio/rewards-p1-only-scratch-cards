# Mint Money — Rewards (Phase 1)

Interactive HTML prototype of the **Phase 1 Rewards tab** for Mint Money.
Users earn **coins** and **scratch cards** by paying bills; every scratch card reveals an **Amazon voucher (₹100 – ₹1,000)**.
Coins unlock gift cards and partner deals in the Rewards store.

Built on the Mint Money 3.0 Design System (mm30-ds). Single self-contained file, no build step.

## Run

Open `index.html` in a browser, or serve the folder:

```bash
npx serve .        # or: python3 -m http.server
```

Works on GitHub Pages as-is (Settings → Pages → deploy from branch root).

## Rewards home (top to bottom)

| # | Section | What it does |
|---|---------|--------------|
| 1 | Scratch card banner | "You have N scratch cards" — opens the scratch popup. Hidden when no cards are left |
| 2 | Rewards balance | Coins and Vouchers tiles (open Coins history / My vouchers) |
| 3 | Pay & earn | Credit card, Electricity, Mobile recharge — "Pay now" simulates a payment and adds a scratch card |
| 4 | Milestones | Carousel: Credit builder, Personal loan, Credit card, Read more to earn more |
| 5 | Scratch cards | Recent cards; tap any card to open the scratch popup |
| 6 | Deals | Carousel — "Claim for [coins]" |
| 7 | Popular brands | 3×2 brand grid — tap a brand to see its gift cards |
| 8 | Top gift cards | Carousel — "Unlock with [coins]" |
| 9 | Menu | Rewards store, My scratch cards, My vouchers, Rewards history, How rewards work, FAQs, Support |

## Scratch card flow

1. Tap the banner or any scratch card → centred popup ("Scratch card 1 of 2").
2. Drag to scratch (or "Reveal without scratching").
3. Confetti + Amazon voucher reveal with code. Voucher is saved to **My vouchers**.
4. Auto-moves to the next card after **3 seconds** (or tap "Next card"). Last card shows "Done".

## UC · Awarded SC (scratch card after a bill payment)

Open **UC · Awarded SC** in the side panel. The Bill details screen loads, and after ~0.8s a scratch card is awarded:

1. Popup with confetti and an animated scratch card: **"Congrats!! You've got a scratch card"** — *Scratch & unlock an Amazon voucher worth up to ₹1,000*.
2. **Scratch now** opens the scratch popup on that card (same reveal + auto-next flow).
3. **Later** keeps the card in My scratch cards (home banner and menu badge update).
4. **Claim Rewards** on the bill screen also opens the scratch popup.

![Awarded scratch card](screenshots/12-uc-awarded-scratch-card.png)

## Rewards store

Tabs: **Gift cards · Deals · Brands**, each with category chips. Cards use the same components as the home screen.

## Screenshots

| | | | |
|---|---|---|---|
| ![Home](screenshots/01-home.png) | ![Pay & earn, Milestones](screenshots/02-pay-earn-milestones.png) | ![Deals, Brands](screenshots/03-deals-brands.png) | ![Top gift cards](screenshots/04-top-gift-cards.png) |
| ![Scratch popup](screenshots/05-scratch-popup.png) | ![Amazon voucher reveal](screenshots/06-reveal-amazon-voucher.png) | ![Store · Gift cards](screenshots/07-store-gift-cards.png) | ![Store · Deals](screenshots/08-store-deals.png) |
| ![Store · Brands](screenshots/09-store-brands.png) | ![My vouchers](screenshots/10-my-vouchers.png) | ![Menu](screenshots/11-bottom-menu.png) | |

## Removed from the full Rewards prototype (out of Phase 1)

Spin & win, cashback, Refer & earn, the old Milestones tracker, Spend your coins, Total rewards value, the dark Gift cards screen.

## Notes / to confirm

- Brand names (Carewell, Pizzaro, Cluckers, NovaCard, Skyhop…) and their artwork are **placeholders** — swap in licensed logos for production. The Amazon voucher uses plain text, not Amazon's logo.
- Coin rate: 24 coins = ₹1. Gift card coin prices other than Carewell (2,400) and Mobile recharge (500) are derived from that rate — confirm.
- Milestone buttons show a toast; target flows to be linked.
- State lives in memory only. Reload or "Reset prototype" to start over.
