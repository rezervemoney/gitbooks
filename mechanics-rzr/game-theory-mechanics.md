---
description: >-
  Below is a concise game‐theoretic breakdown of the Rezerve Money, showing each
  principal actor’s strategic options, their immediate effects, impacts on the
  protocol, and the incentives.
---

# Game Theory Mechanics

_Before diving into specifics, it’s helpful to recognize that the Rezerve Money is designed as a mechanism‐design game in which each participant’s best response aligns with overall protocol health. Stakers, bonders, asset owners (declaring Harberger prices), and governance token holders (FED) all face strategic trade‐offs—between immediate gains, future yield, and downside risk—that are carefully balanced by on‐chain rules and incentives._

At the heart of RZR’s game is the Harberger tax, which asks asset owners to self-assess a value and pay a continuous tax on it, knowing that anyone can buy the asset at that price. This creates a classic mechanism‐design scenario: if you undervalue your position, you risk someone sniping it; if you overvalue, you pay excessive tax—driving you to declare your true reservation price in equilibrium.

Because every declared valuation directly funds the common treasury (PCV), rational actors internalize the externality: their tax payments bolster everyone’s future rebases, creating a public‐goods funding game where collective payoff increases as declarations stabilize near true values.

## Staking and the (3,3) Dynamics

RZR staking mirrors OlympusDAO’s (3,3) game theory meme, where the most profitable joint strategy is for all players to stake rather than sell or bond.

In RZR’s variant, choosing to stake RZR (becoming sRZR) not only earns rebases but also strengthens PCV via Harberger taxes—so staking yields a payoff of +4, while selling or refusing to declare an honest value is strictly dominated, reinforcing a cooperative equilibrium.

## Bonding as a Commitment Game

Bonding in RZR is framed as a time-commitment game: users lock assets to mint discounted RZR, but only receive them over three auto-restaked four-day cycles, aligning long-term commitment with yield capture.

By automating restaking, the protocol removes strategic timing frictions (when to claim and restake), ensuring that the dominant strategy is to bond early for maximal compounding rather than waiting or free-riding on others’ actions.

## Game Theory Table

This table formalizes RZR’s mechanism design: each player’s best response—truthful pricing, cooperative staking, timely bonding, prudent governance—reinforces protocol stability and collective prosperity.

In designing RZR, each on-chain rule aligns individual best responses with overall health: Harberger self-assessments induce truthful pricing; staking yields +4 payoffs akin to Olympus’s (3,3) game; bonding commits capital for compounded returns

<table data-full-width="true"><thead><tr><th width="131.15625">Actor</th><th>Strategy</th><th>Immediate Effect</th><th>Protocol Impact</th><th>Incentive / Payoff</th></tr></thead><tbody><tr><td>Asset Owner</td><td>Under‐declare Value</td><td>Pays lower tax; position vulnerable to sniping</td><td>↓ Harberger tax inflow</td><td>− High risk of losing position</td></tr><tr><td></td><td>Truthful Declaration</td><td>Pays fair tax; position safe</td><td>↑ Stable Harberger revenue into PCV</td><td>+ Maximizes net payoff: tax ≈ value gain; equilibrium strategy under COST model</td></tr><tr><td></td><td>Over‐declare Value</td><td>Pays more tax; deters snipers</td><td>↑ Extra Harberger revenue</td><td>− Extra cost outweighs marginal benefit; only optimal if valuing exclusivity highly</td></tr><tr><td>RZR Holder</td><td>Stake (Become sRZR)</td><td>Locks tokens; mints sRZR</td><td>↑ PCV via Harberger taxes; fuels rebases (≈ +4 payoff)</td><td>+ Highest cooperative payoff, akin to Olympus’s “(3,3)” cooperative equilibrium</td></tr><tr><td></td><td>Sell / Unstake</td><td>Burns sRZR for RZR; exits staking</td><td>↓ PCV inflows; may trigger rebase throttle</td><td>− Lower payoff (“(1,1)” or “(2,−1)”), undermines collective yield</td></tr><tr><td>Bonder</td><td>Bond Early</td><td>Deposits assets; receives auto-compounding vest</td><td>↑ Immediate PCV from bond; long-term supply dilution</td><td>+ Captures maximal compounded yield over 12 days; dominant vs. waiting</td></tr><tr><td></td><td>Wait to Bond</td><td>Holds assets; may benefit from price movements</td><td>→ No PCV inflow until bond; misses compounding</td><td>− Missed yield opportunity; inferior if expecting positive rebase trajectory</td></tr></tbody></table>

Explanation of Payoffs:

* **Asset Owner Game:** Harberger self-assessment creates a classic “truth-telling” equilibrium—undervaluation invites snipes, overvaluation burdens taxes, so truthful declaration is dominant.
* **Staking Game:** By staking, users earn rebases funded by PCV inflows. Adopting the cooperative “stake” strategy yields the highest group and individual returns, analogous to OlympusDAO’s (3,3) equilibrium in the Prisoner’s Dilemma framing.
* **Bonding Game:** The RZR bond automates compounding making early participation strictly superior to delaying, since delaying misses guaranteed yield.

## Nash Equilibrium and Robustness

The confluence of these games produces a Nash equilibrium in which rational participants:

1. Declare honest self-assessments to minimize tax vs. snipe risk.
2. Stake RZR to capture rebases and influence governance.
3. Bond early under the for compounded yield.

This equilibrium sustains high on‐chain participation, robust treasury growth, and resilient defense against bad debt—making the Rezerve Money a self‐enforcing, game-theoretic system.
