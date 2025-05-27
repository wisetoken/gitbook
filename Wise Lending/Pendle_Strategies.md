# 🧠⋅Pendle Strategies

Pendle offers mechanisms for enhancing yields on existing yield-bearing tokens, providing an alternative approach compared to directly using other yield sources.

### What does Pendle do?

[Pendle](https://pendle.finance/) has developed a system that can potentially enhance the APY of yield-bearing tokens, including staked ETH LSTs and yield-bearing stablecoins. Their approach involves splitting tokens into yield-bearing components and principal components, allowing users to take positions on either aspect. This creates a market for yield speculation that generates transaction fees, which can provide additional returns for holders (for example, Lido staked ETH might offer around 3.6% APY while Pendle's Lido pools may offer higher yields depending on market conditions).

Like many DeFi protocols, Pendle uses its native token as part of its incentive structure. While we generally prefer yield sources that don't rely heavily on token incentives, Pendle's yield-speculation fee mechanism provides an additional source of returns. They've implemented a tokenomics model similar to Curve's staking and gauge system, which has shown sustainability in that ecosystem.

Pendle implements decentralized contract architecture, using non-upgradable contracts and factory contracts to generate new pools (similar to Uniswap's approach), which helps limit certain centralization risks.

It's important to note that, as demonstrated by incidents like the Kyberswap exploit, Pendle pools are ultimately dependent on the security of their underlying yield sources. In our strategies, we aim to use established assets and limit the number of integrated protocols to manage risk exposure.

### Why do we use Pendle LPs instead of leveraging PT?

In short: to reduce liquidation risks. Principal Tokens (PT) can experience temporary price decreases when the yield component (YT) increases in value. If our Power Farms directly leveraged PT, these fluctuations could potentially trigger liquidations when YT prices rise significantly. By using Liquidity Provider (LP) positions instead, the pool automatically adjusts by accruing more PT as PT prices decrease, creating a more balanced position. The impermanent loss from this process is typically minor and temporary. For users who prefer a different approach, Wise Lending does accept Pendle PT tokens as collateral, allowing for manual borrowing against PT positions.

### Are there any Fees to use Pendle Power Farms?

Pendle Power Farms include a 1-3% initiation fee (approximately $10-$30 on a $1000 deposit). These fees are used to acquire and stake PENDLE tokens (vePENDLE), which can help access enhanced yield tiers on the platform. As the protocol accumulates more vePENDLE through these fees, it may qualify for higher yield boosts from Pendle's gauge system, potentially benefiting users of our Pendle Power Farm positions.

### What are the liquidation risks? See [Power Farms](../power-farms/)

