---
description: >-
  This proposal addresses major inflationary concerns with the RZR token, making
  staking more predictable for protocol in terms of risk and give out
  ETH/SOL/BNB rewards to RZR stakers.
---

# RZR-2: LST rewards, 6-month veStaking & RZR deflation

After taking feedback from many different liquid funds, exchanges and economists; We are excited to share RZR-2, a proposal aimed to make RZR way more scarce in the short/long term, drive more momentum to the price and drive more value to stakers.

We also propose dropping the harberger tax mechanics thereby simplifying the entire staking mechanics even further. This is a crucial part needed to help us attract more new users to come and stake into the protocol.&#x20;

## TL;DR

* Move from inflation-based rebasing yield to proof of stake yield backed by staked ETH, SOL, BNB, HYPE, and other network assets.
* Replace fixed 3-day staking with flexible staking durations: minimum 1 day, maximum 6 months
* Gradually phase out RZR inflation, replacing it with ETH yield and airdrop rewards.
* Strengthen long-term protocol health and reward loyalty with higher yields for longer stakes.

## Motivation

RZR-1 improved staking UX and tax mechanics, but the protocol still relies heavily on inflationary yield through rebases.&#x20;

As the protocol matures and begins accumulating network tokens (ETH, SOL, BNB, HYPE, etc.), we can evolve to a much better and safer yield model. And this is the "proof of stake" rewards from staking these network tokens.&#x20;

If the amount of ETH/SOL etc.. that the protocol holds, is worth a lot more than the value of the staked RZR, then the real yield gets magnified. We are aiming to give out 30% real yield (ETH/SOL/BNB etc..) to RZR stakers.&#x20;

With the below proposal, our goal is to make RZR stronger in terms of price, still give out high yields (so that we can  get eyeballs into the protocol).

## Proposed Changes

With the above in mind, we propose the following changes keeping in mind existing and future stakers.

### 1. Transition from Inflationary to Real Yield

The protocol treasury holds 2mn$ of ETH and will continue to accumulate SOL, HYPE, BNB and other network tokens that generate yield (e.g., ETH via staking, SOL via restaking, or BNB via validators).

Further more RZR price since the time of launch has increased by over XXX%. Giving holders an average XXX% monthly RoR or over an average of XXX% APR.

Going forward:

* Stakers will earn a blend of real ETH-based yield and reduced RZR emission yield.
* Over time, the RZR component will decrease linearly until yield is fully sourced from real assets.
* The protocol may also distribute airdrop rewards from these staked positions directly to stakers.

> **Example:** If the treasury holds more ETH (by USD value) than the total value of RZR staked, staking RZR becomes naturally deflationary — yield is backed by real assets rather than token inflation.

### 2. Introduce Flexible Staking Durations

We enhance the existing sRZR model to introduce variable lock durations.&#x20;

* The maximum lock period is 6 months, much shorter and more flexible than traditional 4-year “ve” systems.
* Unstaking before maturity is allowed but incurs a penalty that’s redistributed to remaining stakers.
* Longer locks amplify real yield share, encouraging loyalty without overcommitting users.

<table><thead><tr><th width="135.4921875">Duration</th><th>Description</th><th>Reward Multiplier</th></tr></thead><tbody><tr><td>3 days</td><td>Minimum stake</td><td>Base yield</td></tr><tr><td>1 month</td><td>Short-term</td><td>Base yield x 2</td></tr><tr><td>3 months</td><td>Medium-term</td><td>Base yield x 4</td></tr><tr><td>6 months</td><td>Long-term</td><td>Base yield x 8</td></tr></tbody></table>

## Expected Outcome

The transition outlined in RZR-2 is designed not just to make staking sustainable, but to realign RZR’s incentives with long-term value creation.

Through this proposal, we aim to either deliver a consistent \~30% APR in ETH/SOL/HYPE or drive RZR price appreciation strong enough to offset the reduced token yield — achieving real, lasting value for stakers.

### Deflationary Token Pressure & Price Improvement

As inflation phases out and yield sources shift to real assets, token emissions fall dramatically while staking demand rises.

This evolution leads to:

* **Reduced sell pressure:** Less RZR is emitted to the market.
* **Increased buy pressure:** Real ETH yield and staking multipliers attract long-term holders.
* **Improved price reflexivity:** Treasury growth and RZR price become positively correlated — higher prices no longer cause more dilution.

Over time, this structure is expected to generate natural RZR price appreciation, as staking becomes a way to access real external yield rather than speculative token farming.

### New RZR Flywheel to raise debt and get more ETH/SOL/BNB

As RZR appreciates, the protocol’s ability to raise debt and expand treasury holdings strengthens. A higher RZR price directly increases the collateral value backing the USD29Y (4-year bond), allowing the protocol to issue more bonds and acquire additional ETH, SOL, and BNB.&#x20;

More treasury assets mean more staking yield, creating a powerful feedback loop where higher RZR price → more bond capacity → more ETH inflow → greater real yield to RZR stakers.&#x20;

This cycle ensures that price growth and yield generation reinforce each other, driving sustainable value across the entire ecosystem.
