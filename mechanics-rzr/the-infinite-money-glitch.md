---
description: >-
  This page talks a bit about the Infinite Money Glitch and how Rezerve raises
  debt to capture as much as ETH as possible.
cover: ../.gitbook/assets/fantasy-pepe-meme-1-e1746010371886.jpg
coverY: 0
---

# The Infinite Money Glitch

Rezerve’s so-called Infinite Money Glitch has quickly become one of the core functionalities of the protocol. At its core, it is a clever repurposing of a time-tested TradFi instrument, the [convertible bond](raising-debt-and-acquiring-eth/convertible-notes.md), reimagined in the language of stablecoins, on-chain liquidity, and protocol incentives.

## How Does It Work?

When users stake stablecoins into Rezerve’s [convertible bonds](raising-debt-and-acquiring-eth/convertible-notes.md), they are effectively lending the protocol debt capital that can be deployed to acquire more ETH. The protocol, while taking into account various risk parameters, ensures that it borrows the stablecoins and buys ETH in a safe and measured way based on its [leverage profile](raising-debt-and-acquiring-eth/leverage-logic.md).

The bought out ETH is then added into RZR liquidity strengthening price and deepening RZR liquidity.

As ETH appreciates in value, the price of RZR also rises. This appreciation gives bond-holders the option to convert their bonds into RZR. When a conversion takes place, the stablecoins that were originally deposited by the user are transferred to the protocol. The protocol then uses these stablecoins to reduce or write off its outstanding debt.

This mechanism creates a powerful cycle: the protocol maintains and grows its ETH exposure, users can exit the system seamlessly through conversion, and any debt on the protocol’s balance sheet gets cleared in the process.&#x20;

In short, it’s a win-win structure that strengthens the protocol while rewarding participants.&#x20;

## Why It’s Called the “Infinite Money Glitch”?

The reason this has been branded an “Infinite Money Glitch” is not because it defies economics, but because of the reflexive feedback loop it sets in motion. The protocol recycles staked USD stablecoins into ETH, which is then used to deepen liquidity for RZR pairs.

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

In a bullish market, ETH appreciates in value, increasing the effective liquidity backing RZR. This deeper liquidity attracts more trading, more stability, and more demand for RZR. As demand grows, so does the market price of RZR.

Since stakers hold the right to convert USDC positions into RZR at a discount, their option becomes increasingly valuable.

This creates a self-reinforcing cycle: ETH pumps → liquidity strengthens → RZR rallies → conversion upside increases → staker demand rises → more USDC flows in.

## What happens during a bear market?

In a bear market, the Infinite Money Glitch is designed to shift from reflexive growth to resilience. Instead of relying solely on rising ETH or increasing demand for RZR, the protocol prepares by maintaining a deep cushion of USD-denominated capital locked in convertible notes with longer maturities.

These positions, committed for months or even years, cannot be withdrawn prematurely, which ensures the protocol retains a stable reserve of funds even when short-term sentiment turns negative. This locked capital acts as a protective buffer, allowing the system to honor yields and manage liquidity obligations without being forced into distressed asset sales.

In practice, it means that while upside exposure may diminish in a downturn, the protocol’s core structure remains intact—anchored by predictable, stablecoin based commitments that smooth volatility and provide a foundation for eventual recovery when markets turn bullish again.

See the ["bank run"](raising-debt-and-acquiring-eth/the-bank-run-risk/) risk page for more information on how the protocol simulates these scenarios and prepares to raise enough convertible notes.
