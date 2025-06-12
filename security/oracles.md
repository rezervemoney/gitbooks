---
description: >-
  This page talks about how Dre finance uses oracles to get pricefeeds of
  various assets
---

# Oracles

RZR adopts [eOracle (EO)](https://eo.app/) as its primary data layer. At its core, EO is an open infrastructure platform that empowers developers to build secure blockchain oracles backed by Ethereum's battle-tested security model. EO creates a foundation for specialized data services that combine deep domain expertise with unmatched cryptoeconomic security.

We integrate EO at three distinct tiers:

1. **Treasury Mark-to-Market:** Each epoch the Rebase Controller calls eOracle.latestUsdPrice(token) for USDC, BTC, and tokenised T-Bills; it also requests a _virtual price_ feed for Curve and Balancer LPs. The sum sets the stable-asset numerator in the backing-ratio β.
2. **LP Token Accounting:** For volatile-stable pairs (e.g., RZR/USDC Uni-v3 0.05 %), eOracle publishes a bound-checked TWAP with an adaptive window: 30 minutes by default, expanding to 2 h if intra-block variance is high. This mitigates the sandwich vector that required custom keepers in Olympus.
3. **RZR Reference Price:** A dedicated RZR/USD feed—sourced from at least four exchange venues and re-weighted every block with liquidity score—sets the reference used by external money markets like Aave forks. Lenders can therefore calculate LTV against a floor that only ratchets upward _and_ a spot oracle certified by eOracle’s multi-sig.

## Why Oracles Matter

Every moving part in a reserve-currency protocol—how many tokens to mint, how high to set collateral ratios, how much a bond should cost—depends on unbiased, real-time asset values. An oracle is the bridge between on-chain logic and those off-chain truths.

If that bridge is slow, fragile, or manipulable, the protocol can mint unbacked tokens, mis-price bonds, or even hand out free liquidations. A robust oracle mesh is therefore as critical to solvency as the treasury itself.

## Interplay with Monetary Policy

A precise oracle feed feeds directly into RZR’s capped-inflation curve: if the BTC sleeve rallies, β rises, and the APR band can climb safely; if a flash crash slices 20 % off volatile holdings, the oracle reports it before the next epoch, β falls, and minting throttles to zero.

Likewise, bond discounts are applied to the eOracle RZR/USD feed, preventing under-priced minting. Because half of every inflow raises the Floor Price directly, an accurate treasury mark-to-market is the only guarantee that each 1% floor tick is fully collateralised.
