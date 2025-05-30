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

| Lower Bound [wei] | Upper Bound [wei] | Mul-Factor [wei] | Aim (Utilization %, Rate %) |
| :-------------- | :-------------- | :------------- | :------------------------- |
| 1000000000000000000 | 3000000000000000000 | 4000000000000000 | (90%, 3%) |
| 1000000000000000000 | 3000000000000000000 | 5000000000000000 | (90%, 4%) |
| 1000000000000000000 | 3000000000000000000 | 6000000000000000 | (90%, 5%) |
| 1000000000000000000 | 3000000000000000000 | 6500000000000000 | (90%, 5.5%) |
| 1000000000000000000 | 3000000000000000000 | 7000000000000000 | (90%, 6%) |
| 1000000000000000000 | 3000000000000000000 | 8000000000000000 | (90%, 7%) |
| 1000000000000000000 | 3000000000000000000 | 10000000000000000 | (90%, 8%) |
| 1000000000000000000 | 3000000000000000000 | 13000000000000000 | (90%, 11%) |
| 1000000000000000000 | 3000000000000000000 | 14500000000000000 | (90%, 12%) |
| 1000000000000000000 | 3000000000000000000 | 18000000000000000 | (90%, 14%) |
| 1000000000000000000 | 3000000000000000000 | 19000000000000000 | (90%, 15%) |
| 1000000000000000000 | 3000000000000000000 | 22000000000000000 | (90%, 17%) |
| 1000000000000000000 | 3000000000000000000 | 25000000000000000 | (90%, 20%) |
| 1000000000000000000 | 3000000000000000000 | 30000000000000000 | (90%, 24%) |
| 1000000000000000000 | 3000000000000000000 | 35000000000000000 | (90%, 28%) |
| 1000000000000000000 | 3000000000000000000 | 40000000000000000 | (90%, 32%) |
| 1000000000000000000 | 3000000000000000000 | 45000000000000000 | (90%, 36%) |
| 1000000000000000000 | 3000000000000000000 | 50000000000000000 | (90%, 40%) |
| 1000000000000000000 | 3000000000000000000 | 8000000000000000 | (80%, 3%) |
| 1000000000000000000 | 3000000000000000000 | 10000000000000000 | (80%, 4%) |
| 1000000000000000000 | 3000000000000000000 | 17500000000000000 | (80%, 7%) |
| 1000000000000000000 | 3000000000000000000 | 22000000000000000 | (80%, 8%) |
| 1000000000000000000 | 3000000000000000000 | 224000000000000000 | (80%, 9%) |
| 1000000000000000000 | 3000000000000000000 | 27000000000000000 | (80%, 10%) |
| 1000000000000000000 | 3000000000000000000 | 29000000000000000 | (80%, 11%) |
| 1000000000000000000 | 3000000000000000000 | 50000000000000000 | (80%, 17%) |
|                           |                           |                       |                                |

**Parameters Explained:**

- **Lower Bound Rate [wei]:** The minimum interest rate a pool can have, even at zero utilization. Represented in wei (1 ETH = 1E18 wei).
- **Upper Bound Rate [wei]:** The maximum interest rate a pool can target, typically at very high utilization levels. Represented in wei.
- **Mul-Factor [wei]:** A multiplier that influences the steepness of the interest rate curve, particularly how quickly the rate increases as utilization rises towards the target point (e.g., 90% or 80% utilization).
- **Target (Utilization %, Rate %):** This column indicates the desired borrow APY at a specific pool utilization percentage. For example, a target of (90%, 5%) means the parameters in that row are chosen to achieve a 5% borrow APY when the pool's utilization reaches 90%.

By adjusting these parameters, different risk/reward profiles can be established for various lending pools, reflecting the specific characteristics and market dynamics of the underlying assets.
