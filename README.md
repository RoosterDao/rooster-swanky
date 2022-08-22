# rooster-swanky

## Introduction

The setup of this project depends on 4 other projects all bundled in this composed project:
* [Swanky-node](https://github.com/AstarNetwork/swanky-node)
* [Rooster contracts](https://github.com/RoosterDao/rooster-contracts) *swank-node* branch
* [Rooster DAO UI](https://github.com/RoosterDao/rooster-dao-ui) 
* [Rooster NFT viewer]()

You can install all these projects following the instructions from different repositories, but using this composite repository will allow you to install tested versions of all of the above.

## Setting up the repository

Clone this repository and init the submodules

    $ git clone git@github.com:RoosterDao/rooster-swanky.git
    $ cd rooster-swanky
    $ git submodule init
    $ git submodule update

Please refer to the documentation of each project for a more detailed guidance on the building process.

## Swanky-node

To compile the Substrate Swanky node:

    $ cd swanky-node
    $ cargo build --release
    ...
    Compiling sc-cli v0.10.0-dev (https://github.com/paritytech/substrate.git?branch=polkadot-v0.9.27#8eff668a)
    Compiling frame-benchmarking-cli v4.0.0-dev (https://github.com/paritytech/substrate.git?branch=polkadot-v0.9.27#8eff668a)
    Compiling swanky-node v0.9.1 (/tmp/rooster-swanky/swanky-node/node)
    Finished release [optimized] target(s) in 8m 25s

    
To run the freshly build node in development mode you can issue the following:

    $ ./target/./target/release/swanky-node --dev
    2022-08-22 15:52:19 Swanky Node    
    2022-08-22 15:52:19 ✌️  version 0.9.1-9b1bdb793de    
    2022-08-22 15:52:19 ❤️  by Astar Network, 2022-2022    
    2022-08-22 15:52:19 📋 Chain specification: Development    
    2022-08-22 15:52:19 🏷  Node name: grumpy-question-0526    

You can verify the status of your node using [polkadot.js exlorer](https://polkadot.js.org/apps/?rpc=ws%3A%2F%2F127.0.0.1%3A9944#/explorer)

### Rooster Contracts

    $ cd rooster-contracts/
    $ cd contracts/governor/
    $ cargo +nightly contract build
    ...
    Compiling governor v0.0.1 (/tmp/cargo-contract_ebdc4J)
    Compiling metadata-gen v0.1.0 (/tmp/cargo-contract_ebdc4J/.ink/metadata_gen)
    Finished release [optimized] target(s) in 38.05s
    Running `target/ink/release/metadata-gen ''`
    [5/5] Generating bundle
    
    Original wasm size: 116.0K, Optimized: 63.2K
    
    The contract was built in DEBUG mode.

    Your contract artifacts are ready. You can find them in:
    /tmp/rooster-swanky/rooster-contracts/contracts/governor/target/ink

     - governor.contract (code + metadata)
     - governor.wasm (the contract's code)
     - metadata.json (the contract's metadata)
     
 After succesful completion the WASM contract is generated. You can use the [polkadot.js exlorer](https://polkadot.js.org/apps/?rpc=ws%3A%2F%2F127.0.0.1%3A9944#/explorer) to deploy the contract manually and interact with it.

### Rooster DAO UI

### Rooster NFT Viewer

## Run

