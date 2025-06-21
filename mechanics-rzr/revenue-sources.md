---
description: >-
  This page goes into detail about how the protocol generates revenue and how
  revenue is distributed
---

# Revenue Sources

Revenue is a crucial component for any protocol. In Rezerve, revenue is directly translated to newly minted RZR towards stakers and a [rising floor price for RZR](yield-mechanics/price-hard-floor.md).

To this note, there are five independent sources of revenue that the protocol genreates fees from.

### **Trading fees on protocol-owned liquidity**

The DAO owns the majority of its RZR-USDC and RZR-ETH liquidity positions on DEXes.  Because the pools are deliberately concentrated around the prevailing price, they generate 2–10 bp per trade and capture most of the market’s swap volume. &#x20;

Fees accrue in real time, are auto-compounded into the position, and then streamed to the treasury at epoch boundaries as raw USDC/ETH.  This “always-on market-making desk” provides depth for traders while paying the protocol for the service.

### **Bond sales (discounted inflow)**

When the market price trades above the hard floor, users can deposit USDC, BTC-DRE LP or other whitelisted assets and receive DRE at a modest 5-20 % discount. &#x20;

The full deposit is credited to the treasury on day 0, while the discounted DRE vests over twelve days.  In high-premium environments bond flow is the largest single influx of new collateral, driving the backing ratio β higher and unlocking richer staking APRs.

### **Lending-market revenue**

A slice of idle stable reserves is supplied to low-risk money markets such as Aave, Morpho or Spectra vaults, earning organic lending yield (typically 3–6 % APY on stables). &#x20;

Allocation is capped at 25% of stable PCV and can be recalled within one block through flash-repay guardians.  This “lazy cash” layer covers operational gas costs and cushions APR when bond demand is quiet.

### **DEX-partner emissions (“external bribes”)**

By seeding POL on veToken DEXes, the DAO qualifies for weekly emissions of the venue’s native token (VELO, PENDLE, etc.).  Two-thirds of the farmed tokens are market-sold for stables and routed into the floor-price ratchet; the remaining third is recycled as bribes to keep gauge weight pointed at the DRE pairs.  This flywheel subsidises deeper liquidity without selling extra DRE.

### **Harberger-tax stream**

All staked positions self-declare a valuation and prepay a 5 % annual “ownership tax.”  The tax drips into the treasury block-by-block, giving the protocol a bond-independent income floor even when trading volumes are thin. &#x20;

Because users can be bought out if they understate, the mechanism stays honest while producing a predictable cash trickle.

Furthermore bond purchases also charge a 1% trading fee which goes towards the rising floor price.

See [staking RZR](staking-rzr-srzr/) and [Harberger taxes](revenue-sources.md#harberger-tax-stream).

## How the streams converge?

Every eight-hour epoch the controller tallies new US-dollar value from _all_ four sources, feeds it to the ρ-splitter (50 % to floor at 80 % staking, 40 % to stakers, 10 % ops) and then reassesses the backing ratio β. &#x20;

If inflows beat the previous epoch’s inflation cost, the oracle floor ticks one percent higher.  Over time this design lets the floor, the staking yield and the treasury balance climb in lock-step—trading fees and emissions cover the bear market, bond sales capture the bull, and lending yield smooths the cycle in between.
