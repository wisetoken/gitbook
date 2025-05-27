# 🥩⋅Staking WISE

### How to Create WISE stakes:

WISE stakers are rewarded for making WISE more scarce by locking it up. Staking rewards are funded with 75% of the annual WISE inflation (25% funds referrals). Unstaking WISE early is penalized, so staking WISE creates a supply shock and a predictable future price floor.

To start a stake, go to [https://wise.one/staking/hub](https://wise.one/staking/hub). and click "Create WISE stake".

<figure><img src="../../../.gitbook/assets/image (4).png" alt=""><figcaption><p>starting a WISE stake</p></figcaption></figure>

The 5 green arrows are the settings, and the yellow are the bonuses.&#x20;

Input the **Staking Amount** of ETH or WISE you wish to use for your stake (ETH will be converted to WISE for the stake if you select that option).

Input the desired **Stake Duration** in days. The bonus increases based on the number of days following a piecewise linear progression (see the documentation).&#x20;

If you entered the website with a referral link, you will see the 10% **Referral Bonus** \
If not, you can choose a team referral address with the selector **I want to use team referral address** &#x20;

By default, the selector **I prefer this stake to be transferable** is off. \
That means the stake is not transferable, but is scrapable.\
If the selector **I prefer this stake to be transferable** is turned on, the stake is transferable (to another wallet or used DEFI project), but not scrapable.\
In the near future, a full WISE stake version will be released (transferable and scrapable)

**HIGH Gas costs for starting/ending stakes:**\*\*\
Our shares system and referral rewards make our staking contract much more complicated than a simple lock-up. Ending a stake costs much more than a simple swap, and the cost grows with the length of the stake. Holders must monitor Ethereum gas prices, start and end stakes during periods of low gas demand, and stake larger amounts ($5000+ for example).

### Scraping interest on WISE stakes:

The interest earned on WISE stakes can be collected at any time by scraping. This does not affect the principal amount of staked WISE, but it does reset the shares amount of the stake, meaning the shares advantage for staking earlier is reset as if the stake was started on the day you scrape. This will cause a significant reduction in APY for the remainder of your stake, so scraping is not recommended unless the stake is nearing maturity. Subsequent scrapes do cost significantly less gas, and closing scraped stakes will cost slightly reduce gas fees.

<figure><img src="../../../.gitbook/assets/image.png" alt=""><figcaption><p>Click to see the current stake status and scrapable rewards</p></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (1).png" alt=""><figcaption><p>Scrape or Terminate the stake</p></figcaption></figure>

### Terminate a WISE Stake Before Maturity:

You can end your stake any time before maturity for a significant penalty. The penalty is equivalent to the percentage of time you have not completed on your stake. \
For example, a 100 days stake ended on day 30 will cost 70% of your principal to end. The penalized WISE is distributed proportionally among the remaining WISE stakers. Interest earned on stakes is never penalized.\
Note : if you create a stake one day, it will really begin at midnight that day. You can terminate it any time during that day without penalty. &#x20;

