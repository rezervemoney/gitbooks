---
description: How Rezerve uses DeFi and smart contracts to reach it's goal of 1 million ETH
---

# The Rezerve Approach

Similar to how MicroStrategy tapped into traditional markets and structured notes to raise capital, Rezerve relies on DeFi to do the same. This is achieved through two core mechanisms:

1. On-Chain Bonds — short-term discounted ETH accumulation.
2. Lending Protocols — leveraging assets to borrow capital for further growth.

This dual strategy mirrors successful accumulation models from traditional finance—like MicroStrategy’s leveraged Bitcoin purchases—but adapts them to DeFi’s decentralized, transparent, and programmable environment.&#x20;

Rezerve then uses this newly acquired ETH to provide liquidity to the RZR token, allowing investors to get enough liquidity to enter/exit from the ecosystem further increasing the loop.

{% hint style="info" %}
To dive deeper into the Rezerve feedback loop, see [Infinite Money Glitch](../mechanics-rzr/the-infinite-money-glitch.md).
{% endhint %}

<figure><img src="../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

### 1. Convertible Bonds

Rezerve issues on-chain convertible bonds—tokenized instruments that allows the protocol to raise debt and give lenders the option to convert their debt into RZR tokens at a later price.

Investors purchase bonds with any liquid asset they have. In return, they receive RZR at a discounted rate. Rezerve does bond sales on it's own interface over at [Rezerve.money](https://rezerve.money/).

#### **Benefits:**

* **ETH Accumulation:** Every bond purchase increases Rezerve’s ETH treasury.
* **Price Support:** Lenders are given the option to convert to RZR at a higher price (reducing sell pressure to the protocol)

### 2. Lending Protocols

In addition to bonds, Rezerve uses decentralized lending markets (such as Aave or Euler equivalents on supported chains) to borrow capital against its assets.

RZR is first deposited into lending protocols as collateral. The Rezerve protocol then borrows stablecoins or other liquid assets at low interest rates. The borrowed capital is used to purchase more ETH, increasing the reserve size.

To enable this to happen, Rezerve needs to work with lending protocols that accept RZR as collateral and has lenders to lend USDC to it. Which is why the Rezerve protocol actively curates vaults on [Morpho](https://morpho.org/) and [Euler](https://euler.finance/).

#### **Benefits:**

* **Capital Efficiency:** Retains existing treasury assets while deploying additional liquidity.
* **Growth Acceleration**: Allows the protocol to accumulate ETH faster than organic inflows alone.
* **Market Resilience**: Strategic use of borrowing during favorable market conditions enhances returns.

## Economical Risks

Both of these methods of raising capital comes with it's own set of economical risks.

* **Market Volatility & ETH Price Risk:** Since the treasury is primarily denominated in ETH, a significant drop in Ethereum’s price can reduce the protocol’s reserve value and impact market confidence or cause liquidations. This is especially relevant during highly leveraged positions acquired via lending protocols.
* **Bond Discount Dilution:** While discounted bonds are a tool for ETH accumulation, excessive discounting or poorly timed bond issuances could create sell pressure on RZR, reducing price stability and harming long-term holder confidence.
* **Liquidation Risk from Borrowing:** When borrowing capital using ETH or other assets as collateral, price volatility can trigger liquidations. This can result in forced asset sales at unfavorable prices, reducing the reserve and harming the protocol’s growth trajectory.
* **Liquidity Constraints in DeFi Markets:** Using lending protocols and bond sales depends on deep and reliable liquidity. In times of market stress, liquidity can dry up, leading to higher borrowing costs, reduced bond demand, or inability to execute key strategies efficiently.

Managing risk is a key factor in ensuring that the protocol does not face any kind of bad debt.
