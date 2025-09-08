---
description: How the protocol uses convertible notes to raise debt to buy ETH
---

# Convertible Notes

{% hint style="success" %}
[Convertible bonds](https://en.wikipedia.org/wiki/Convertible_bond?utm_source=chatgpt.com) is an improvement over the previously implemented [Discounted Bonds](../bonds.md) and is now the primary source of new liquidity for the protocol.&#x20;
{% endhint %}

Rezerve’s convertible bonds are structured financial instruments that combine the stability of debt with the potential upside of equity. Investors purchasing these bonds are essentially lending to Rezerve, receiving periodic coupon payments like traditional bonds. However, what distinguishes them is the embedded option: holders can convert their bonds into Rezerve’s native token RZR under predefined conditions.

This design serves two main purposes:

1. **Capital Raising Flexibility:** Rezerve secures funding without immediately diluting token supply, while still providing investors an equity-like upside if the project performs well.
2. **Risk Management for Investors:** Bondholders enjoy downside protection through fixed income returns, while retaining the option to convert into tokens if market appreciation makes it more profitable.

### Convertible Notes in Traditional Markets

{% embed url="https://www.youtube.com/watch?v=PtTDmeU-Kok" %}

In traditional financial markets, convertible notes are regarded as hybrid instruments that straddle the line between debt and equity. They are initially issued as bonds, meaning they carry an obligation to pay periodic interest and repay principal at maturity.&#x20;

What makes them distinct is the built-in option for bondholders to convert their holdings into equity, usually at a predetermined conversion price or at a discount to the prevailing market price of the shares. This dual nature allows companies to borrow capital at lower interest rates than straight debt, since investors also gain the potential upside of equity appreciation.

Startups have historically used convertible notes as a way to sidestep valuation negotiations in the early stages. Instead of fixing a valuation too early, they allow investors to lend money with the promise that the loan may convert into equity when a priced funding round occurs.&#x20;

For mature corporations, convertible notes provide a more flexible financing structure, enabling access to cheaper capital than traditional debt, while postponing immediate equity dilution. Academic and market literature often cite them as a financing tool that balances investor risk protection with issuer flexibility.

See:

* [Convertible bond - Wikipedia](https://en.wikipedia.org/wiki/Convertible_bond?utm_source=chatgpt.com)
* [Convertible note by Thomson Reuters](https://legal.thomsonreuters.com/blog/convertible-note-legal-glossary/)

### MicroStrategy’s Use of Convertible Notes

{% embed url="https://www.youtube.com/watch?v=ae_eNJRbDdU" %}

MicroStrategy provides a striking contemporary example of how these instruments can be deployed in non-traditional ways. Beginning in late 2020, the company issued several rounds of senior unsecured convertible notes, raising billions of dollars.&#x20;

For example, [in December 2020](https://www.sec.gov/Archives/edgar/data/1050446/000119312521020760/d92691dex991.htm?utm_source=chatgpt.com) it issued $650 million of 0.75% convertible senior notes due 2025, followed by a $1.05 billion issuance of 0% convertible senior notes due 2027 in early 2021.&#x20;

What truly distinguished this issuance was the use of proceeds: rather than reinvesting in its enterprise software business, MicroStrategy used nearly all of the raised capital to purchase Bitcoin. This aggressive strategy positioned MicroStrategy as a leveraged proxy for the cryptocurrency, with its stock price closely tracking Bitcoin’s performance.

See:

* [How MicroStrategy leverages debt to accumulate Bitcoin (BTC)](https://cointelegraph.com/learn/articles/how-microstrategy-leverages-debt-to-accumulate-bitcoin?utm_source=chatgpt.com)
* [MicroStrategy proposes $500 million convertible note offering to acquire more bitcoin](https://www.theblock.co/post/299943/microstrategy-proposes-500-million-convertible-note-offering-to-acquire-more-bitcoin?utm_source=chatgpt.com)

## The Rezerve Method to Convertible Bonds

While traditional convertible notes rely on equity conversion and MicroStrategy’s version relies on stock exposure to Bitcoin, Rezerve adapts the logic of convertibles into the stablecoin and DeFi context. Instead of bonds denominated in fiat or equity shares, users allocate stablecoins into a structured system that produces multiple layers of yield.&#x20;

<figure><img src="../../.gitbook/assets/image (13).png" alt=""><figcaption><p>The Rezerve way of staking stablecoins to get decentralized convertible notes.</p></figcaption></figure>

Visit [https://rezerve.money/lend](https://rezerve.money/lend) to see more information about the convertible notes

### 1/ Multiple Yield Sources

When users deposit stablecoins into Rezerve, they gain access to three distinct tranches of yield.&#x20;

* A fixed yield in stablecoins
* A dynamic yield from lending markets paid in stablecoins.
* A dynamic incentive yield paid in RZR

The longer users choose to lock their stablecoins, the more favourable the yield becomes and the lower the conversion price becomes.

| Property         | 1 Month Lock         | 12 Month Lock | 48 Month Lock       |
| ---------------- | -------------------- | ------------- | ------------------- |
| Conversion Price | 52 RZR/USD (Highest) | 43 RZR/USD    | 15 RZR/USD (Lowest) |
| Net Yield Earned | 11% (Lowest)         | 22%           | 62% (Highest)       |

The table above illustrates the various benefits to users who stake their assets for longer periods of time. The values above are for illustration purposes only.

### 2/ NFT Positions

In Rezerve, user positions are not simply account balances inside a protocol contract; they are instead represented as non-fungible tokens (NFTs).&#x20;

Each NFT encapsulates the full details of a user’s allocation such as the lock duration, the amount of stablecoins deposited, the yield accrued, and the option to convert into $RZR at maturity or trigger events.

Meaning users now further trade their lock positions on secondary marketplaces like OpenSea.

### 3/ Dynamic Lock Durations

Rezerve introduces dynamic lock durations as a mechanism for aligning user incentives with the stability of the protocol. Instead of imposing a single fixed lock-up period, users can choose to stake their assets for any duration ranging from 1 month to 48 months.&#x20;

Shorter lock-ups, such as one or three months, appeal to users who value liquidity and want quicker access to their funds. These users accept lower yield in exchange for flexibility. On the other end of the spectrum, participants who commit to longer horizons (up to four years) signal stronger conviction in the protocol’s future and willingness to forgo liquidity. In return, they are rewarded with higher yields and more favorable terms, reflecting the added value their stability brings to the system.

{% embed url="https://streamable.com/k60t9z" %}

From the protocol’s perspective, longer commitments enhance borrowing predictability. When assets are locked for extended periods, the system can more confidently allocate capital toward lending, liquidity provision, and yield strategies without the risk of sudden withdrawals.&#x20;

This reduces liquidity risk and allows the protocol to design more efficient lending and liquidation mechanisms. In essence, long-term locks function as a stabilizing anchor, much like long-term bondholders in traditional finance.

## Conclusion

Whether you’re looking for short-term flexibility or long-term yield maximization, Rezerve’s structured approach to lending and dynamic lock durations makes it easy to find a strategy that fits your goals.&#x20;

Explore the different lock periods, and see how your returns can grow. Get started today by visiting [rezerve.money/lend](https://rezerve.money/lend) and trying out our interactive calculator to design the lending position that works best for you.
