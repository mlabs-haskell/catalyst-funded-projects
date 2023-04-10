# Apropos

Property tests help ensure mission-critical dApps don’t contain vulnerabilities. They accomplish this by verifying formal properties are upheld throughout code blocks. This is opposed to unit tests which simply assure atomic pieces of code return the correct, anticipated value.  For Haskell, QuickCheck is a groundbreaking and affective tool for developing property tests.

However, writing tests to check every contract permutation and edge-case state is exhausting, if not wholly impossible. Apropos is a metaprogramming toolkit for generating QuickCheck-style property tests from a logical model. This is a particularly powerful approach because the logical model in question can be complex representing thousands of solutions, each of which can become a property test. 

Overall, this makes thorough testing of code simpler – a lot of the heavy lifting is automated – while ensuring edge cases are not overlooked. Our Fund9 Apropos proposal seeks to build out the Apropos project, already underway, to effectively and effortlessly provide more extensive testing and security assurances for Cardano DApps.

Project ID: [900151](https://docs.google.com/spreadsheets/d/1bfnWFa94Y7Zj0G7dtpo9W1nAYGovJbswipxiHT4UE3g/edit#gid=917336114)


## Progress Reports

### April 2023

Progress on Apropos continued focusing on the Hedgehog-plutus-simple dependency. Notably, team members switched to testing frameworks fro from Hedgehog to Tasty. This allows making scripts into unit tests:
https://github.com/mlabs-haskell/hedgehog-plutus-simple/pull/63

And merged scriptTxValid changes implementing the ChainState data type and scriptTxValid for checking tx validity:
https://github.com/mlabs-haskell/hedgehog-plutus-simple/pull/62

Finally, there was some code cleanup:
https://github.com/mlabs-haskell/hedgehog-plutus-simple/commit/e89be86b3a9e5550ac3d8c6b343621030733b2ba

### March 2023

On the Hedgehog dependency, chain state initialization was added: 
https://github.com/mlabs-haskell/hedgehog-plutus-simple/pull/49

The test harness was integrated and added to
https://github.com/mlabs-haskell/hedgehog-plutus-simple/pull/43/commits/d2c83d54d192cef0cb75617f5e452b2136143c28
https://github.com/mlabs-haskell/hedgehog-plutus-simple/pull/45

The project was also built within the Pioneer program English Auction:
https://github.com/mlabs-haskell/hedgehog-plutus-simple/pull/46

And HKDs and an HKD newtype and its instances were added to the testing data:
https://github.com/mlabs-haskell/hedgehog-plutus-simple/pull/59

Moreover, the ability to run scripts was added as well as positive and negative tests for verification:

https://github.com/mlabs-haskell/hedgehog-plutus-simple/pull/58


Finally, the spendScriptUntyped helper function was added to the Contract model module of the plutus-simple-model dependency
https://github.com/mlabs-haskell/plutus-simple-model/commit/650f9584af2f3ab251bda2ae034b4eaee6d5b35d


### February 2023

Work continued implementing functions for adjunction architecture:
https://github.com/mlabs-haskell/hedgehog-plutus-simple/pull/11
https://github.com/mlabs-haskell/hedgehog-plutus-simple/pull/10
https://github.com/mlabs-haskell/hedgehog-plutus-simple/pull/16

as well as a Mockchain wrapper layer:
https://github.com/mlabs-haskell/hedgehog-plutus-simple/pull/14

The Hedgheog-plutus-simple dependency was also addressed. Specifically, more script contexts were added:
https://github.com/mlabs-haskell/hedgehog-plutus-simple/pull/30

alongside the integration of Cardano-simple and documentation updates
https://github.com/mlabs-haskell/hedgehog-plutus-simple/pull/25
https://github.com/mlabs-haskell/hedgehog-plutus-simple/pull/28


Finally, instances of untyped scripts were added to the PSM dependency:
https://github.com/mlabs-haskell/plutus-simple-model/pull/71

While other work here aimed at further Babbage support:
https://github.com/mlabs-haskell/plutus-simple-model/pull/95
https://github.com/mlabs-haskell/plutus-simple-model/pull/90

### January 2023

Over the last month, we focused on example contracts and state machines
https://github.com/mlabs-haskell/hedgehog-plutus-simple/commit/9a14c7560b53a326b649f79391f8140600823d46 
https://github.com/mlabs-haskell/hedgehog-plutus-simple/commit/3df0a01e36a8a40b255de1899b4165871e026096

And performed some maintenance work for plutus-simple-model - untyped validators and Plutarch scripts, as well as bug fixing and cleanup
https://github.com/mlabs-haskell/plutus-simple-model/commit/6557212cd8ba34361fda7821fe3c3e28461f51f8
https://github.com/mlabs-haskell/plutus-simple-model/commit/98fcf391ba614e04b749857b29c12740de35332a


Finally, we focused heavily on the balanceTx function and ensuring it balances correctly, and updating documentation
https://github.com/mlabs-haskell/hedgehog-plutus-simple/commit/f562d4ae6a37184f77876c602b8521b855f6fb35
https://github.com/mlabs-haskell/hedgehog-plutus-simple/commit/9a8bda4e370e2ce1c569272ea73155814349b1f2
https://github.com/mlabs-haskell/hedgehog-plutus-simple/commit/8ae7f7f0263e5381dd05a0564d3369ed834bb612

### December 2022

Over the last month, some fundamental considerations of the Apropos project were revisted - part of the project reboot following the pause mentioned last month. Specifically, this included:

* addressing repo under-documentation
* reliance on StrictData
* handling undefined data
* compliance with our internal style guide
* the repo structure and dependence on the Hedgehog library
* the broader object of the project

That said, the main updates are likely that a reconfigured version of the Plutus.Simple.Model has been merged, and type formatting was readressed.

### November 2022

The Apropos project was rebooted last month after a successful Fund9 campaign. Since then, the repo has been refactored to support GHC 9 and it currently builds with GHC 9.2. This is an encouraging development as this was an early milestone of the Fund9 proposal.

Moving forward, a handful of other issues have been addressed while others have been recently identified. At its core, Apropos relies on the Plutus-simple-model, a fast and easy-to-use testing library for writing unit tests for DApp transactions against a mock model blockchain. Since Apropos was unmaintained for a short period, the repo was updated to reflect developments on this dependency.

Finally, some light clerical work was also accomplished. In particular, the repo was brought into line with our internal style guide. Meanwhile, unnecessary dependencies were also removed making the project more lightweight overall.

### October 2022

Fund9 vote results were announced in late September and our Apropos proposal was successfully supported by Catalyst voters. We have established a team to work on the project and are currently awaiting the first batch of Fund9 payments before beginning work.

## Further Information

Apropos Repo: https://github.com/mlabs-haskell/apropos

Apropos-tx Repo: https://github.com/mlabs-haskell/apropos-tx

MLabs Website: https://mlabs.city

MLabs Twitter: https://twitter.com/MLabs10

MLabs Contact: info@mlabs.city
