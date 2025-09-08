# Price Hard Floor

The _Price Hard Floor_ is the protocol-guaranteed minimum redeemable value of one RZR token, denominated in USD-pegged stable assets held by the treasury. At any moment the floor equals

$$
\text{FloorUSD} \;=\; \frac{\text{Floor-Escrow stables}}{\text{Circulating RZR}}
$$

and cannot decrease. It only ratchets upward as new stablecoins flow in.

## How the Floor Is Funded?

A fixed 25 % of every newly minted RZR (from rebases) (via bond deposits, Harberger-tax payments, AMM fees) goes straight into a _Floor Escrow_ sub-account of the treasury.

During each 8-hour epoch the controller checks

$$
\text{Surplus} = \text{Escrow} - (\text{FloorUSD} \times \text{Supply})
$$

If surplus ≥ 5 % of required collateral, the floor is lifted by +1 %.

Because the escrowed assets are stablecoins and never rehypothecated, a raised floor can’t move down—only sideways (if inflows pause) or up.
