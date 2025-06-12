---
description: Allocation Engine in a Nutshell
---

# Staking Ratio - ρ

The Greek letter ρ (rho) stands for the staking ratio—the fraction of circulating RZR that is locked in the staking contract

$$
\rho =\frac{\text{Staked RZR}}{\text{Circulating RZR}}
$$

ρ is the thermostat of the protocol: when most tokens are staked, the system can divert more revenue to hard collateral; when few are staked, it must incentivize holders to stake with richer yields.

## Dynamic cash-flow split

Every dollar that enters the protocol (bonds, Harberger taxes, swap fees) is split three ways:

| Bucket         | Formula                                                    | Purpose                      |
| -------------- | ---------------------------------------------------------- | ---------------------------- |
| Floor-Escrow   | $$f(\rho)=\min\bigl(15\%+50\%\!\times\!\rho,\;50\%\bigr)$$ | Secures the hard floor (RFV) |
| Staker Rewards | $$s(\rho)=1-f(\rho)-10\%$$                                 | Fuels headline APR           |
| Ops Wallet     | 10% fixed                                                  | Bribes, audits, integrations |

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption><p>How the staking ratio influences the yield allocation between stakers and raising the floor price</p></figcaption></figure>

**Orange curve – Floor-Escrow % -** _Starts at 15 % when almost nobody is staked, then rises linearly as ρ climbs, but caps at 50% once staking exceeds 70%._ This slice is wired straight to increase the price hard floor for RZR (see [Price Hard Floor](../price-hard-floor.md))

**Red curve – Staker-Rewards % -** Because the ops bucket is fixed at 10 %, whatever isn’t orange (Floor-Escrow) becomes red. _When ρ is low the red band is widest (≈ 75 %), showering more yield on stakers; as ρ rises the red band narrows, bottoming at ≈ 40 % once Floor-Escrow hits its cap._

**Grey dotted line – Operations 10 % -** A constant strip that funds veDEX bribes, audits and integration grants; it never changes with ρ.

## Why this matters

- **Self-balancing -** If staking participation dries up, yields spike automatically, drawing tokens back into the vault.
- **Exponential floor growth -** When almost everyone is staked, half of every dollar races straight to the stable-escrow, letting the hard floor climb as fast as supply.
- **Predictable runway -** A constant 10 % ops slice guarantees treasury fuel for veDEX bribes and audits no matter where ρ sits.

In short, the diagram visualises how the protocol automatically tilts more revenue toward hard collateral when most holders are already committed (high ρ), and tilts more toward juicy staking rewards when participation lags (low ρ). The Floor-Escrow is the orange engine behind every future “Floor raised to $1.23” banner.

## An Example Simulation

We start with 1,000,000 RZR, a floor-oracle price $$F_0 = \$1.00$$, and let one dollar of new value flow into the protocol every block (≈ $10 000 day for illustration).

Each day the controller

1. Allocates the inflow according to the rule
   1. $$f(\rho)=\min(15\%+50\%\rho,\;50\%)$$ → how much RZR the floor should increase by
   2. $$s(\rho)=0.90-f(\rho)$$ → how much RZR stakers mint
2. Rebases the base supply at ≈ 500 % APR (≈ 1.37 % day),
3. Mints $$s(\rho)\times\text{inflow}\,/\,F_t$$ straight to stakers,
4. Lifts the internal floor by $$(\text{floor slice})/\text{supply}.$$

The table shows end-of-year results for three fixed staking-ratios ρ.

| ρ (staking ratio) | Floor after 365 d | Supply after 365 d | Inflation driver                                   | Floor driver                    |
| ----------------- | ----------------- | ------------------ | -------------------------------------------------- | ------------------------------- |
| 0.20 (low)        | $1.15             | 206 M RZR          | Huge staker mint (≈ 75 % of inflow) + 500 % rebase | Only 17 % of inflow lifts floor |
| 0.50              | $1.25             | 190 M RZR          | Balanced mint vs. rebase                           | 35 % of inflow to floor         |
| 0.80 (target)     | $1.33             | 179 M RZR          | Smallest extra mint; rebase still 500 % APR        | Max 50 % of inflow to floor     |

Reading the outcome

- When ρ is low the system throws most dollars at stakers, so supply explodes while the floor inches up only \~15 %.
- At the target 80 % ratio the floor price climbs by a third in a year even though the base rebase keeps churning; supply still grows 180× but not the 200×-plus seen at lower ρ.
- Thus the allocation rule self-balances: as more holders stake, extra dollars shift to the oracle floor, letting both intrinsic value and circulating supply rise exponentially—without one outrunning the other.

