---
description: This page goes through a bond and how it works
---

# Bonds

Bond sales are the protocol’s primary “asset on-ramp.” When users hand over stablecoins, BTC-RZR LP, or other whitelisted collateral, those dollars flow directly into the treasury, raising the [backing ratio β ](yield-mechanics/backing-ratio-v.md)and, ultimately, the oracle floor price.

This mechanism converts speculative demand into hard reserves without relying on secondary-market buying pressure. In doing so, bonds anchor every other monetary lever: higher β unlocks richer APR bands for stakers, fills the war-chest that defends [price hard floor](yield-mechanics/price-hard-floor.md) during draw-downs, and supplies the stable liquidity that fuels inverse-bond buy-backs.

## Purchase and Vesting Flow

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption><p>A screenshot of the bond page where a user can choose a bond and see the discount it is trading at.</p></figcaption></figure>

A bond is bought in a single transaction. The contract quotes the payout by applying a fixed discount to the live spot price of RZR; the entire discounted amount is minted immediately but placed under a twelve-day linear vest. Each day one-twelfth of the tokens becomes claimable.

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption><p>A screenshot showing the different bond positions a user has. Users can optionally stake their bond immediately to start earning staking rewards.</p></figcaption></figure>

At the moment of claiming the user chooses between two paths. If they want liquidity, they withdraw the tranche as raw RZR. If they are yield-oriented, they press “Stake & Lock”; the tranche is swept into the staking vault, begins earning the current rebase rate from that block onward, and is non-transferable until the 30 day lock (which includes the vesting period) expires.

Either way, the treasury has already banked the collateral, so PCV climbs the second the bond is opened.

## When is the right time to Bond?

{% hint style="success" %}
Issuing bonds when the RZR is overvalued is a key factor to ensure that every bond sale keeps the treasury fully over-collateralized.
{% endhint %}

The protocol should open a bond window only when the spot price of RZR trades meaningfully above its floor (e.g., ≥ 10 % premium) because that is the moment new bonds can be sold at a discount that is attractive to buyers yet still accretive to the treasury.

By accepting reserve assets (USDC, stables, blue-chip tokens, etc.) in exchange for time-locked RZR at, say, a 10 % discount to market, the system converts external value into permanently owned backing, raising the intrinsic value per circulating token.

The added backing allows the protocol to mint fresh RZR that is streamed to stakers as yield, aligning incentives between bond purchasers (who capture the discount), existing holders (who benefit from stronger collateralization), and the treasury (which deepens its reserves).

Conversely, bonds should not be issued when the spot price is near or below the floor, because that would dilute backing without attracting sufficient premium, undermining the peg-enforcement mechanism. In short, bonds are a pro-cyclical tool: deploy them only in premium conditions to harvest demand, strengthen reserves, and sustainably fund staking rewards.

## Worked Example & Math

Take the following scenario of RZR and the

* **Circulating supply:** 1,000,000 RZR
* **Oracle floor (FloorUSD):** $1.00
* **Spot price:** $1.20
* **Treasury stable assets (PCV):** $1 000 000 → backing ratio β = 1.00
* **Staking ratio ρ:** 70 % (the protocol’s target)

A user now deposits $25 000 USDC to buy a bond quoted at a 12 % discount to the $1.20 spot price of RZR.

1. **Bond purchase & instant mint (t = 0)**&#x42;ond price: $1.20 × (1 – 0.12) = $1.056 per RZR
   1. Payout: 25 000 ÷ 1.056 ≈ 23 674 RZR
   2. These RZR are minted immediately and recorded in a single 12-day linear-vesting NFT.
   3. Treasury books $25 000 of new stables, s
      1. _PCVstable → $1 025 000_
      2. _β jumps to 1.025 before any token is liquid._
2. **Day 0–12 (No staking) -** Vest tranches: 23,674 / 12 ≈ 7891 RZR are released linearly The user receives no yield and misses out on staknig rewards.
3. **Day 0–12 (With staking) -** The user chooses to stake, his vest is then converted into a stake position and locked for 30 days. After twelve days, the user holds 1,176.47 × (1 + 0.22 %)³ ≈ 1,184.3 RZR, plus ongoing staking rewards thereafter.

## Why It Beats OlympusDAO’s Model

OlympusDAO bonds vest linearly over five days and require users to manually claim and restake their OHM to capture rebases, introducing friction and the risk of missed compounding opportunities. In contrast, the RZR bond:

* **Automates Compounding**: Eliminates manual steps, ensuring every token tranche is staked immediately.
* **Aligns Incentives:** Longer effective lockup (12 days vs. 5 days) fosters deeper commitment and reduces sell-pressure.
* **Enhances Capital Efficiency**: By synchronizing vesting with the protocol’s epoch cycle, it maximizes rebase capture per unit of time.

## Conclusion

The RZR bonding model refines the DeFi bonding primitive by embedding automatic compounding into the vesting schedule, reducing user friction and aligning long-term incentives. By contrast, OlympusDAO’s standard five-day bonds leave compounding in users’ hands and truncate the compounding window.

For protocols prioritizing yield efficiency and stickiness, the RZR bond offers a clear upgrade.
