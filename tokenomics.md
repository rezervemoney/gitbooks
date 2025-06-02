---
description: This page goes through the tokenomics of the DrDre token.
---

# Tokenomics

DrDre is designed to align long-term governance incentives with protocol health. A fixed supply is minted at genesis and allocated as follows:

<figure><img src=".gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

<table><thead><tr><th width="181.5859375">Allocation Category</th><th width="135.94140625">% of Total Supply</th><th>Notes on Purpose &#x26; Vesting</th></tr></thead><tbody><tr><td>Presale</td><td>60 %</td><td>Private &#x26; public sale to bootstrap community and raise initial treasury funds. 100% Unlock.</td></tr><tr><td>Early Stakers</td><td>20 %</td><td>Rewards for earliest DRE stakers who provided protocol traction. 100% Unlock.</td></tr><tr><td>Liquidity Provision</td><td>10 %</td><td>Incentives for initial LP on DEXes (e.g. DRE/ETH). Emissions distributed over 3 months.</td></tr><tr><td>Treasury Reserve</td><td>10 %</td><td>Held by DAO for strategic grants, ecosystem partnerships, and insurance buffer top-ups. 1 Year Linear Vesting</td></tr></tbody></table>

## Value-Accrual Flywheel

This section explains the various components that creates a positive feedback loop for the DrDre token.

### Surplus buffer fills

_20 %_ of every Harberger-tax receipt and bond fee is routed to a stable-coin Surplus Buffer (SB) until it equals 5 % of PCV.

### Buy-back & burn

When SB > target, 50 % of the excess is streamed through a TWAMM to market-buy DrDre and send it to the burn address—an approach used by xSUSHI, BNB auto-burn and recent Frax buy-back proposals.

### Insurance reserve

If a backing asset crash pushes the backing ratio β < 1 and SB is empty, the protocol triggers an Insurance Auction that mints just enough new HBG to recapitalize β ≥ 1—exactly how MakerDAO mints MKR in a debt auction.

DrDre is designed to align long-term governance incentives with protocol health. A fixed supply is minted at genesis and allocated as follows:

## Key Takeaways

* The 60 % presale and 20 % early staker allocations ensures that the community holds roughly 80% of the total supply.
* With no unlocks and vesting (except for the treasury) this ensures that the token is almost fully circulating at the time of launch.
* With constant buyback and burns, this ensures deflationary mechanics which makes DrDRE scarce over time. There are no inflationary mechanics like staking rewards etc.

This balanced structure drives early network growth, sustains active governance participation, and builds a robust insurance layer for DRE token holders.
