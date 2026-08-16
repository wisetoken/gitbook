# 🥩&nbsp;Staking WISE

### How to Create WISE stakes:

WISE stakers are rewarded for making WISE more scarce by locking it up. Staking rewards are funded with 75% of the annual WISE inflation (25% funds referrals). Unstaking WISE early is penalized, so staking WISE creates a supply shock and a predictable future price floor.

To start a stake, go to [https://stake.wise.one](https://stake.wise.one). and click "Create WISE stake".

<figure><img src="../../../.gitbook/assets/image (4).png" alt=""><figcaption><p>starting a WISE stake</p></figcaption></figure>

The 5 green arrows are the settings, and the yellow are the bonuses.&#x20;

Input the **Staking Amount** of ETH or WISE you wish to use for your stake (ETH will be converted to WISE for the stake if you select that option).

Input the desired **Stake Duration** in days. The bonus increases based on the number of days following a piecewise linear progression (see the documentation).&#x20;

If you entered the website with a referral link, you will see the 10% **Referral Bonus** \
If not, you can choose a team referral address with the selector **I want to use team referral address** &#x20;

By default, the selector **I prefer this stake to be transferable** is off.
That means the stake is not _transferable_, but is _scrapable_.
If the selector **I prefer this stake to be transferable** is turned on, the stake is _transferable_ (to another wallet or used DEFI project), and also _scrapable_.

**Gas costs for starting/ending stakes:**\
Our shares system and referral rewards make our staking contract much more computationally expensive than a simple lock-up. Ending a stake could costs more than a simple swap, and the cost grows with the length of the stake linearly. Holders must monitor Ethereum gas prices, start and end stakes during periods of low gas demand, and consider staking larger amounts ($5,000+ for example).

### Scraping interest on WISE stakes:

The interest earned on WISE stakes can be collected at any time by scraping. This does not affect the principal amount of staked WISE, but it does reset the shares amount of the stake, meaning the shares advantage for staking earlier is reset as if the stake was started on the day you scrape. This will cause a significant reduction in APY for the remainder of your stake, so scraping is not recommended unless the stake is nearing maturity. Subsequent scrapes do cost significantly less gas, and closing scraped stakes will cost slightly reduce gas fees.

<figure><img src="../../../.gitbook/assets/image.png" alt=""><figcaption><p>Click to see the current stake status and scrapable rewards</p></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (1).png" alt=""><figcaption><p>Scrape or Terminate the stake</p></figcaption></figure>

### Terminate a WISE Stake Before Maturity:

You can end your stake any time before maturity for a significant penalty. The penalty is equivalent to the percentage of time you have not completed on your stake. \
For example, a 100 days stake ended on day 30 will cost 70% of your principal to end. The penalized WISE is distributed proportionally among the remaining WISE stakers. Interest earned on stakes is never penalized.\
Note: if you create a stake one day, it will really begin at midnight that day. You can terminate it any time during that day without penalty. &#x20;

### Signature Stakes: Transferable WISE as Collateral

A **Signature Stake** is a WISE stake created with the **I prefer this stake to be transferable** option turned on (see above). Unlike a standard non-transferable stake, a Signature Stake can be sent to another wallet or used directly by third-party DeFi protocols, while continuing to earn staking rewards and remaining scrapable for the life of the stake (durations up to 42 years).

Because a Signature Stake is a transferable on-chain position with a predictable, growing value, it can be pledged as collateral to open a **line of credit** without ever unstaking the underlying WISE. This works today on general-purpose NFT/position-collateral lending markets such as [anvil.xyz](https://anvil.xyz), and is also the basis for a native Wise collateral product currently in development.

The Signature Stake contract is the single largest WISE staking position in the ecosystem, holding roughly a quarter of all staked WISE — see the [live holder breakdown on DeBank](https://debank.com/token/eth/0x66a0f676479cee1d7373f3dc2e2952778bff5bd6/group).

