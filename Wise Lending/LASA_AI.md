# 🤖&nbsp;LASA AI

LASA (Lending Automated Scaling Algorithm) is our on-chain mechanism that dynamically determines the borrow APY (Annual Percentage Yield) in our lending pools. It's designed to adjust interest rates based on market conditions, primarily the utilization rate of assets within a pool.

## How LASA Works

LASA aims to maintain an optimal balance between rewarding lenders and providing competitive rates for borrowers. It achieves this by implementing an interest rate model that responds to supply and demand.

- **Utilization Rate:** This is a key metric LASA uses. It's the ratio of borrowed assets to the total supplied assets in a pool.
    - A low utilization rate might suggest low demand for borrowing or an oversupply of assets, leading LASA to potentially lower borrow APYs to incentivize borrowing.
    - A high utilization rate indicates high demand or low supply, prompting LASA to increase borrow APYs to attract more liquidity and make borrowing more expensive.

- **Interest Rate Curves:** LASA uses a model with configurable parameters to define an interest rate curve for each asset. This curve dictates how the borrow APY changes as the utilization rate changes. Typically, the curve will have a gentler slope at lower utilization rates and a steeper slope as utilization approaches high levels (e.g., 80-90%), to aggressively incentivize repayment or new deposits and prevent liquidity crunches.

## LASA Parameters for Pool Interest Rate Curves

The following table provides lookup values for different borrow rate curves. These parameters are used to construct specific interest rate models tailored to different assets or market conditions. The goal is to achieve a target interest rate at a specific utilization percentage (referred to as 'Gaue Value' or 'Gauge Value' in some contexts, indicating a target calibration point for the curve).

| Lower Bound Rate [wei] | Upper Bound Rate [wei] | Mul-Factor [wei]      | Target (Utilization %, Rate %) |
| :----------------------- | :----------------------- | :-------------------- | :----------------------------- |
| 1E18 (1000000000000000000) | 3E18 (3000000000000000000) | 4E15 (4000000000000000) | (90%, 3%)                      |
| 1E18 (1000000000000000000) | 3E18 (3000000000000000000) | 5E15 (5000000000000000) | (90%, 4%)                      |
| 1E18 (1000000000000000000) | 3E18 (3000000000000000000) | 6E15 (6000000000000000) | (90%, 5%)                      |
| 1E18 (1000000000000000000) | 3E18 (3000000000000000000) | 6.5E15 (6500000000000000)| (90%, 5.5%)                    |
| 1E18 (1000000000000000000) | 3E18 (3000000000000000000) | 7E15 (7000000000000000) | (90%, 6%)                      |
| 1E18 (1000000000000000000) | 3E18 (3000000000000000000) | 8E15 (8000000000000000) | (90%, 7%)                      |
| 1E18 (1000000000000000000) | 3E18 (3000000000000000000) | 10E15 (10000000000000000)| (90%, 8%)                      |
| 1E18 (1000000000000000000) | 3E18 (3000000000000000000) | 13E15 (13000000000000000)| (90%, 11%)                     |
| 1E18 (1000000000000000000) | 3E18 (3000000000000000000) | 14.5E15 (14500000000000000)|(90%, 12%)                     |
| 1E18 (1000000000000000000) | 3E18 (3000000000000000000) | 18E15 (18000000000000000)| (90%, 14%)                     |
| 1E18 (1000000000000000000) | 3E18 (3000000000000000000) | 19E15 (19000000000000000)| (90%, 15%)                     |
| 1E18 (1000000000000000000) | 3E18 (3000000000000000000) | 22E15 (22000000000000000)| (90%, 17%)                     |
| 1E18 (1000000000000000000) | 3E18 (3000000000000000000) | 25E15 (25000000000000000)| (90%, 19%)                     |
| 1E18 (1000000000000000000) | 3E18 (3000000000000000000) | 27.5E15 (27500000000000000)|(90%, 20%)                     |
| 1E18 (1000000000000000000) | 3E18 (3000000000000000000) | 28E15 (28000000000000000)| (90%, 21%)                     |
| 1E18 (1000000000000000000) | 3E18 (3000000000000000000) | 30E15 (30000000000000000)| (90%, 22%)                     |
| 1E18 (1000000000000000000) | 3E18 (3000000000000000000) | 35E15 (35000000000000000)| (90%, 25%)                     |
| 1E18 (1000000000000000000) | 3E18 (3000000000000000000) | 53E15 (53000000000000000)| (90%, 35%)                     |
| 1E18 (1000000000000000000) | 3E18 (3000000000000000000) | 8E15 (8000000000000000) | (80%, 3%)                      |
| 1E18 (1000000000000000000) | 3E18 (3000000000000000000) | 10E15 (10000000000000000)| (80%, 4%)                      |
| 1E18 (1000000000000000000) | 3E18 (3000000000000000000) | 17.5E15 (17500000000000000)|(80%, 7%)                      |
| 1E18 (1000000000000000000) | 3E18 (3000000000000000000) | 22E15 (22000000000000000)| (80%, 8%)                      |
| 1E18 (1000000000000000000) | 3E18 (3000000000000000000) | 24E15 (24000000000000000)| (80%, 9%)                      |
| 1E18 (1000000000000000000) | 3E18 (3000000000000000000) | 27E15 (27000000000000000)| (80%, 10%)                     |
| 1E18 (1000000000000000000) | 3E18 (3000000000000000000) | 29E15 (29000000000000000)| (80%, 11%)                     |
| 1E18 (1000000000000000000) | 3E18 (3000000000000000000) | 50E15 (50000000000000000)| (80%, 17%)                     |
|                           |                           |                       |                                |

**Parameters Explained:**

- **Lower Bound Rate [wei]:** The minimum interest rate a pool can have, even at zero utilization. Represented in wei (1 ETH = 1E18 wei).
- **Upper Bound Rate [wei]:** The maximum interest rate a pool can target, typically at very high utilization levels. Represented in wei.
- **Mul-Factor [wei]:** A multiplier that influences the steepness of the interest rate curve, particularly how quickly the rate increases as utilization rises towards the target point (e.g., 90% or 80% utilization).
- **Target (Utilization %, Rate %):** This column indicates the desired borrow APY at a specific pool utilization percentage. For example, a target of (90%, 5%) means the parameters in that row are chosen to achieve a 5% borrow APY when the pool's utilization reaches 90%.

By adjusting these parameters, different risk/reward profiles can be established for various lending pools, reflecting the specific characteristics and market dynamics of the underlying assets.
