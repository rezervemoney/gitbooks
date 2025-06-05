---
description: This page goes through bond and how it works
---

# Bonding Model

The (4,4,4) bond bundles bonding, vesting, and auto-compounding into a single user flow: users purchase a bond that vests over four days, and at each four-day interval the protocol automatically restakes the vested tokens twice, resulting in a total of three compounding cycles over twelve days.&#x20;

This streamlined mechanism delivers superior capital efficiency, frictionless compounding, and stronger alignment between user incentives and protocol health compared to OlympusDAO’s five-day linear-vesting bonds, which require manual claiming and restaking.

## Structure of a (4,4,4) Bond

In a (4,4,4) bond, a user deposits assets (e.g., LP tokens or stablecoins) in exchange for a discounted payout denominated in the protocol’s native token. The bond’s key parameters are:

* **Vesting Period:** Four days per cycle, matching the protocol’s epoch length.&#x20;
* **Auto-Restake Rounds:** Upon the first four-day vest, the newly issued tokens are automatically staked for another four days; this repeats once more.&#x20;
* **Total Lockup:** Twelve days (4 + 4 + 4), during which each tranche compounds at the current rebase rate.&#x20;

By embedding restaking logic in the bonding contract, the (4,4,4) model eliminates user friction and ensures every vesting tranche immediately begins earning rewards.

## Worked Example & Math

Suppose the protocol offers a 20 % APR bond (annualized) and an 8-hour epoch rebase rate of 0.22 %. A user deposits $1,000 of assets at a 15 % discount, so they are entitled to 1,176.47 tokens (1,000 / (1–0.15)).&#x20;

1. **Day 0–4 (Epochs 0–12)**
   * Vest tranche 1: 1,176.47 / 3 ≈ 392.16 DRE are released linearly and staked into sDRE.
   * These tokens are auto-staked, earning 0.22% per epoch (3 epochs/day).
   * If a user wants to retrieve the underlying DRE, then should trigger an unstake request which gives out liquid DRE in a 3 day period. (Which means if a user chooses to be aggressive and not go for staking, they'll get 33% of their yield upfront in a 3 day cliff).
2. **Day 4–8 (Epochs 13–24)**
   * Tranche 1 continues to earn rebases in staked form.
   * Tranche 2 (another 392.16 DRE) vests and is immediately staked.
   * Same logic for withdrawals applies as above.
3. **Day 8–12 (Epochs 25–36)**
   * All previously issued tokens (tranches 1 & 2) compound further.
   * Tranche 3 vests into staking, completing the three-cycle compounding.

After twelve days, the user holds 1,176.47 × (1 + 0.22 %)³ ≈ 1,184.3 DRE, plus ongoing staking rewards thereafter.

## Why It Beats OlympusDAO’s Model

OlympusDAO bonds vest linearly over five days and require users to manually claim and restake their OHM to capture rebases, introducing friction and the risk of missed compounding opportunities.  In contrast, the (4,4,4) bond:

* **Automates Compounding**: Eliminates manual steps, ensuring every token tranche is staked immediately.&#x20;
* **Aligns Incentives:** Longer effective lockup (12 days vs. 5 days) fosters deeper commitment and reduces sell-pressure.&#x20;
* **Enhances Capital Efficiency**: By synchronizing vesting with the protocol’s epoch cycle, it maximizes rebase capture per unit of time.&#x20;

## Conclusion

The (4,4,4) bonding model refines the DeFi bonding primitive by embedding automatic compounding into the vesting schedule, reducing user friction and aligning long-term incentives. By contrast, OlympusDAO’s standard five-day bonds leave compounding in users’ hands and truncate the compounding window.&#x20;

For protocols prioritizing yield efficiency and stickiness, the (4,4,4) bond offers a clear upgrade.
