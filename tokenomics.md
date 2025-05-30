---
description: This page goes through the tokenomics of the DrDre token.
---

# Tokenomics

<figure><img src=".gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

## Value-Accrual Flywheel

This section explains the various components that creates a positive feedback loop for the DrDre token.

### Surplus buffer fills

_20 %_ of every Harberger-tax receipt and bond fee is routed to a stable-coin Surplus Buffer (SB) until it equals 5 % of PCV.

### Buy-back & burn

When SB > target, 50 % of the excess is streamed through a TWAMM to market-buy DrDre and send it to the burn address—an approach used by xSUSHI, BNB auto-burn and recent Frax buy-back proposals.

### Insurance reserve

If a backing asset crash pushes the backing ratio β < 1 and SB is empty, the protocol triggers an Insurance Auction that mints just enough new HBG to recapitalize β ≥ 1—exactly how MakerDAO mints MKR in a debt auction.
