# IDO Pool Smart Contract

This is a Solidity smart contract for an Initial DEX Offering (IDO) pool and a staking pool. The contract allows users to participate in three rounds of token sales, claim their tokens, and stake their tokens in the staking pool for rewards.

## IDO Pool Contract Details

- Solidity version: 0.8.0
- SPDX-License-Identifier: MIT
- Inherits from: `Ownable`, `ReentrancyGuard`

## Staking Pool Contract Details

- Solidity version: 0.8.0
- SPDX-License-Identifier: MIT
- Inherits from: `Ownable`

## Dependencies

The contracts depend on the following external contracts:

- `SafeMath.sol`: A library for safe mathematical operations.
- `Ownable.sol`: A contract that provides basic authorization control.
- `ReentrancyGuard.sol`: A contract that prevents reentrancy attacks.
- `ERC20.sol`: An interface for the ERC20 token standard.
- `STRToken.sol`: A contract representing the STR token.

## Functionality

The IDO Pool contract provides the following functionality:

1. Initialization: The contract is initialized with various parameters, including token price, reward token contract address, round timestamps, funding goal, and total supply.
2. Token Purchase: Users can purchase tokens during each round by sending USDC to the contract. The contract verifies the round availability and eligibility criteria.
3. Claim Tokens: Once the distribution period begins, users can claim their tokens based on the number of tokens they have purchased. The claimed tokens are transferred to the user's address.
4. Refund: If the total distribution for a round is lower than the funding goal, users can request a refund of the excess USDC they have deposited.
5. Whitelist Management: The contract owner can add addresses to the whitelist for each round to allow eligible users to participate.
6. Pool Allotment: The contract automatically divides investors into different pools based on their staking status. The allocation of tokens to each pool is calculated and executed.
7. Withdrawal: The contract owner can withdraw the remaining USDC from the contract once the distribution period is over.

The Staking Pool contract provides the following functionality:

1. Staking: Users can stake their STR tokens in the staking pool to earn rewards.
2. Unstaking: Users can unstake their tokens after a specified lock-in period and receive their staked tokens along with rewards.
3. Rewards Calculation: The contract calculates rewards based on the staking duration and the specified annual percentage yield (APY).
4. Withdrawal: Users can withdraw their unstaked tokens along with rewards once the lock-in period is over.

## Usage

To use the IDO Pool and Staking Pool contracts, follow these steps:

1. Deploy the contracts on the Ethereum network using a compatible development environment.
2. Set the required parameters during contract initialization, such as token price, reward token contract address, round timestamps, funding goal, and total supply.
3. Deploy or link the required dependencies, including `SafeMath.sol`, `Ownable.sol`, `ReentrancyGuard.sol`, `ERC20.sol`, and `STRToken.sol`.
4. Allow users to purchase tokens during each round by calling the respective `buyTokenRoundX` function in the IDO Pool contract.
5. Start the distribution period and allow users to claim their tokens using the `claim` or `claimFor` functions in the IDO Pool contract.
6. If necessary, refund excess USDC to eligible users by calling the corresponding `refundUSDCRoundX` functions in the IDO Pool contract.
7. Manage the whitelist for each round by calling the `addToWhitelistRoundX` functions in the IDO Pool contract.
8. Allocate tokens to different staking pools automatically based on staking status using the `poolAllotment` function in the IDO Pool contract.
9. Users can stake their STR tokens by calling the `stakeTokens` function in the Staking Pool contract.
10. Users can unstake their tokens and claim rewards by calling the `unstakeTokens` function in the Staking Pool contract.
11. Calculate rewards for stakers based on the staking duration using the `calculateRewards` function in the Staking Pool contract.
12. Users can withdraw their unstaked tokens and rewards by calling the `withdraw` function in the Staking Pool contract.

## License

The IDO Pool and Staking Pool contracts are released under the MIT License. See the [LICENSE](./LICENSE) file for more details.

