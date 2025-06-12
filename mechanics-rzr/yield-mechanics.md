---
description: >-
  This section explains how the yield mechanics work for the RZR and how it's
  different from the OHM model
---

# Yield Mechanics

Below is a step-by-step “token-flow ledger” that shows exactly where RZR's yields come from, where they go, and why they can more sustainable than OlympusDAO’s model.

## OlympusDAO Recap

We'll start with a 60-second refresher on OHM mechanics, then layer-in the Harberger-tax twist to undertand how the system is different.

| Symbol              | What it is                   | Typical 2021 value                |
| ------------------- | ---------------------------- | --------------------------------- |
| $$PCV_t$$           | Treasury assets at epoch t   | $500 M (stablecoins + LP)         |
| $$S_t$$             | Total OHM supply             | 17 M                              |
| $$sS_t$$            | Staked supply (≈ 97 %)       | 16.5 M                            |
| $$B_t$$             | New bond deposits this epoch | $3 M                              |
| $$r\_\text{epoch}$$ | Rebase reward rate           | 0.35 % per 8 h → 20 K % APY       |
| $$\Delta S_t$$      | OHM minted to stakers        | sS\_{t-1}\times r\\\_\text{epoch} |

When OHM trades at a fat premium to its backing, discounted bonds become ultra-profitable, so $$B_t$$ soars → Treasury swells → policy can maintain (or even raise) $$r_\text{epoch}$$ without breaching the 1 OHM ≥ $1 backing rule.

In effect speculative inflows are alchemised into rebase yield.

## RZR – adding a Harberger-tax fuel line

| Symbol           | What it is                        | Default                                   |
| ---------------- | --------------------------------- | ----------------------------------------- |
| $$H_t$$          | Harberger-tax inflow this epoch   | Declared-value × 5 % APR × (epoch length) |
| $$r_\text{max}$$ | Initial reward rate (5000 % APR)  | 0.359 % per epoch                         |
| $$r_\text{min}$$ | Floor rate (1000 % APR)           | 0.092 % per epoch                         |
| $$\tau$$         | Time since last bond sale (hours) |                                           |

### Reward-rate formula

The reward rate formula is enabled as long as the token price trades higher than the protocol backing and linearly decreases until a new bond is cleared.

#### $$r_t \;=\; \max\!\Bigl(r_\text{min},\; r_\text{max}-\tfrac{\tau}{12}\,(r_\text{max}-r_\text{min})\Bigr)$$

_Resets to_ $$r_\text{max}$$ _whenever a bond clears._

### Treasury growth

Treasury growth (Or PCV growth) is the sum of all the new bond sales and the taxes collected from the Harberger tax.

$$\Delta PCV_t = B_t \;+\; H_t$$

### Token emissions

$$\Delta S_t = sS_{t-1} \times r_t \quad\text{distributed as:}\quad \begin{cases} 85\% &\text{→ stakers (sRZR)}\\ 10\% &\text{→ veDRE lockers (boost)}\\ 5\% &\text{→ referral payouts} \end{cases}$$

### Keeping each RZR “over-collateralised”

To keep every RZR token over-collateralized, the protocol continously checks a backing ratio and ensures that it is always above 1.

$$\text{Backing ratio } \beta_t = \frac{PCV_t}{S_t} \ge 1$$

If $$\beta_t$$ threatens to drop below 1 the protocol throttles $$r_t$$ toward $$r_\text{min}$$ (or pauses rebases) until fresh $$B_t + H_t$$ arrive.

## Worked example – one 8-hour epoch

To understand the mechanics better, we go through an 8 hour epoch to see how the variables play out.

| Item                          | Value                           |
| ----------------------------- | ------------------------------- |
| Starting PCV                  | $10 000 000                     |
| Starting supply               | 1 000 000 RZR                   |
| Declared sRZR value           | $30 M                           |
| Bond inflow $$B_t$$           | $100 000 (4,4,4 bond)           |
| Harberger tax $$H_t$$         | $30 M × 5 % / (365×3) ≈ $12 330 |
| Epoch reward rate $$r_t$$     | 0.359 % (fresh bond just hit)   |
| New HBA minted $$\Delta S_t$$ | 1 000 000 × 0.359 % = 3 590     |
| PCV after epoch               | $10 112 330                     |
| Backing per RZR               | $10.03 (↑ from $10.00)          |

In this example,

- The Treasury absorbs $112k without selling any RZR.
- Only 3.6 k RZR are printed, boosting stakers yet barely denting the backing ratio.
- If no new bonds land for 12 h, $$r_t$$ decays to 0.092 % (= 1000 % APR) — still sky-high, but four-times lower inflation.

_Rebase rewards are printed out of thin air, but they live or die by whether the Treasury can keep up._ OHM relied purely on waves of speculative bonding to fund that backing.

RZR adds a second hose (Harberger taxes) that keeps dollars flowing even when hype cools—letting it maintain high yields without blowing up the collateral ratio.
