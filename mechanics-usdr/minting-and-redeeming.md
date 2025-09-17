---
description: How minting and redeeming USDR works
---

# Minting & Redeeming

The USDR Treasury system enables users to mint USDR stablecoins by depositing collateral assets and redeem USDR back to underlying assets.

Minting & redeeming assets to/from USDR is permissionless allowing USDR peg to be maintained at 1$.

## Minting Process (Asset → USDR)

During the minting process, the system queries the oracle for an asset’s price per unit of its decimal base, validates the result against the stored reference price within a ±0.1% range, and then applies the mint formula, where the minted USDR amount is derived from the asset amount multiplied by its price, scaled to 18 decimals.

Users must first approve the treasury to spend their tokens, after which the treasury verifies eligibility, transfers the tokens, and mints the corresponding USDR.

## Redeem Process (USDR → Asset)

Redemption works in reverse but applies a fee. The redeem price is adjusted downward by the protocol fee (typically 0.1%) before converting USDR into the chosen asset.

The formula ensures that while minting is fee-free, redemptions return slightly less than the deposited value, creating an asymmetric incentive that discourages short-term cycling and generates revenue for the protocol.

For example, minting 1 USDC yields 1 USDR, but redeeming 1 USDR only returns 0.99 USDC.

## Security Considerations

**Price deviation:** Price deviation checks protect against manipulation, reverting if the oracle and stored price differ by more than 0.1%. If the price of an underlying asset deviates by more than 0.1%, mint/redeem operations for that asset will fail.

**Supply Caps:** To manage risk, each asset has its own supply cap that can be increased by the governor or decreased by guardians in response to market conditions.

**Access Control:** Access control ensures minting and redemption are open to all users when the system is active, but only governors can configure assets, while guardians have emergency powers such as pausing operations.
