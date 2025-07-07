---
description: This page talks a bit about the lstRZR token.
---

# Liquid Staking - lstRZR

{% hint style="success" %}
The lstRZR token is currently deployed on the Sonic chain at [0x67a298e5b65db2b4616e05c3b455e017275f53cb](https://sonicscan.org/token/0x67a298e5b65db2b4616e05c3b455e017275f53cb) and the source code for it can be found over at [Github](https://github.com/rezervemoney/code/blob/main/contracts/periphery/Staking4626.sol).
{% endhint %}

lstRZR is an ERC-4626 compliant liquid staking token (LST) that allows users to stake RZR tokens and receive liquid staking tokens (lstRZR) in return. The vault automatically compounds rewards and implements a unique Harberger tax mechanism with a 130% buyout premium.

All rewards accumulate back into the LST's staked position, which means over time a user continues to see the rate of lstRZR/RZR increase over time.

### Key Features

- **ERC-4626 Compliance**: Standard vault interface for deposits, withdrawals, and share calculations
- **Automatic Reward Compounding**: Harvests and compounds staking rewards automatically
- **Harberger Tax System**: Implements a self-declared value system with buyout premiums
- **Liquid Staking**: Users can trade their lstRZR tokens while maintaining exposure to RZR staking rewards

By being compliant to the 4626 standard, this allows multiple other protocols (yield marketplaces, vaults, lending protocols etc...) to easily integrate with the protocol's staking token.

## How does the vault handles the staking tax?

Since any token that stakes into the protocol has to pay a 5% harberger tax on it's declared value, the vault is pre-configured to treat all deposits at a **130% buyout premium.** This means that:

- When you stake RZR into the LST, you declare a value that is 130% of your staked amount
- This creates a buyout price that others must pay to acquire your position

Example Calculation: If you stake **100 RZR**

1. **Declared Value** = 100 × 130% = **130 RZR**
2. **Tax Paid** = 130 × 5% = **6.5 RZR**
3. **Net Staked** = 100 - 6.5 = **93.5 RZR**

You will get back 93.5 lstRZR (assuming no yield has been auto-compounded into the position).

This pre-configured buyout value can be changed by governance at any point in time.

## Technical Specification

The follow sections below describe technically how the 4626 vaults handles deposits and withdrawals.

### Deposit Process

During the deposit flow, the protocol will charge a 6.5% tax (which is part of the [staking harberger tax](./)) automatically from the user's position.

A sample deposit transaction can be found over [here](https://sonicscan.org/tx/0x0b3726bbdaeffb815f6c27241493330fdec271036e81bb362c1b9ee5c92a56b2).

```solidity
function deposit(uint256 assets, address receiver) public returns (uint256 shares)
```

1. User calls `deposit(100 RZR)`
2. Vault calculates net assets after tax: `_netStakeAfterTax(100)`
3. For 100 RZR with 130% premium and 5% tax:
   - Declared value = 100 × 130% = 130 RZR
   - Tax = 130 × 5% = 6.5 RZR
   - Net staked = 100 - 6.5 = 93.5 RZR
4. Vault mints shares based on net staked amount
5. RZR tokens are transferred to the vault and staked

### Withdrawal Process

During the withdraw flow, the protocol will return a NFT position representing a user's stake in the protocol. To get the underlying tokens back, users need to go through a 3 day cooldown.

A sample withdraw transaction can be found over [here](https://sonicscan.org/tx/0xd078df9bee2de3e4c07011392c31cdd56692647b14690fa4c16c50b7aa6c5e01).

```solidity
function withdraw(uint256 assets, address receiver, address owner) public returns (uint256 shares)
```

1. User calls `withdraw(50 RZR)`
2. Vault calculates required shares: `previewWithdraw(50)`
3. Burns the calculated shares
4. Splits the staking position proportionally
5. Transfers RZR tokens to receiver
