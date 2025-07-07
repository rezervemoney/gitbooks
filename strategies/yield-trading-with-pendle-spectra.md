---
description: >-
  This page explains how one can trade yield with yield trading platforms like
  Spectra/Pendle
---

# Yield Trading with Pendle/Spectra

lstRZR is a liquid staking wrapper around the native RZR staking system, offering a 130% buyout value for early exits. lstRZR represents a claim on staked RZR and accrues yield over time from validator rewards.

This design allows lstRZR holders to access DeFi yield trading protocols like Spectra/Pendle, which enable separating and trading the yield component of the asset independently from its principal.

## How Yield Trading Works?

Platforms like Spectra/Pendle tokenize yield-bearing assets (like lstRZR) into two components:

1. **Principal Token (PT):** Represents the principal amount of lstRZR, redeemable at maturity or via buyout.
2. **Yield Token (YT):** Represents the right to claim all the future yield from the principal until maturity.

This separation unlocks new financial strategies:

- **Buy PTs at discount:** Lock in a fixed yield by buying PTs at less than face value and redeeming at maturity.
- **Trade YTs:** Gain leveraged exposure to yield or hedge against yield fluctuations.
- **Provide liquidity:** Earn LP fees and incentives on PT/YT pools.

To learn more about how yield trading works, see

{% embed url="https://www.youtube.com/watch?v=RHuqNScvrnw" %}

## Why trade RZR yield?

Trading RZR yield is especially compelling because RZR offers unusually high staking returns, driven by mechanisms inspired by OlympusDAO’s game-theoretic design—including protocol-owned liquidity, rebasing, and incentive-driven staking dynamics. These high yields create a deep secondary market for yield speculation and arbitrage.

By trading the yield separately (via YT-lstRZR), users can either cash out these high forward yields upfront, or gain leveraged exposure to them if they believe the rewards will persist or grow. This allows DeFi participants to take directional bets on staking performance, hedge against dilution or emission changes, and unlock a new layer of capital efficiency while interacting with one of the most aggressive yield systems in the ecosystem.

## Strategies

Based on the above information, we can create various strategies on trading yield.

### 1. Sell Yield Upfront

This strategy allows users to unlock future staking rewards today. Upon depositing lstRZR into a yield trading platform like Pendle/Spectra, it is split into PT-lstRZR (principal) and YT-lstRZR (yield).

Users can immediately sell their YT tokens to obtain upfront yield while retaining PT tokens to be redeemed at full value at maturity. This is useful for users who seek immediate liquidity or expect future yields to decline.

Example: If a user deposits 100 lstRZR and sells YT for 10 tokens, they effectively receive that 10-token yield immediately and later redeem 100 tokens worth of PT.

#### An Example

Imagine you hold 100 lstRZR tokens and want to monetize your future staking rewards today without fully exiting your staking position.

You deposit your 100 lstRZR into a platform like Pendle/Spectra, which splits it into:

- PT-lstRZR (100 tokens) — representing the principal value redeemable at maturity (e.g., in 6 months)
- YT-lstRZR (100 tokens) — representing the right to receive all yield generated over the next 6 months

Now, suppose the current market price for 1 YT-lstRZR token is 0.12 RZR, reflecting buyers’ valuation of the upcoming yield stream.

**You execute the following:**

- Sell all 100 YT-lstRZR tokens on the open market → Receive 12 RZR immediately (100 × 0.12)
- Hold the 100 PT-lstRZR tokens until maturity → Redeem for the original 100 RZR later

**Outcome:** You’ve locked in 12 RZR of future yield instantly. At maturity, you’ll get your 100 RZR principal back. Your total return is 112 RZR (effectively a 12% upfront yield).

It’s the DeFi equivalent of selling future coupon payments while holding a bond until maturity.

### 2. Buy Yield to Arbitrage or Speculate

In this approach, users buy YT-lstRZR tokens on the open market to gain exposure to yield—particularly when they believe these tokens are undervalued or that staking rewards will increase.

By acquiring YT at a discount and holding it, users can profit from the actual accrued yield. This strategy is especially appealing for DeFi traders expecting network upgrades, validator changes, or RZR tokenomics that could boost staking returns.

#### An Example

Let’s say you’re analyzing the YT-lstRZR market on Pendle/Spectra and notice that a YT representing yield over the next 6 months is trading at 5 RZR. You expect staking rewards from lstRZR over this period to generate at least 12 RZR in yield.

This creates a clear arbitrage opportunity:

- **Action**: You buy the YT-lstRZR for 5 RZR.
- **Expected Yield Payout**: Over the next 6 months, you collect 12 RZR from the underlying lstRZR staking rewards.
- **Profit**: 12 RZR received – 5 RZR invested = 7 RZR net profit, or 140% return.

This strategy hinges on your belief that the market is underpricing future yield. If your forecast holds, you’ve effectively bought a cash flow stream at a steep discount.

Alternatively, if RZR staking APR is trending upward (e.g., moving from 8% to 15% due to validator set reductions), you can speculate on that rise by acquiring YT cheaply and selling it later at a premium once the market reprices expected returns.

This kind of forward-looking, yield curve arbitrage is common among sophisticated DeFi traders, and it can be magnified using leverage or integrated into broader treasury strategies.
