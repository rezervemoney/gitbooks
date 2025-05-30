---
description: >-
  Below is a one-page deep dive into Protocol-Controlled Value (PCV) as it will
  operate within the DRE Protocol, including how it accumulates, what it backs,
  and why it’s critical for DRE’s stability
---

# Protocol Controlled Value (PCV)

In the DRE Protocol, PCV represents the on-chain assets the protocol itself owns and controls—distinct from user-supplied liquidity. PCV underwrites every DRE token, provides perpetually available liquidity, and funds yield-generating deployments.&#x20;

By sourcing PCV from both bond proceeds and Harberger-tax inflows, DRE ensures that staking rewards (rebases) and strategic treasury actions are always backed by real capital. Robust governance over PCV allocation and risk management safeguards DRE’s peg and amplifies long-term protocol health.

## What Is PCV in DRE?

Protocol-Controlled Value in DRE is the sum of all stablecoins, LP tokens, and Harberger-tax receipts held in DRE’s treasury smart contracts. Unlike Total Value Locked (TVL), which includes assets users can withdraw, PCV is reserved exclusively for protocol objectives—backing DRE at a minimum $1-per-token ratio and seeding permanent liquidity on decentralized exchanges (POL) ￼.

In DRE’s dual-token design, PCV fuels both:

* Rebase rewards paid to sDRE stakers, converting incoming capital into yield.
* Surplus buy-backs of DrDre, creating a deflationary sink when reserves exceed target buffers.

## How PCV Accumulates in DRE

1. **Bond Sales -** Users purchase DRE at a discount by depositing assets (e.g., USDC, DAI, LP tokens). These assets flow directly into PCV, strengthening the protocol’s collateral backing. (Read [PCV by Sherpies](https://medium.com/sherpa-library/in-pcv-we-trust-e07ed4c5051))
2. **Harberger-Tax Inflows -** Every sDRE holder self-assesses their position’s value and pays a continuous tax (e.g., 5% APR) on that valuation. These recurring payments accrue in PCV as a stable revenue stream, even when bond demand wanes.&#x20;
3. **Yield Deployments -** PCV assets may be strategically deployed—such as providing liquidity to new pools or farming yield—then harvested and returned to PCV, compounding the treasury over time

### Uses of PCV in DRE

*   Backing DRE Supply

    The controller enforces a minimum backing ratio $$\beta = \tfrac{PCV}{\text{DRE supply}} \ge 1$$, ensuring every DRE token has tangible collateral. If \beta dips, rebase rates are throttled or paused to protect solvency.
*   Protocol-Owned Liquidity (POL)

    A portion of PCV is locked in DRE/ETH and DRE/stablecoin pools, guaranteeing continuous market depth and reducing vulnerability to external liquidity churn.
*   Surplus Buffer & DrDre Buy-Backs

    Excess PCV above a governance-set target (e.g., 5% of PCV) is earmarked for DrDre buy-backs: assets are used to purchase DrDre on the open market and burn it, rewarding long-term governance participants.

## Governance & Risk Management

DRE’s DrDre token holders vote on all PCV-related parameters: bond discounts, Harberger-tax rate, surplus targets, and deployment strategies. In stress scenarios (e.g., asset de-pegging), the multi-tier defense ladder triggers sequential actions—rebase throttling, inverse bonds, surplus draws, and, if needed, DrDre insurance auctions—to restore $$\beta\ge1$$ without jeopardizing protocol integrity  .

By centralizing capital under on-chain governance and layering diverse revenue streams, DRE’s PCV model offers a resilient, transparent, and growth-oriented treasury—ensuring that every DRE token remains backed, liquid, and primed for sustainable yield.
