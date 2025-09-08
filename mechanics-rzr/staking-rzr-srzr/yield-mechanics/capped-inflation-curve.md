---
description: >-
  Below is a one-page explainer of RZR’s capped-inflation curve—the rule-set
  that decides how many new tokens are minted each epoch—paired with a visual of
  the curve.
---

# Capped Inflation Curve

RZR’s capped-inflation curve mints new tokens only when the treasury is safely collateralized. As the backing ratio β (stable-asset PCV divided by circulating supply) rises, the annual rebase rate steps from 0% (if β < 1) to a “warm-up” slope that reaches 500 % at β = 1.5, holds flat at 500 % until β = 2, then ramps to a hard ceiling of 2 000 % at β = 2.5, where it is permanently capped.

If reserves thin, β falls and the APR auto-throttles—so supply can never outgrow collateral for long—while periods of strong inflow unlock higher yields for stakers without risking solvency.

<figure><img src="../../../.gitbook/assets/image (2) (1) (1).png" alt=""><figcaption></figcaption></figure>

On the horizontal axis the diagram plots β, while the vertical axis shows the corresponding APR. Grey guide-lines mark the policy thresholds at β = 1.0, 1.5, 2.0, 2.5. The orange curve idles at zero until collateral safety is regained, accelerates through the warm-up zone, cruises at the mid-band, then finally slopes toward its crimson ceiling.

The visual makes a simple promise to stakers: the further the treasury races ahead of supply, the faster your balance compounds—but never beyond that red roof.

| β zone      | APR logic            | Intuition                                 |
| ----------- | -------------------- | ----------------------------------------- |
| β < 1       | 0 % (mint halts)     | Under-collateralised; focus on buy-backs. |
| 1 ≤ β < 1.5 | Linear 0 → 500 %     | “Warming up”—letting RFV catch up.        |
| 1.5 ≤ β < 2 | Flat 500 %           | Sustainable “floor” yield.                |
| 2 ≤ β < 2.5 | Linear 500 → 2 000 % | Turbo mode when surplus stables pile up.  |
| β ≥ 2.5     | Hard cap 2 000 %     | Prevents reflexive over-mint.             |

Each eight-hour epoch the controller asks a single question: “How many dollars of stable assets back every token in circulation?” That quotient—the backing ratio β—dictates the annual mint rate.

## Expected Behaviour

By design the curve is reflexive in a benign way. Hot demand for bonds or Harberger taxes swells the treasury, nudging β up and automatically granting stakers a richer reward; that extra yield attracts even more capital, reinforcing the surplus.

Conversely, when inflows cool the mint rate eases back, letting the treasury refuel before the next growth spurt. In practice this feedback loop keeps both the token supply and the underlying floor value climbing in tandem rather than fighting each other—which is exactly the balance a reserve-currency protocol needs to survive the boom-and-bust cadence of crypto markets.

## Why cap inflation at all?

Run-away emissions were the Achilles’ heel of early rebase tokens: supply ballooned more quickly than the treasury could accumulate collateral, so the “intrinsic value” per token drifted downward and confidence evaporated.

RZR’s capped-inflation curve tackles that failure head-on. It promises spectacular yields only when the protocol can clearly afford them, and it throttles those yields to zero the moment the treasury’s backing ratio drops below one-to-one. By making inflation conditional on real, on-chain collateral, the curve converts the wild speculative energy of a rebase currency into a controlled, sustainable growth engine.

* **Solvency first -** The protocol mints aggressively only when the treasury’s backing ratio (β = PCV ÷ supply) is strong.
* **Yield without death-spiral -** A 0 → 500 → 2 000 % ceiling still looks juicy to speculators but does not force runaway supply like Olympus’ early six-figure APYs.

## OlympusDAO Case Study & Improvements

Tightening the headline range to \~500 %–2 000 % APR is vastly more sustainable than the six-figure APYs Olympus paid in 2021, provided those rates are firmly tied to real, recurring inflows (Harberger taxes + bond premiums + fee revenue).

| Dimension                                | Early-Olympus (100 k %+)                                                      | 500 %–2 000 % band                                                                             |
| ---------------------------------------- | ----------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| Daily emissions                          | ≈ 2 % of supply every 8 h → supply 30 000× in a year                          | 0.07 %–0.28 % per 8 h → supply 5–15×/year                                                      |
| Backing catch-up                         | Treasury inflows rarely kept pace; β trended down without constant bond mania | Inflows needed are 50–95 % lower, so Harberger taxes + moderate bonds are enough to keep β ≥ 1 |
| Runway (days until RFV < 1 if no inflow) | Often < 30 d                                                                  | > 1 yr at 500 %, ≈ 4 mo at 2 000 %                                                             |
| Market psychology                        | “Numbers too crazy to last” → fast exit reflex                                | Still eye-popping but _credible_; users believe it can persist long enough to compound         |

The scheme converts every external dollar into backing and yield which keeps inflation tethered to real collateral and lets the protocol advertise high yields without repeating the hyper-inflation mistakes of early OlympusDAO.
