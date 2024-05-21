# Real Estate Vault (RESTV) Smart Contract - BEP-20 Token

This repository contains the smart contract for the Real Estate Vault (RESTV) token. The contract is built using Solidity and includes various features such as dividend distribution, fee handling, and ownership management.

## Contract Overview

The Real Estate Vault contract is a BEP-20 token with the following features:
- **Dividend Distribution:** Automatically distributes dividends to holders.
- **Fee Handling:** Handles various fees including liquidity, reflection, marketing, and development fees.
- **Ownership Management:** Includes functions for ownership transfer and authorization management.
- **Blacklist Management:** Allows for blacklisting addresses.
- **Cooldown and Transaction Limits:** Implements cooldown periods and transaction limits for trading.

## Contract Address

The contract address for the USDT token (RWRD) used for dividend distribution:
- **USDT Token (RWRD):** `0x55d398326f99059fF775485246999027B3197955`

## Features

### SafeMath Library
Provides safe mathematical operations for addition, subtraction, multiplication, and division to prevent overflow and underflow errors.

### IBEP20 Interface
Defines the standard interface for BEP-20 tokens, including functions for transferring tokens, checking balances, and approving allowances.

### Auth Contract
Manages ownership and authorization, allowing for specific addresses to be authorized for certain actions.

### Dividend Distributor
Handles the distribution of dividends to token holders based on their share of the total supply.

### Main Contract (REALESTATEVAULT)
Implements the BEP-20 token with additional features such as:
- **Trading:** Ability to enable or disable trading.
- **Fee Management:** Setting and adjusting various fees.
- **Blacklist Management:** Enabling or disabling blacklist mode and managing blacklisted addresses.
- **Cooldown Periods:** Implementing cooldown periods between trades.

## Usage

### Deployment
To deploy the contract, you will need to use a Solidity compiler compatible with version 0.8.20 and have access to a Binance Smart Chain (BSC) node.

### Interacting with the Contract
You can interact with the contract using tools like Remix, Truffle, or directly via Web3 libraries. Below are some of the key functions available:

#### Owner Functions
- `authorize(address adr)`: Authorizes an address.
- `unauthorize(address adr)`: Revokes authorization from an address.
- `renounceOwnership()`: Renounces ownership of the contract.
- `transferOwnership(address newOwner)`: Transfers ownership to a new address.
- `setMaxWalletPercent_base1000(uint256 maxWallPercent_base1000)`: Sets the maximum wallet holding percentage.
- `setMaxTxPercent_base1000(uint256 maxTXPercentage_base1000)`: Sets the maximum transaction percentage.
- `enable_blacklist(bool _status)`: Enables or disables blacklist mode.
- `manage_blacklist(address[] calldata addresses, bool status)`: Manages blacklisted addresses.

#### Public Functions
- `transfer(address recipient, uint256 amount)`: Transfers tokens to a specified address.
- `approve(address spender, uint256 amount)`: Approves a spender to transfer tokens on behalf of the caller.
- `claimDividend()`: Claims dividends for the caller.
- `setDistributionCriteria(uint256 _minPeriod, uint256 _minDistribution)`: Sets the criteria for dividend distribution.
- `setShare(address shareholder, uint256 amount)`: Sets the share for a specific shareholder.
- `deposit()`: Deposits BNB into the contract for dividend distribution.

### Events
- `Transfer(address indexed from, address indexed to, uint256 value)`: Emitted when tokens are transferred.
- `Approval(address indexed owner, address indexed spender, uint256 value)`: Emitted when an approval is made.
- `OwnershipTransferred(address owner)`: Emitted when ownership is transferred.
- `AutoLiquify(uint256 amountBNB, uint256 amountTokens)`: Emitted when liquidity is added automatically.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contributing

Contributions are welcome! Please fork the repository and create a pull request with your changes. Ensure that your code follows the Solidity style guidelines and includes appropriate tests.

## Contact

For any questions or support, please open an issue in the repository or contact the project maintainers.

---

**Note:** This smart contract is provided as-is and without any warranties. Use it at your own risk.
