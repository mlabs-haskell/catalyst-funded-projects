# Cardano-Transaction-Library 
The [Cardano-Transaction-Library (CTL)](https://cardano.ideascale.com/c/idea/396607) is an SDK for making and balancing transactions for browser-based wallets and JavaScript environments. It is intended as an analog for the web3.js libraries available on Ethereum.

Project ID: [00255](https://docs.google.com/spreadsheets/u/0/d/1bfnWFa94Y7Zj0G7dtpo9W1nAYGovJbswipxiHT4UE3g/htmlview#)

GitHub Repo: https://github.com/Plutonomicon/cardano-transaction-lib


## Proposal Roadmap

- [x] **Stage 1** Build a simple transaction in the browser that works with at least one light wallet (Nami)
- [x] **Stage 2** Once we can construct a simple user-to-user transaction, we will try to use the library to submit the tx with nami
- [x] **Stage 3** Once we have a simple working transaction, we will seek to build a Plutus smart contract transaction with datum from scratch
- [x] **Stage 4** Once we can construct Plutus smart contract transactions, we will seek to build a library/DSL/interface such that transactions can be built using constraints and lookups - as close as possible to a cut-and-paste solution from Plutus' `Contract` monad code in Haskell (but with no guarantee that code changes are not necessary)
  - [ ] **Stage 4.1** Investigate supporting compatibility with the Vasil hardfork and improvements to our initial `Contract` API (**In progress**)
- [ ] **Stage 5** Once we have a basic `Contract`-style API, we will further refine its public interface, expand wallet support (see [below](#light-wallet-support)), expose a test interface (see [here](doc/plutip-testing.md)), provide a more ergonomic JS/TS API, support stake validators, and support CIP workflows on the public testnet
- [ ] **Stage 6** Once CTL's `Contract` interface has been stabilized, we will add support for even more wallets and attempt to deprecate CTL's currently required Haskell server

## Current Status

v2.0.0 currently in beta.

Integration into the [Seabug NFT Marketplace](https://seabug.io/) coming soon.

## Progress Report


## Demo Overview


## Further Information

CTL GitHub Repo: https://github.com/Plutonomicon/cardano-transaction-lib

Seabug Contracts Used with CTL: https://github.com/mlabs-haskell/seabug-contracts

Seabug Website: https://https://seabug.io/

Seabug Medium: https://seabug.medium.com/

Seabug Discord: http://discord.gg/UZUCJbTAG6

MLabs Website: https://mlabs.city

MLabs Contact: info@mlabs.city
