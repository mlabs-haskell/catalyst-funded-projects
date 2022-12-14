# Apropos

Property tests help ensure mission-critical dApps don’t contain vulnerabilities. They accomplish this by verifying formal properties are upheld throughout code blocks. This is opposed to unit tests which simply assure atomic pieces of code return the correct, anticipated value.  For Haskell, QuickCheck is a groundbreaking and affective tool for developing property tests.

However, writing tests to check every contract permutation and edge-case state is exhausting, if not wholly impossible. Apropos is a metaprogramming toolkit for generating QuickCheck-style property tests from a logical model. This is a particularly powerful approach because the logical model in question can be complex representing thousands of solutions, each of which can become a property test. 

Overall, this makes thorough testing of code simpler – a lot of the heavy lifting is automated – while ensuring edge cases are not overlooked. Our Fund9 Apropos proposal seeks to build out the Apropos project, already underway, to effectively and effortlessly provide more extensive testing and security assurances for Cardano DApps.

Project ID: [900151](https://docs.google.com/spreadsheets/d/1bfnWFa94Y7Zj0G7dtpo9W1nAYGovJbswipxiHT4UE3g/edit#gid=917336114)

## Current Status

Bootstrapping. 

## Progress Report

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
