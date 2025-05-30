---
description: >-
  This page goes through all the various glossary of terms used in the
  documentation.
icon: book-open
---

# Glossary

#### Protocol-Controlled Value (PCV)

Protocol-Controlled Value represents the assets a protocol owns outright and can deploy for its objectives (e.g., backing a token or funding treasury operations). Unlike Total Value Locked (TVL), which includes user-supplied liquidity, PCV measures the capital that the protocol itself controls. For instance, if a protocol’s treasury holds $100 M in stablecoins and LP tokens and its native supply is 10 M tokens, its PCV per token is $10  .

**Bonds (DeFi Bonding)**

In bonding mechanisms, users deposit assets (like stablecoins or LP tokens) into a protocol in exchange for its native token at a discount, subject to a vesting schedule. This raises fresh capital (boosting PCV) while incentivizing long-term engagement. OlympusDAO pioneered bonds that vest linearly over five days, requiring manual claims; newer “4-4-4” bonds vest over three four-day cycles with automatic restaking at each interval, streamlining compounding and deepening commitment  .

**Rebase Tokens**

Rebase (or elastic-supply) tokens automatically adjust their circulating supply to target a desired price band. When the market price exceeds the target, a positive rebase increases supply; when below, a negative rebase shrinks it. Holders’ balances expand or contract proportionally, aiming for price stability. Ampleforth (AMPL) is a well-known example  .

**Harberger Tax**

A Harberger tax is a mechanism where asset owners self-assess a value, pay a continuous tax (e.g., 5 % per year) on that valuation, and must be willing to sell the asset at the declared price at any time. This incentivizes truthful pricing: undervalue → risk sniping; overvalue → higher tax. It has been prototyped on Ethereum for digital assets and DAO treasuries  .

**Impermanent Loss**

Impermanent loss arises when providing liquidity to AMMs: as token prices diverge, the pool’s constant-product formula forces an uneven asset ratio, leaving liquidity providers worse off than simply holding assets. The “loss” becomes permanent when withdrawing liquidity while prices remain divergent  .

**Total Value Locked (TVL)**

TVL is the aggregate USD value of tokens staked, lent, or otherwise locked in a DeFi protocol. It serves as a rough gauge of protocol scale and user trust, though it can fluctuate with market prices and does not distinguish between user-owned and protocol-owned assets  .

**APY vs. APR**

Annual Percentage Rate (APR) measures simple, non-compounded returns, while Annual Percentage Yield (APY) accounts for compounding over the year. In DeFi, APY is often higher than APR due to frequent auto-compounding (e.g., every block or epoch)  .

**Liquidity Pool**

A liquidity pool is a smart contract that holds reserves of two or more tokens, enabling traders to swap them via an automated market maker (AMM) formula. Liquidity providers deposit assets into the pool and earn trading fees but face risks like impermanent loss  .

**Staking**

Staking involves locking tokens in a protocol—often as collateral or to secure the network—in exchange for rewards (newly minted tokens or a share of fees). In PoS blockchains, validators stake native coins to propose blocks; in DeFi, users stake governance or rebase tokens to earn yield  .

**Governance Token**

Governance tokens grant holders voting rights over protocol parameters (e.g., fee rates, treasury allocations, tax percentages). This decentralizes decision-making but can concentrate power if token distribution is uneven  .

**veToken (Voting-Escrowed Tokens)**

veTokens emerge when users lock governance tokens for a set period in exchange for boosted voting power and protocol rewards. The longer the lock, the greater the multiplier, aligning long-term commitment with governance influence (e.g., Curve’s veCRV model). Although powerful, veTokens can concentrate governance among long-lock holders.
