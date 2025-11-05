---
description: This page talks about the various audits done on the protocol
---

# Audits

RZR’s core contracts are hard-forked from OlympusDAO v2, inheriting its battle-tested architecture Treasury, BondDepository, RebaseController, and sToken with only two surgical edits to the staking flow:

1. Instant-Stake Hook added to BondDepository so newly-vested tokens can auto-stake without a second transaction.
2. Floor-Price Oracle bump inserted to raise the internal price floor instead of transferring yield in stables.

Outside these inserts the staking contract’s math, access modifiers, and checkpoint logic remain byte-for-byte identical to Olympus, preserving the original invariant proofs.

Seperately an indepedent audit was conducted by [Halborn](https://www.halborn.com/) on the protocol on the changes made.

## Audit History

Because most of the logic is inherited, RZR benefits from the three full-scope audits OlympusDAO commissioned in 2021-22 (PeckShield, Quantstamp, and OpenZeppelin).

* [Halborn - 2025](https://github.com/rezervemoney/code/blob/main/audits/2025-06-21-halborn.pdf)
* [PeckShield - 2021](https://github.com/peckshield/publications/blob/master/audit_reports/PeckShield-Audit-Report-OlympusDAO-v1.0.pdf)
* [Omniscia - 2021](https://omniscia.io/reports/olympus-dao-protocol-v2/)

## Timelock & Multisig Ownership

All admin roles are held by a 3-of-5 Gnosis Safe fronting a 24-hour TimelockController. Any upgrade, parameter tweak, or treasury movement is visible onchain for a full day before execution, giving the community ample time to review or veto.

See more at [timelocked multisig admin](timelocked-multisig-admin.md).

## Bug Bounty

A standing bounty (up to $100k) rewards disclosure of vulnerabilities that could drain funds, break Floor-Price invariants, or inflate supply beyond authorised mint routes.

Reproducible Build & Source References

* Canonical repository: [https://github.com/rezervemoney/code](https://github.com/rezervemoney/code)
