---
description: This page talks about the various security practices takes up by RZR Finance.
---

# Overview

At RZR Finance every core contract for staking, bonding, treasury is wired for defense in depth. We combine hardened code, battle-tested external data, explicit human checkpoints and perpetual public scrutiny so that no single failure can compromise funds or mint unbacked supply.

#### **Use of external oracle for price feeds**

All treasury assets, LP positions and the RZR/USD reference price come from eOracle, a hybrid push/pull network that pairs Chainlink-grade validator quorums with onchain medianisers. Liquidity-weighted medians, per-block freshness and signed payloads protect against thin-DEX manipulation which is the exact weakness that early Olympus TWAPs exposed.

Read [Oracles](oracles.md)

#### **Timelocked Gnosis Safe**

Protocol ownership sits behind a 3-of-5 multisig Gnosis Safe which is, in turn, the only _proposer_ for a 24-hour TimelockController. Any upgrade, parameter change or treasury movement must (i) collect three hardware-wallet signatures, (ii) sit onchain for a full day, and (iii) be open to public veto before execution. Fast iteration is possible, but never instant or invisible.

Read [Timelocked Admin](timelocked-multisig-admin.md)

#### **Audits + Bug Bounty**

The codebase is a minimal fork of Olympus v2 already vetted by PeckShield, Quantstamp and OpenZeppelin with only two new modules (instant-stake hook and floor-price oracle) reviewed by BlockSec and a public Code4rena contest. A standing $300 k Immunefi bounty pays white-hats for any vulnerability that could drain assets, break the floor invariant or inflate supply beyond authorised routes.

Read [Audits](audits.md)

#### **Maximum Transparency**

All solidity, deployment scripts and ABI hashes live in the public repo: github.com/rzr-protocol/core. Deployed addresses, constructor args and timelock queue logs are published the moment they hit mainnet. Front-end dashboards surface real-time β, ρ and Floor Price so anyone can cross-check monetary policy against onchain reality.

Read [Deployed Addresses](deployed-addresses.md) and view our [Github](https://github.com/rezervemoney/code)
