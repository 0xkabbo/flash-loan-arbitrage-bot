# Flash Loan Arbitrage Bot

This repository contains a professional-grade Solidity smart contract and supporting scripts designed to execute Flash Loans. It leverages the Aave V3 protocol to borrow assets, perform a trade across two different decentralized exchanges, and repay the loan in a single atomic transaction.

## Features
- **Collateral-Free Borrowing**: Utilize Aave Flash Loans to access deep liquidity.
- **Atomic Transactions**: Ensures that if the arbitrage trade is not profitable, the entire transaction reverts, protecting the user from losses (except gas).
- **Multi-DEX Routing**: Logic for swapping tokens between Uniswap V2/V3 and Sushiswap.
- **Flat Structure**: Simplified root-level organization for easy copy-pasting into Remix or Hardhat.

## Arbitrage Logic
The bot seeks a price discrepancy ($P$) between DEX A and DEX B. The profit is calculated as:

$$\text{Profit} = (\text{Amount}_{out} - \text{Amount}_{in}) - \text{Fee}_{flashloan} - \text{Gas}$$

If $\text{Profit} > 0$, the transaction executes. Otherwise, it fails, and the loan is never taken.



## License
MIT
