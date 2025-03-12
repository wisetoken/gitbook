1. [💰Wise Lending](/wise/wise-lending)

# 🧠Pendle Strategies

Pendle is in the business of augmenting existing yield tokens, which makes them the clear choice over using any other yield sources directly, and there are currently no competitors to Pendle.

## What does Pendle do exactly?

[Pendle](https://pendle.finance/) has created a unique additional layer of yield that can augment the APY of any yield-bearing token, including staked ETH LSTs and yield-bearing stable coins. They split the yield-bearing part of tokens away from the principal part, which enables users to long or short the yield by purchasing only yield tokens or only principle tokens. This speculation creates transaction fees, which act as a second layer of rewards for holders (e.g. currently Lido staked ETH is 3.6% APY vs 7% un-boosted APY on Pendle Lido pools).

Pendle does use their own token to pad rewards, which is a practice we frown upon, but Pendle is still uniquely viable even without the extra token rewards. Their rewards layer from yield-speculation fees makes Pendle a better yield source, even if their token had zero value. We also noticed that Pendle copied Curve's staking/bribing tokenomics model, and this has served CRV well for years.

Pendle upholds the pure decentralized standards of true DeFi. They have fully decentralized contracts (not upgradable proxies), and they use factory contracts to generate new pools (like Uniswap does), which means Pendle can't rug their pools.

However, as we saw with the Kyberswap exploit, it is important to understand that Pendle pools are only as safe as their underlying yield sources. Wise Lending uses only blue chip assets for strategies and keeps the number of strategies down to the bare minimum.

## Why do we use Pendle LPs instead of leveraging PT?

TLDR: to avoid unnecessary liquidations. The value of PT assets can drop temporarily if the yield (YT) portion goes up in value. If Power Farms leveraged only PT, it could result in liquidations if the YT increased significantly. However, in an LP, the pool will accrue more PT as the value of PT goes down, and the tiny amount of impermanent loss created from this happening is negligible and temporary.
Wise Lending does accept Pendle PT tokens as collateral, so users can manually borrow against their PT and then loop it if they so desire.

## Are there any Fees to use Pendle Power Farms?

Our Pendle Power Farms charge a 1-3% initiation fee (e.g. $10-$30 on $1000 deposited). This fee gets converted into staked PEDNLE tokens (vePENDLE), to unlock higher tiers of APY for our users. As more Pendle Power Farm positions are created, the accumulating fees snowball, creating more vePENDLE, and unlocking more boosted APY for Pendle Power Farm users. Yay for boosted APY!

## What are the liquidation risks? See [Power Farms](/wise/wise-lending/power-farms)

[PreviousPower Farms](/wise/wise-lending/power-farms)[NextLeaderboards](/wise/wise-lending/leaderboards)

Last updated 9 months ago