# Simple Storage

## About

A basic smart contract that allow user to set favorite number and retrieve it.

## Foundry - Set up

1. run `curl -L https://foundry.paradigm.xyz | bash` this will install foundryup.
2. run `foundryup` to install forge, cast, anvil and chisel.

## Initialize Foundry project

Create a directory and run,

```bash
forge init
```

It will create a basic starter project

## Local deployment

1. Open a new terminal and run
   ```bash
   anvil
   ```
   This will spin up the local blockchain
2. Compile and build the project
   ```bash
   forge build
   ```
3. To deploy using command line run,
   ```bash
   forge create SimpleStorage --private-key <private_key>
   ```
4. To deploy using script file run
   ```bash
   forge script script/SimpleStorage.s.sol --rpc-url http://127.0.0.1:7545 --private-key <private_key> --broadcast
   ```
5. To execute the test run
   ```bash
   forge test --match-path test/SimpleStorage.t.sol
   ```

## Interact with deployed contract

1. To set new favorite number
   ```bash
   cast send <contract_address> "store(uint256)" 777 --rpc-url http://127.0.0.1:7545 --private-key <private_key>
   ```
2. To view new favorite number
   ```bash
   cast call <contract_address> "retrieve()" --rpc-url http://127.0.0.1:7545
   ```
   then `cast --to-base <hex_value> dec` to get the decimal output.
