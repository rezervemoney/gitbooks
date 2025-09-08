---
description: >-
  This page talks a bit about the Infinite Money Glitch and how Rezerve raises
  debt to capture as much as ETH as possible.
---

# The Infinite Money Glitch

Rezerve’s so-called Infinite Money Glitch has quickly become one of the core functionalities of the protocol. At its core, it is a clever repurposing of a time-tested TradFi instrument—the [convertible bond](raising-debt-and-acquiring-eth/convertible-notes.md)—reimagined in the language of stablecoins, on-chain liquidity, and protocol incentives.

## How It Works

When you stake USD assets on Rezerve, your capital immediately start earning yield for your deposit. The longer you stake your USD, the more yield you'll get it.

But that’s not all. Each stake is effectively a convertible bond on-chain. If the price of RZR rallies, your staked USDC can be converted into RZR at a pre-set discount, giving you equity-like upside on top of your base yields.

When you convert your position into RZR, the underlying assets you had initially committed goes back to the protocol which is then used to write off it's debt.&#x20;

To learn more about Rezerve's convertible bonds, see [Convertible Bonds](raising-debt-and-acquiring-eth/convertible-notes.md).

## Why It’s Called the “Infinite Money Glitch”

The reason this has been branded an “Infinite Money Glitch” is not because it defies economics, but because of the reflexive feedback loop it sets in motion. The protocol recycles staked USDC into ETH, which is then used to deepen liquidity for RZR pairs.&#x20;

In a bullish market, ETH appreciates in value, increasing the effective liquidity backing RZR. This deeper liquidity attracts more trading, more stability, and more demand for RZR. As demand grows, so does the market price of RZR. Since stakers hold the right to convert USDC positions into RZR at a discount, their option becomes increasingly valuable.&#x20;

This creates a self-reinforcing cycle: ETH pumps → liquidity strengthens → RZR rallies → conversion upside increases → staker demand rises → more USDC flows in.

## What happens during a bear market?

In a bear market, the Infinite Money Glitch is designed to shift from reflexive growth to resilience. Instead of relying solely on rising ETH or increasing demand for RZR, the protocol prepares by maintaining a deep cushion of USD-denominated capital locked in convertible notes with longer maturities.&#x20;

These positions, committed for months or even years, cannot be withdrawn prematurely, which ensures the protocol retains a stable reserve of funds even when short-term sentiment turns negative. This locked capital acts as a protective buffer, allowing the system to honor yields and manage liquidity obligations without being forced into distressed asset sales.&#x20;

In practice, it means that while upside exposure may diminish in a downturn, the protocol’s core structure remains intact—anchored by predictable, stablecoin based commitments that smooth volatility and provide a foundation for eventual recovery when markets turn bullish again.

See the ["bank run"](raising-debt-and-acquiring-eth/the-bank-run-risk/) risk for more information on how th protocol simulates these scenarios and prepares to raise enough convertible notes.
