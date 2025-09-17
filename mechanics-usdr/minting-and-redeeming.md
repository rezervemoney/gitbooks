---
description: How minting and redeeming USD69 works
---

# Minting & Redeeming

The USD69 Treasury system enables users to mint USD69 stablecoins by depositing collateral assets and redeem USD69 back to underlying assets.&#x20;

Minting & redeeming assets to/from USD69 is permissionless allowing USD69 peg to be maintained at 1$.

## Minting Process (Asset → USD69)

During the minting process, the system queries the oracle for an asset’s price per unit of its decimal base, validates the result against the stored reference price within a ±0.1% range, and then applies the mint formula, where the minted USD69 amount is derived from the asset amount multiplied by its price, scaled to 18 decimals.&#x20;

Users must first approve the treasury to spend their tokens, after which the treasury verifies eligibility, transfers the tokens, and mints the corresponding USD69.

## Redeem Process (USD69 → Asset)

Redemption works in reverse but applies a fee. The redeem price is adjusted downward by the protocol fee (typically 0.1%) before converting USD69 into the chosen asset.&#x20;

The formula ensures that while minting is fee-free, redemptions return slightly less than the deposited value, creating an asymmetric incentive that discourages short-term cycling and generates revenue for the protocol.&#x20;

For example, minting 1 USDC yields 1 USD69, but redeeming 1 USD69 only returns 0.99 USDC.&#x20;

## Security Considerations

**Price deviation:** Price deviation checks protect against manipulation, reverting if the oracle and stored price differ by more than 0.1%. If the price of an underlying asset deviates by more than 0.1%, mint/redeem operations for that asset will fail.

**Supply Caps:** To manage risk, each asset has its own supply cap that can be increased by the governor or decreased by guardians in response to market conditions.&#x20;

**Access Control:** Access control ensures minting and redemption are open to all users when the system is active, but only governors can configure assets, while guardians have emergency powers such as pausing operations.
