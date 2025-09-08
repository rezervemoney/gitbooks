---
description: >-
  This page goes into detail on how the protocol decides how much to borrow and
  at what LTV to borrow at.
---

# Leverage Logic

Traditional lending engines in DeFi are designed with immediate liquidation triggers. If collateral value drops below a healthy loan-to-value (LTV) ratio, the system liquidates positions on the spot market to protect lenders. While this works for short-term solvency, it makes protocols highly sensitive to volatility and forces them to sell off assets at the worst possible times.

Rezerve’s leverage system is designed differently. Instead of relying on instant liquidation, it allows the protocol to remain under-collateralized for a fixed duration of time. This is made possible because lender liquidity is committed through convertible notes that cannot be withdrawn early.

<figure><img src="../../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

As a result, Rezerve can ride through short-term volatility without being forced into distressed liquidations.

## An Example

For example, suppose the protocol deposits $100,000 of ETH as collateral and borrows $80,000 of assets against it at 80% LTV. In addition, it has $50,000 in convertible notes, which act as locked USD-denominated reserves.

In a traditional leverage system, only the ETH collateral is counted, so if ETH drops 10% (to $90,000), the LTV spikes dangerously close to liquidation (88%).

| Parameter         | Value / Behavior                                                                    |
| ----------------- | ----------------------------------------------------------------------------------- |
| Collateral Type   | Typically volatile assets (e.g., ETH)                                               |
| Collateral Amount | $100,000 in ETH                                                                     |
| Borrowed Amount   | $80,000                                                                             |
| Initial LTV       | 80%                                                                                 |
| If ETH Drops 10%  | Collateral falls to $90,000                                                         |
| New LTV           | 88% (close to liquidation threshold)                                                |
| Liquidation Rule  | Immediate liquidation once LTV exceeds threshold (e.g., 80%)                        |
| Consequence       | Forced asset sale at depressed prices, crystallizing losses and shrinking liquidity |

But in Rezerve’s design, the collateral base includes both ETH and convertible notes, so the new collateral is $90,000 in ETH + $50,000 in notes. Because the notes are USD-stable, they don’t lose value during ETH volatility. The LTV after the same ETH drop is only 57%, leaving plenty of room before stress levels are reached.

| Parameter         | Value / Behavior                                                                          |
| ----------------- | ----------------------------------------------------------------------------------------- |
| Collateral Type   | ETH + Convertible Notes (USD-backed)                                                      |
| Collateral Amount | $100,000 in ETH + $50,000 in convertible notes                                            |
| Borrowed Amount   | $80,000                                                                                   |
| Initial LTV       | 53%                                                                                       |
| If ETH Drops 10%  | ETH collateral falls to $90,000, but convertible notes remain $50,000                     |
| New Collateral    | $90,000 (ETH) + $50,000 (Notes) = $140,000                                                |
| New LTV           | 57% (still far below liquidation threshold)                                               |
| Liquidation Rule  | No forced liquidation; protocol remains solvent through volatility                        |
| Consequence       | Greater resilience, more predictable liquidity, stability during short-term ETH drawdowns |

This approach allows the protocol to take on leverage more sustainably, since the convertible notes provide a stabilizing floor of value that smooths out ETH’s volatility.

## Infinite Minting and Risk Controls

Technically, Rezerve can mint infinite RZR and put it into lending protocols as collateral. This means that the protocol can never be force-liquidated in the way traditional DeFi lending positions can.

However, solvency is not about minting power alone—it depends on whether the protocol has enough real liquidity (ETH, USD reserves, and convertible note backing) to meet obligations without triggering a bank run.

That’s why leverage logic in Rezerve is built on two guiding constraints:

1. **Available Liquidity in the Books:** The system continuously tracks how much borrowable liquidity exists in lending markets where RZR is posted as collateral. This determines the real borrowing capacity at any given moment.
2. **Liquidity Locked in Convertible Notes:** Since convertible notes cannot be withdrawn early, they act as guaranteed backing. The more USD is locked in notes, the higher the tolerance the protocol has for ETH volatility before solvency is threatened.

## Why This Matters?

By combining ETH collateral with USD-denominated convertible notes, Rezerve creates a blended collateral model that reduces sensitivity to short-term crashes. Where traditional systems would trigger mass liquidations at high volatility, Rezerve can “hold its breath” through drawdowns, giving the system breathing room to recover.

This doesn’t mean risk is eliminated. If ETH enters a prolonged bear market or if sell pressure on RZR overwhelms liquidity, the protocol still faces solvency challenges. But with structured notes, risk simulations, and transparent dashboards, the system is designed to keep leverage at sustainable levels.

For more detail, you can review live risk dashboards at [rezerve.money/risk](https://rezerve.money/risk) and explore open-source risk simulations at [github.com/rezervemoney/risk](https://github.com/rezervemoney/risk). You can also see the risk measures the protocol takes to [prevent the bank run risk](the-bank-run-risk/).

Together, these constraints allow the protocol to calculate how much ETH exposure it can safely take on from lending markets, balancing growth against risk.

## Case Study: MicroStrategy & the Bitcoin Crash of 2021

When Bitcoin experienced a steep decline in 2021, MicroStrategy’s bold strategy of amassing BTC via convertible debt came under intense scrutiny. Here’s how the company navigated the downturn and what lessons can be drawn.

Under CEO Michael Saylor, MicroStrategy transformed from a business intelligence company into a self-styled “Bitcoin Treasury Company,” accumulating a massive BTC position through convertible notes and equity financing. By late 2024, the firm held hundreds of thousands of BTC, financed via low-interest, convertible senior notes, some even carrying a 0% coupon .

While this strategy delivered massive upside in bull markets, it exposed the company to significant risk during downturns. In mid-2021, Bitcoin’s value plunged, causing MicroStrategy to record major asset-impairment charges over $180 million in one quarter and additional potential losses forecasted in the follow-up.

Despite these losses, MicroStrategy avoided insolvency. Here’s how:

- **Comfortable Margin Levels:** Their debt was structured to avoid margin calls even if BTC dropped significantly. The company stated it would face a margin call only if Bitcoin fell to approximately $21,000. When prices briefly flirted with that zone in June 2022, no margin call occurred thanks to sufficient collateral and liquidity buffers.
- **Convertible Debt Buffer:** Convertible notes provided financing flexibility and delayed dilution. As long as the stock didn’t collapse, investors holding these debt instruments didn’t force liquidity demands in the midst of volatility.
- **Strategic Patience**: MicroStrategy did not panic-sell BTC to cover its debt obligations. The firm demonstrated confidence in its long-term thesis and held through the downturn.

While the crash inflicted billion-dollar paper losses (reported at over $1.2 billion) ￼, MicroStrategy’s solid liquidity planning and strategic debt structure allowed it to remain solvent and positioned for recovery when market sentiment improved.

Read More:

- [Billionaire Saylor's MicroStrategy Loses over $1.2 Billion in the Bitcoin Crash](https://www.thestreet.com/crypto/investing/billionaire-saylors-microstrategy-loses-over-1-2-billion-in-the-bitcoin-crash?)
- [Will MicroStrategy Go Bankrupt if Bitcoin Keeps Falling?](https://marketrealist.com/p/will-microstrategy-go-bankrupt/?)
- [What Does Strategy (Formerly MicroStrategy) Do and Why Does It Hold So Much Bitcoin?](https://www.investopedia.com/what-does-strategy-formerly-microstrategy-do-11750239?)
