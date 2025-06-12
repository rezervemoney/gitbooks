---
description: >-
  Below is a one-page deep dive into Protocol-Controlled Value (PCV) as it will
  operate within the Rezerve Money, including how it accumulates, what it backs,
  and why it’s critical for RZR’s stability
---

# Protocol Controlled Value (PCV)

In the Rezerve Money, PCV represents the on-chain assets the protocol itself owns and controls—distinct from user-supplied liquidity. PCV underwrites every RZR token, provides perpetually available liquidity, and funds yield-generating deployments.

By sourcing PCV from both bond proceeds and Harberger-tax inflows, RZR ensures that staking rewards (rebases) and strategic treasury actions are always backed by real capital. Robust governance over PCV allocation and risk management safeguards RZR’s peg and amplifies long-term protocol health.

## What Is PCV in RZR?

Protocol-Controlled Value in RZR is the sum of all stablecoins, LP tokens, and Harberger-tax receipts held in RZR’s treasury smart contracts. Unlike Total Value Locked (TVL), which includes assets users can withdraw, PCV is reserved exclusively for protocol objectives—backing RZR at a minimum $1-per-token ratio and seeding permanent liquidity on decentralized exchanges (POL).

In RZR’s dual-token design, PCV fuels both:

- Rebase rewards paid to sRZR stakers, converting incoming capital into yield.
- Surplus buy-backs of DrDre, creating a deflationary sink when reserves exceed target buffers.

## How PCV Accumulates in RZR

1. **Bond Sales -** Users purchase RZR at a discount by depositing assets (e.g., USDC, DAI, LP tokens). These assets flow directly into PCV, strengthening the protocol’s collateral backing. (Read [PCV by Sherpies](https://medium.com/sherpa-library/in-pcv-we-trust-e07ed4c5051))
2. **Harberger-Tax Inflows -** Every sRZR holder self-assesses their position’s value and pays a continuous tax (e.g., 5% APR) on that valuation. These recurring payments accrue in PCV as a stable revenue stream, even when bond demand wanes.
3. **Yield Deployments -** PCV assets may be strategically deployed—such as providing liquidity to new pools or farming yield—then harvested and returned to PCV, compounding the treasury over time

### Uses of PCV in RZR

- **Backing RZR Supply -** The controller enforces a minimum backing ratio $$\beta = \tfrac{PCV}{\text{RZR supply}} \ge 1$$, ensuring every RZR token has tangible collateral. If \beta dips, rebase rates are throttled or paused to protect solvency.
- **Protocol-Owned Liquidity (POL) -** A portion of PCV is locked in RZR/ETH and RZR/stablecoin pools, guaranteeing continuous market depth and reducing vulnerability to external liquidity churn.
- **Surplus Buffer & DrDre Buy-Backs -** Excess PCV above a governance-set target (e.g., 5% of PCV) is earmarked for DrDre buy-backs: assets are used to purchase DrDre on the open market and burn it, rewarding long-term governance participants.

## Governance & Risk Management

RZR’s DrDre token holders vote on all PCV-related parameters: bond discounts, Harberger-tax rate, surplus targets, and deployment strategies. In stress scenarios (e.g., asset de-pegging), the multi-tier defense ladder triggers sequential actions—rebase throttling, inverse bonds, surplus draws, and, if needed, DrDre insurance auctions—to restore $$\beta\ge1$$ without jeopardizing protocol integrity .

By centralizing capital under on-chain governance and layering diverse revenue streams, RZR’s PCV model offers a resilient, transparent, and growth-oriented treasury—ensuring that every RZR token remains backed, liquid, and primed for sustainable yield.
