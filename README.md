# Foundry Lottery Smart Contract

## Description

- This is a proveably random smart contract lottery.
- The users can enter the lottery by paying a fee for the ticket.
- After the set period of time, the lottery will automatically draw a winner and the fees that are collected through tickets from all the users will got to the Winner.
- This is done by using
  - Chainlink VRF: For the lottery Randomness
  - Chainlink Automation: A time based Trigger.

## Test Deployment

- The contract was deployed on the SEPOLIA Network. The deployed contract was successfully verified and is at [`0x85dF4F8607E0615Ddf77df08C1AF24393e1CcB7f`](https://sepolia.etherscan.io/address/0x85df4f8607e0615ddf77df08c1af24393e1ccb7f#code)

## Tests!

1. Write some deploy scripts
2. Write the tests
   1. Work on local chain
   2. Forked Testnet
   3. Forked Mainnet

## Commands

- Fund a VRF Subscription from CLI

  ```
  forge script script/Interactions.s.sol:FundSubscription --rpc-url $SEPOLIA_RPC_URL --private-key $PRIVATE_KEY --broadcast -vvvv
  ```

- Test on a fork-url

  ```
  forge test --fork-url $SEPOLIA_RPC_URL
  ```

- To get a report of the test coverage
  ```
  forge coverage --report debug > coverage.txt
  ```
- Verify Contract Script
  ```
  forge verify-contract 0x85dF4F8607E0615Ddf77df08C1AF24393e1CcB7f src/Raffle.sol:Raffle --etherscan-api-key $ETHERSCAN_API_KEY --chain-id 11155111 --compiler-version 0.8.18 --watch
  ```
