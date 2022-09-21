# Cardano-Transaction-Library 
The [Cardano-Transaction-Library (CTL)](https://cardano.ideascale.com/c/idea/396607) is an SDK for making and balancing transactions for browser-based wallets and JavaScript environments. It is intended as an analog of the web3.js libraries available on Ethereum.

Project ID: [800255](https://docs.google.com/spreadsheets/u/0/d/1bfnWFa94Y7Zj0G7dtpo9W1nAYGovJbswipxiHT4UE3g/htmlview#)

GitHub Repo: https://github.com/Plutonomicon/cardano-transaction-lib


## Proposal Roadmap

- [x] **Stage 1** Build a simple transaction in the browser that works with at least one light wallet (Nami)
- [x] **Stage 2** Once we can construct a simple user-to-user transaction, we will try to use the library to submit the tx with Nami
- [x] **Stage 3** Once we have a simple working transaction, we will seek to build a Plutus smart contract transaction with datum from scratch
- [x] **Stage 4** Once we can construct Plutus smart contract transactions, we will seek to build a library/DSL/interface such that transactions can be built using constraints and lookups - as close as possible to a cut-and-paste solution from Plutus' `Contract` monad code in Haskell (but with no guarantee that code changes are not necessary)
  - [ ] **Stage 4.1** Investigate supporting compatibility with the Vasil hardfork and improvements to our initial `Contract` API (**In progress**)
- [ ] **Stage 5** Once we have a basic `Contract`-style API, we will further refine its public interface, expand wallet support, expose a test interface, provide a more ergonomic JS/TS API, support stake validators, and support CIP workflows on the public testnet
- [ ] **Stage 6** Once CTL's `Contract` interface has been stabilized, we will add support for even more wallets and attempt to deprecate CTL's currently required Haskell server

### Light wallet support

Support is planned for the following light wallets:

- [x] [Nami](https://namiwallet.io/)
- [x] [Gero](https://gerowallet.io/)
- [x] [Flint](https://flint-wallet.com/)
- [ ] [Lace](https://www.lace.io/)
- [ ] [Typhon](https://typhonwallet.io/)
- [ ] [Yoroi](https://yoroi-wallet.com/)
- [ ] [Eternl (formerly CCvault)](https://eternl.io/)


## Current Status

v2.0.0 currently in beta.

Integration with [Seabug NFT Marketplace](https://seabug.io/) and other client projects ongoing. 

Freeze on new features until Vasil hardfork has concluded.


## Progress Report

### September 2022

The CTL team focused primarily on optimizations and ergonomics over the last month as well as integrating support for Babbage. Several issues were managed and merged, including:
* Updates to Flakes package manager for Nix
* Fixing Babbage bugs 
* Tx pretty printers
* Parsing inline datums
* Optimization of local testing environments  (Plutip support, suppressing logging, preprod testnet deployment, etc.)
* Initial Hydra integration
* Additional wallet support (Lode, mock wallets)
* Released [demo video](https://www.youtube.com/watch?v=P0imLF6QvuM) of CTL as experienced using Seabug, an NFT marketplace

That said, the CTL team is thrilled to announce the release of CTL v2.0.0. Although further milestones remain, the main update involves support for Babbage-era features, not least of which is reference script support. Among other upgrades, the team:
* Improved the constraints interface
* Improved the constraints API while mostly maintaining backward compatibility
* Released example contracts highlighting new features

Details, build instructions, further documentation, and so on is available via the [CTL Git repo](https://github.com/Plutonomicon/cardano-transaction-lib).

### August 2022

Despite initial progress, team members faced significant difficulties first assimilating the CTL with major DApps. The mechanics of DApp actions exposed several bugs, and we realized how our library must be adapted to individual use cases. Fortunately, hurdles were by and large surmounted, and testing and iterative development helped stabilize applications. 

Yet, work remains as the approaching hardfork introduced a new set of challenges. Vasil offers significant improvements to how smart contract systems transact and are structured. While exciting, these low-level optimizations mean dramatic changes to codebases. This is particularly true of light wallets, essentially the end-user of the CTL. As the Cardano ecosystem shifts, we are focused on absorbing the upgrades as smoothly as possible and addressing user issues. Development of most new features has been frozen until stability is regained, and team members are instead fine-tuning error handling and the developer experience.

### July 2022

Early CTL development was slow as team members were forced to ramp up on several distinct technologies at once (PureScript, Ogmios API, Cardano Node, etc.). Moreover, chain information and transaction builds were not straightforward to query and automate. The Cardano Node and the complex nature of eUTXO transactions forced developers to handle awkward and unfamiliar data structures, delaying functionality and early testing.

That said, we have made substantial progress to date. It should be noted that CTL began development in December 2021 after similar solutions were deemed inadequate to manage DApp off-chain actions. MLabs internally funded the CTL throughout the lengthy Fund8 process. We were able to get a head start and accomplish several of our goals before the results were even known. Excitingly, v1.0.0 of the CTL was released in June 2022 and we have continued building. As such, we are pleased to report we were able to extend the scope and vision of the project as we accomplish our original milestones. In particular, the library supports a greater variety of light wallets than initially imagined. Furthermore, CTL is reliably integrated with Plutip, a testnet contract testing tool we developed separately. 


## Demo Overview

[Video demo](https://www.youtube.com/watch?v=P0imLF6QvuM), published September 2022, features the CTL in use on [Seabug](http://page.seabug.io/), an NFT marketplace.

## Further Information

CTL GitHub Repo: https://github.com/Plutonomicon/cardano-transaction-lib

Seabug Contracts Used with CTL: https://github.com/mlabs-haskell/seabug-contracts

Seabug Website: https://seabug.io/

Seabug Medium: https://seabug.medium.com/

Seabug Discord: http://discord.gg/UZUCJbTAG6

MLabs Website: https://mlabs.city
 
MLabs Twitter: https://twitter.com/MLabs10
 
MLabs Contact: info@mlabs.city
