---
description: This page talks about the DrDRE governance token
---

# Overview

In essence, DrDRE soaks up _positive_ cash-flow by buying itself back and burning, yet can be _minted_ to recap the treasury after a loss—exactly the reflex that MakerDAO pioneered with MKR. The loop keeps DRE’s rebase engine humming while shifting tail-risk onto DrDRE holders, a structure already proven in MakerDAO, Aave’s Safety Module, Sushi’s xSUSHI, Binance-BNB and others.

## Why add a second token?

**Surplus recycling:** directing excess Harberger-tax and bond fees into periodic buy-backs pushes HBG price up and removes supply, echoing xSUSHI and BNB burns.

**Contingent insurance:** if backing ever falls below 1, the protocol can auction freshly-minted HBG for stablecoins, the same “debt-auction” circuit MakerDAO used to cover its $4 m ETH-crash shortfall in 2020.

**Governance skin-in-the-game:** voters who raise risk also face dilution in a loss event—MKR’s foundational incentive.

| Flow                     | Trigger                                       | Action                                                  | Analogue                                 |
| ------------------------ | --------------------------------------------- | ------------------------------------------------------- | ---------------------------------------- |
| Surplus Buy-back         | Surplus buffer SB > target (e.g., 5 % of PCV) | Spend 50 % of SB to TWAMM-buy HBG, then burn            | Sushi buy-back queue, Frax 2022 proposal |
| Surplus Refill           | SB < target & PCV solvent                     | Route 20 % of Harberger tax + 20 % of bond fee into SB  | Maker DAO surplus auction (reverse)      |
| Insurance Auction        | Backing ratio \beta<1 and SB=0                | Mint HBG, Dutch-auction for stablecoins until \beta\ge1 | Maker debt auction, Aave shortfall slash |
| Safety Module (optional) | Users stake HBG for yield                     | Up to 30 % may be slashed before minting new HBG        | Aave Safety Module rules                 |

## Impact analysis

#### On DRE (rebase token)

* More stable APY: surplus receipts buffer small PCV draw-downs so r\_t need not pause at every wobble.
* Lower tail risk: catastrophic shortfall covered first by slashing staked HBG or minting new HBG, sparing HBA holders until HBG market cap is exhausted.

#### On DrDre (governance/insurance)

* Dual demand drivers:
  * upside from buy-backs (xSUSHI, BNB).
  * yield from staking in a Safety Module (Aave).
* Downside dilution: minting in crises resembles MKR printing—perceived as a put option on the protocol's solvency.

#### Systemic robustness

* **Granular defence ladder:** surplus → stake-slashing → DRE mint → inverse bonds (sell PCV for HBA). Combining insurance and inverse bonds echoes Olympus’ RBS design but with an extra equity layer.
* **Socialised risk pricing:** HBG holders internalise protocol leverage, aligning votes on risk parameters with personal downside (Maker Endgame rationale).

## Conclusion

By absorbing upside through buy-backs and wearing downside via dilution, DrDRE socializes risk the same way MKR does for DAI, AAVE does for Aave and xSUSHI does for SushiSwap fee flow. ￼ ￼ ￼ This two-token structure lets the protocol keep DRE’s headline APY attractive while ensuring that any “mad bad-debt” event is pre-funded by governance token holders—not by a sudden haircut on stakers.
