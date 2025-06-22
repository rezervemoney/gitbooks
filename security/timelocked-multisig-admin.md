---
description: >-
  This page talks about how Rezerve keeps the entire protocol ownership
  behind a timelock and a multisig
---

# Timelocked Multisig Admin

All major ownership about the protocol is kept behind a timelocked multisig admin.

The Timelock Admin contract is the safety buffer between RZR’s on-chain governance and the live core contracts. All privileged actions—upgrading the rebase controller, changing the bond discount curve, moving treasury assets—must be queued in the timelock and can only be executed after a full 24-hour delay.

The pause gives the community time to audit proposed changes, exit positions if necessary, or mobilise emergency governance to cancel malicious transactions.

- 1 day Timelock - [0x616634e975dbcf4c3bdf25a5e0f8f37c4fff0fc7](https://sonicscan.org/address/0x616634e975dbcf4c3bdf25a5e0f8f37c4fff0fc7)

- Safe Gnosis - [0x0E43DF9F40Cc6eEd3eC70ea41D6F34329fE75986](https://app.safe.global/home?safe=sonic:0x0E43DF9F40Cc6eEd3eC70ea41D6F34329fE75986)

{% hint style="success" %}

{% endhint %}
