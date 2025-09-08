---
description: >-
  Nothing good is without it's risks. This page talks about the various risks
  that the protocol faces and how it addresses.
cover: ../../../.gitbook/assets/Apr23_28_1473717627.avif
coverY: -92.45393786127168
---

# The "Bank Run" Risk

Essentially, Rezerve is a protocol that is leveraged long on ETH with its own internal leverage design that allows it to maintain exposure to ETH while minimizing the effects of short-term volatility and liquidation risks. However, the most critical factor that determines the solvency of the protocol is the possibility of a [“Bank run.”](https://en.wikipedia.org/wiki/Bank_run)

If at any point the total USD value of ETH held as collateral drops below the total outstanding debt of the protocol, it becomes under-collateralized. This can occur due to sharp declines in ETH price, cascading sell pressure on $RZR (which is paired with ETH liquidity), or sudden lender withdrawals.&#x20;

If lenders believe their funds could face losses, they may rush to withdraw simultaneously—causing a self-reinforcing liquidity crisis known as a bank run.

## Scenarios that Could Trigger a Bank Run

1. **Short-Term ETH Volatility**: If ETH experiences a sudden price crash, the value of ETH collateral declines. Since $RZR liquidity is paired with ETH, its price tends to follow, leading lenders to doubt the protocol’s solvency.
2. **Sell Pressure on RZR**: Large sell-offs of RZR (whether from profit-taking, short-sellers, or external shocks) can extract liquidity and depress the token price. This reduces the collateral buffer, heightening the risk of under-collateralization.
3. **Sudden Liquidity Withdrawals:** If lenders collectively withdraw capital in a short period, the protocol may be forced to pay abnormally high interest rates to attract replacement capital. This further stresses reserves and increases the risk of insolvency.

## Lessons from Past Bank Runs

The most infamous bank runs that have happened in the crypto-sphere have been the following.

* **FTX Collapse (2022):** Once one of the largest crypto exchanges, FTX imploded after revelations of misused customer deposits and overexposure to illiquid assets like FTT. When confidence evaporated, mass withdrawals overwhelmed the exchange’s reserves, triggering insolvency ([FTX timeline, CoinDesk](https://www.coindesk.com/learn/ftx-collapse-a-timeline-of-the-exchanges-fall/?utm_source=chatgpt.com)). Also see the [FTX case study](the-ftx-case-study.md).
* **Celsius Network Collapse (2022):** Celsius promised outsized yields on deposits but was overexposed to risky loans and leveraged strategies. When markets turned bearish, users rushed to withdraw, only to find withdrawals frozen. The imbalance between liquid liabilities and illiquid assets led to bankruptcy ([Celsius case summary, Reuters](https://www.reuters.com/technology/crypto-lender-celsius-files-bankruptcy-protection-us-2022-07-13/?utm_source=chatgpt.com)). Also see the [Celsius Network case study](celcius-network-case-study.md).

These examples highlight how fragile systems can become when liquidity mismatches meet collapsing confidence.

## How Rezerve Mitigates Bank Run Risk?

Keeping all these various risks in mind, the protocol and it's designs have taken various steps from the very beginning of the protocol to mitigate these risks.

### 1/ A Focus on Convertible Notes

Incentives are designed to encourage lenders to lock their capital into long-duration convertible notes (up to four years). This creates predictability in borrowing and ensures a base cushion of capital that cannot be withdrawn during short-term volatility.&#x20;

Convertible notes also open a channel for accessing cheap, stable debt in both bull and bear conditions.

See [Convertible Notes](../convertible-notes.md).

### 2/ Continuous and Open Source Risk Simulations

The protocol continuous risk simulations taking into account worst-case scenarios and doomsday mechanics. The risk simulations can be found over [https://github.com/rezervemoney/risk](https://github.com/rezervemoney/risk)

Based on the risk simulations the protocol effectively makes decisions on how much leverage it can take over. The risk simulation evaluate dooms day scenarios so that the protocol can make the least riskiest decision.

### 3/ Transparency & Community Trust

A live public dashboard at [rezerve.money/risk](https://rezerve.money/risk) provides full visibility into collateralization ratios, leverage levels, and system health. This transparency builds trust, allowing the community to monitor risks in real time.

### 4/ Sufficient Leverage Management

The protocol carefully calibrates leverage to ensure that even in worst-case ETH crashes, collateral remains above debt obligations. This provides a buffer against sudden drawdowns.

### 5/ Protocol-Owned Liquidity (PoL) and Protocol-Owned Supply (PoS)

By controlling significant amounts of RZR supply and liquidity, Rezerve reduces reliance on mercenary liquidity providers and minimizes vulnerability to external sell pressure. PoL and PoS data are made publicly available at [rezerve.money/risk](https://rezerve.money/risk).

[https://rezerve.money/risk](https://rezerve.money/risk) showcases how much of the supply and liquidity that the protocol owns.

See [Protocol Owned Supply](../../protocol-driven-buybacks-pds/protocol-owned-supply.md) and [Protocol Owned Liquidity](../../protocol-driven-buybacks-pds/protocol-controlled-value-pcv.md) for more information.

## FAQs

### What makes Rezerve different from failed projects like FTX or Celsius?

Unlike FTX and Celsius, Rezerve is fully on-chain, transparent, and governed by open-source smart contracts. All positions and risks are visible in real time, preventing hidden leverage or off-balance-sheet liabilities.

The Rezerve model is very similar to MicroStrategy and enforces the transparency of the blockchain.

### What happens if ETH price crashes by 80% overnight?

The protocol’s risk simulations continuously stress-test for extreme drawdowns. Capital locked in long-duration convertible notes ensures a base reserve that cannot be withdrawn, providing a cushion to absorb shocks while leverage is adjusted dynamically.

The protocol never takes on a position if it estimates it can be at risk of a downturn.

### Can lenders withdraw at any time?

Yes, for flexible lending products, withdrawals are possible, but most incentives encourage long-term locks via convertible notes. This reduces the risk of sudden mass withdrawals.

### How is the protocol incentivized to remain solvent?

Rezerve owns significant portions of its own liquidity and token supply (PoL and PoS). This means the protocol’s sustainability directly depends on maintaining solvency and trust.

### Where can I track the health of the protocol?

You can view real-time metrics on collateral, leverage, and liquidity at [rezerve.money/risk](https://rezerve.money/risk).
