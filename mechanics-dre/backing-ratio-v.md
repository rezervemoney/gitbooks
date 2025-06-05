---
description: The Compass of DRE Monetary Policy
---

# Backing Ratio - β

The backing (or bonding) ratio β measures how many non-native assets sit in the treasury for each DRE token in circulation:

$$
\beta \;=\; \frac{\text{Protocol-Controlled Value (stable assets only)}}{\text{Circulating DRE}}
$$

**Numerator** – USDC, tokenised T-Bills, the stable-coin leg of DRE/USDC LP, and any other risk-free assets that can be liquidated on-chain within minutes.

**Denominator** – All liquid DRE plus the staked supply (sDRE); tokens held by the treasury itself are counted, because they can be re-introduced to the market.

β therefore answers a single question: _“If every token holder redeemed simultaneously, how many dollars could the protocol deploy per token?”_

## Why β Matters

1. **Inflation Governance -** DRE’s capped-inflation curve keys off β. When β < 1, issuance halts; between β = 1 and 2.5, APR rises from 0 % to 2 000 %. Thus β is the throttle that keeps rebase rewards solvent.
2. **Floor-Price Enforcement -** The hard-floor logic requires β ≥ 1. If market price dips below the floor, the treasury uses its stable reserves to buy back and burn DRE; those reserves exist precisely because β was >=1 before inflation resumed.
3. **Collateral Listings -** Lending protocols look to β to decide loan-to-value caps. A high, slowly increasing β signals lower default risk, unlocking deeper liquidity for DRE-backed loans.

## How does β changes with a rising floor price?

When the hard-floor ratchets upward, each token suddenly “owes” more collateral: the required stable value per DRE steps from, say, $1.18 to $1.19. Because the treasury has just locked in the surplus that triggered the lift, the numerator (stable PCV) already covers the new obligation, but the denominator—circulating supply—hasn’t changed.&#x20;

The immediate effect is that β, which is PCV / supply, slips slightly (the same pile of stables is now divided by a larger per-token requirement). That small dip is intentional: it nudges the APR curve down a notch, slowing emissions until fresh inflows replenish the surplus and nudge β back up.&#x20;

In other words, every floor increase reallocates a slice of the surplus from “excess collateral” into “hard backing,” momentarily tightening issuance yet leaving the system fully solvent; subsequent bond deposits and Harberger taxes grow PCV again, pushing β higher and re-unlocking the steeper yield bands.

To underestand more about the floor price, read [here](price-hard-floor.md).
