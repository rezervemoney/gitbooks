---
description: >-
  RZR-1 introduces a further improvement in the staking dynamics and makes using
  lstRZR more attractive within DeFi.
---

# RZR-1: Update in the staking dynamics

This is the first governance post that addresses a very crucial part about the protocol’s growth. Voting for this proposal will be made live on SnapShot and users can vote with your lstRZR or sRZR balance.

## TL;DR

* Replace the upfront Harberger tax with a continuous (streamed) tax plus a small prepaid buffer.
* Introduce clear economic incentives to buy mis-priced stakes.
* Migrate fairly and convert already-paid upfront taxes into tax credits so early users are treated fairly.

## Pain Points Identified

1. **Upfront tax kills UX & composability.** Integrations must swallow a large one-time cost.
2. **No strong reason to buy stakes** because RZR is liquid; buyers prefer the market unless a stake is underpriced by >5%.
3. **4626 vault integrations pay \~6.5%** on entry—too high for partners and LPs to justify.

With this in mind we propose the following changes.

## Changes Proposed

1. Convert taxes from being paid upfront to instead be streamed over time.
2. Introduce a dynamic deposit fee for staking mechanism that changes based on demand.
   1. During periods of high demand, the deposit fee will increase (5-10%) creating a reason for new users to buy stakes when staking charges an upfront fee as that creates a cheaper opportunity to enter into.
   2. During periods of low demand, the deposit fee will decrease (0%) users can easily enter into the staking ecosystem by buying liquid RZR and creating new stakes without any upfront fee.
   3. When the proposal goes live, the deposit fee will be 0.
3. We must not punish early adopters who pre-paid tax. To this we have come up with a tax “credit” system where all paid tax is taken from this credit. Snapshot each stake/vault depositor’s **unamortized portion** of the upfront tax. Future streaming taxes burn down this credit. For vault depositors, the credit lives at the vault and is consumed pro-rata.
