# Timelocked Multisig Admin

All major ownership about the protocol is kept behind a timelocked admin.

The Timelock Admin contract is the safety buffer between DRE’s on-chain governance and the live core contracts. All privileged actions—upgrading the rebase controller, changing the bond discount curve, moving treasury assets—must be queued in the timelock and can only be executed after a full 24-hour delay.&#x20;

The pause gives the community time to audit proposed changes, exit positions if necessary, or mobilise emergency governance to cancel malicious transactions.

{% hint style="success" %}
The timelock deployment can be found and verified over here [0x481dE207e04c32cbE5968bAa7F438B57E46F22c2](https://sonicscan.org/address/0x481de207e04c32cbe5968baa7f438b57e46f22c2) and the multisig safe (gnosis) can be found over there [0x0E43DF9F40Cc6eEd3eC70ea41D6F34329fE75986](https://app.safe.global/home?safe=sonic:0x0E43DF9F40Cc6eEd3eC70ea41D6F34329fE75986)
{% endhint %}