This illustrates how RZR can pursue aggressive yield yet still push its guaranteed price floor upward simply by modulating the split with the staking ratio ρ, no USDC escrow required

## Case Study—When Everyone Stakes: OlympusDAO vs. Ethena

In this section we analyze two stablecoin ecosystems and compare how they've grown.

### OlympusDAO

<figure><img src="../../.gitbook/assets/image (5).png" alt=""><figcaption><p>99% of OHM is currently staked, making holding unstaked OHM unattractive and OHM lifespan short - <a href="https://defillama.com/protocol/olympus-dao?treasury=false">https://defillama.com/protocol/olympus-dao?treasury=false</a></p></figcaption></figure>

From late-2021 onward Olympus’ “(3, 3)” meme convinced almost every holder to lock up tokens for rebasing yield. Analytic snapshots put the staking ratio above 90 % and at times above 91 % of the circulating supply—one of the highest in crypto. With scarcely 8-10 % of OHM liquid, most real-world uses—DEX collateral, payment rails, governance delegation—were starved of inventory.

The token’s only visible purpose became _staking to protect oneself from dilution_, so fresh demand hinged on new buyers repeating the same behaviour. Even after Olympus slashed its APY to a single-digit 7.35 % in 2023, the sticky staking reflex lingered, leaving the liquid OHM market thin and volatile. The protocol achieved its goal of deep “commitment,” but at the cost of everyday utility: merchants, LPs and lenders could not source enough unstaked OHM to build services.

### Ethena (USDe / sUSDe)

Ethena’s synthetic dollar tells a similar but softer story. By February 2025 USDe’s supply rocketed past $6 billion, with “over 60 %” immediately restaked as sUSDe to farm funding-rate yield ￼. Activity graphs on DefiLlama show most swaps, bridges and lending pools centre on the yield-bearing sUSDe wrapper, while vanilla USDe turnover is modest.

The bias is less extreme than Olympus—roughly a 40 : 60 liquid-to-staked split—so USDe still circulates on CEXes and as collateral on perp platforms, but every uptick in yield pushes more holders to convert to sUSDe, gradually hollowing out the free-floating float.

### Why RZR Outshines the “All-Stake” Models

OlympusDAO proves that a ­>90 % staking ratio can starve a token of real-world utility, while Ethena shows that drifting above \~60 % shifts nearly all activity into its yield-bearing wrapper. RZR solves this crowding-out effect with a dynamic split that uses the staking ratio ρ as a throttle: when ρ is low, 65 % of every inbound dollar is paid out as yield to entice deposits;

When ρ is high, up to 50 % is siphoned into the Floor-Escrow, pushing the risk-free floor upward and throttling emissions. This self-balancing engine keeps a healthy liquid float, lets RFV per token and supply grow in tandem, and leaves a constant 10 % ops budget for bribes and integrations—creating a token that is simultaneously yield-rich and widely usable as collateral or medium of exchange.

| Feature                   | OlympusDAO (OHM, peak 2022) | Ethena (USDe, Q1-2025)     | RZR                                                    |
| ------------------------- | --------------------------- | -------------------------- | ------------------------------------------------------ |
| Typical staking ratio     | 90 – 92 %                   | ≈ 60 %                     | Auto-target 40 – 70 % via ρ-based split                |
| Liquid float              | < 10 % of supply            | \~40 %                     | Always ≥ 30 % (by design)                              |
| Floor mechanism           | RFV ≥ $1 (static)           | None (soft peg to funding) | Hard floor that ratchets up 1 % whenever surplus ≥ 5 % |
| Yield design              | Fixed rebase (now 0 %)      | Funding-rate passthrough   | 500 % – 2 000 % APR capped, tied to β                  |
| Inbound-dollar allocation | 100 % to treasury / stakers | Mostly to sUSDe vault      | 25 % floor, 65 % stakers, 10 % ops — dynamic with ρ    |
| Collateral appeal         | Thin market, low LTV        | Moderate LTV (sUSDe only)  | Rising floor + liquid float → high LTV for raw RZR     |

In short, RZR combines Olympus-style reserve building with Ethena-style yield harvesting, then adds an adaptive cash-flow splitter so neither utility nor intrinsic value is sacrificed—delivering a reserve currency that stays liquid, solvent and attractive across market cycles.
