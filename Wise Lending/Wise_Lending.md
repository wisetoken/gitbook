# 💰&nbsp;Wise Lending

A DeFi liquidity market where users can supply crypto assets to earn variable yield from borrowers. Wise Lending focuses on capital efficiency and yield optimization strategies.

## Wise Lending is a decentralized application built by our development team. It offers a platform for earning yield on your crypto assets with flexible withdrawals and the ability to use your deposits as collateral for borrowing.

## **How do crypto lending dApps work?**

In the crypto ecosystem where traditional credit scoring isn't applicable, loans are secured through collateral in the form of deposited crypto assets. Users often deposit assets they plan to hold long-term into lending platforms to generate passive income from borrowers. Depositors can also borrow against their own funds, which may provide tax advantages in some jurisdictions or allow for additional investment opportunities. Deposits generally remain accessible for withdrawal (subject to available liquidity), and the platform's reserves can be verified through blockchain analytics.

## What's the significance of being Built from Scratch?

Many lending platforms in DeFi are forks of established protocols like Aave or Compound, often adding their own token for additional incentives. Wise Lending was developed independently, allowing us to implement custom features and optimizations. This approach has helped us create a platform that aims to provide competitive yields without heavy reliance on token incentives that can dilute value over time.

## Key features of Wise Lending:

### 1) Optimized Yield for Lenders

Many lending platforms offer relatively modest yields because borrowing demand is limited to users looking to leverage market positions, which requires trading skill and risk tolerance. Wise Lending integrates with external yield sources that borrowers can access through our platform, potentially creating additional borrowing demand and yield opportunities for lenders. These integrated yield strategies aim to simplify the process for users. See [Power Farms](power-farms/) for more details.

### 2) Oracle safety mechanisms

To mitigate oracle manipulation risks, Wise Lending implements multiple price feed checks. We compare oracle data with Uniswap TWAP (Time-Weighted Average Price) data as a verification mechanism. When price feeds deviate by more than 2.5% from each other, the platform triggers a temporary freeze on the affected asset. During these freezes, users can unwind leveraged positions but cannot initiate new borrowing. This protective state lasts for 30 minutes and continues until price feeds reconcile. We utilize multiple oracle solutions, with RedStone Oracles serving as our primary data source for crypto asset pricing.

### 3) Lending Automated Scaling Algorithm: (LASA)

Our on-chain algorithm that helps determine and adjust interest rates in borrowing pools based on utilization and market conditions.

### 4) NFT-based position management

User positions are represented as NFTs when they first interact with the platform. This design enables transferable positions and creates the foundation for additional features that can be built on top of the base protocol, such as potential future options markets.

## How secure is Wise Lending?

Wise Lending prioritizes security through multiple layers of protection. Our smart contracts have undergone thorough audits by respected security firms, and we maintain an active bug bounty program with rewards up to $100k for critical vulnerabilities. The platform implements circuit breakers that automatically pause specific functions if unusual activity is detected, particularly around price feeds. Additionally, our oracle safety mechanisms help protect against price manipulation attacks by comparing multiple data sources before executing transactions.

## What makes Wise Lending different from other lending platforms?

Unlike many DeFi platforms that simply fork existing code and add a token, Wise Lending was built from scratch with specific improvements in mind. Our platform features innovative yield optimization through Power Farms, advanced oracle safety mechanisms, the dynamic LASA interest rate algorithm, and NFT-based position management. We focus on sustainable yields without relying on inflationary token rewards that dilute value over time. The platform also emphasizes transparency, with all reserves verifiable on-chain and a commitment to decentralization.

### 5) Capped Liquidation Fees

Rather than using percentage-based liquidation fees that can result in large losses for borrowers during volatile market conditions, we implement hard caps on liquidation fees. This approach aims to maintain liquidator incentives while providing borrowers with some protection against excessive capital loss during liquidation events.

### 6) Solely Deposit Mode

This optional feature allows users to place deposits in separate siloed vaults that aren't made available to borrowers. While this means forgoing earnings that come from borrowers using your assets, it provides an additional layer of protection against potential protocol risks. Users in solely deposit mode can still use their deposited assets as collateral for borrowing.


