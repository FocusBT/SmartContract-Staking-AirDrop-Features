# MyToken Smart Contract



# Description:
The MyToken contract implements a modified version of the ERC20 standard along with added functionality for staking, blacklisting, and rewarding token holders. The contract is deployed by the contract owner and initially mints a fixed supply of tokens that are added to the contract owner's account.

# Key Features:
**Minting**: The contract owner can mint tokens to any specified address.

**Blacklisting**: The contract owner can blacklist any address. Blacklisted addresses are restricted from staking.

**Staking**: Addresses can stake a specified amount of tokens in the contract. The staking process includes claiming rewards which are based on the amount staked and the duration of the stake.

**Reward Distribution**: The contract implements a reward system, where each transfer contributes to various rewards pools (Liquidity, wheel, reflections, instant reward). Additionally, an array is maintained with the addresses of all token holders who make a transfer within a specific time window. These addresses are eligible to win rewards.

**Airdrops**: The contract owner can enable or disable airdrops. If airdrops are enabled, addresses with a balance above a certain threshold become eligible for airdrops.

**DevWallets**: The contract owner can flag addresses as development wallets. These flagged addresses have different transfer fee rules applied to them.

**Anti-bot**: To discourage frequent transfers, the contract implements an anti-bot feature. After each transfer, an address must wait at least 10 minutes before initiating another transfer.

**Customizable Transfer Fees**: When tokens are transferred or approved, a percentage of the amount is deducted as fees and divided among several pools. The rules for fee deductions are different based on whether the recipient is flagged as a dev wallet or not.



Built with:
Solidity ^0.8.4
OpenZeppelin Contracts
Please note, that this contract uses the version of Solidity that is specified as ^0.8.4. Always use the appropriate version of Solidity that matches the contract to avoid potential compatibility issues.

```shell
npx hardhat help
npx hardhat test
REPORT_GAS=true npx hardhat test
npx hardhat node
npx hardhat run scripts/deploy.js
```
