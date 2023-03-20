# CTL Blockfrost Backend

The [Cardano-Transaction-Library (CTL)](https://github.com/Plutonomicon/cardano-transaction-lib) is a toolkit for developers to build transactions for the Cardano Blockchain. Reaching version 1.0 in June 2022 and already seeing on-chain adoption on several large-scale industrial dApps, the CTL is currently using Ogmios to fill this gap. Ogmios is a self-hosted solution, and some features available on Blockfrost are not available from Ogmios, necessitating additional infrastructure. Furthermore, upcoming changes may result in Ogmios being replaced.

A clear alternative approach to making CTL more versatile and useful is to allow Blockfrost as an alternative backend service. Instead of running their own servers, users provide a Blockfrost API key and any other required configuration. However, the maintenance of their server may be greatly reduced or eliminated. Due to the relative ease of use, it's expected that many developers will use the Blockfrost service as a default during development and production. This proposal seeks to accomplish this integration.

Project ID: Project ID: [900154](https://docs.google.com/spreadsheets/d/1bfnWFa94Y7Zj0G7dtpo9W1nAYGovJbswipxiHT4UE3g/edit#gid=917336114)

## Progress Reports

### March 2023

We are happy to announce that we were able to deliver our CTL Blockfrost backend project. We were able to frontload development obilgations and are happy to have finished ahead of schedule. 

Please see our closeout demo available here: 
https://www.youtube.com/watch?v=zP4O8jRVlKg&t=2s

### February 2023

Over the last month, team members focused on wallet integration and functionality as well as improvements to testing and documentation. This included Plutip integration:

https://github.com/Plutonomicon/cardano-transaction-lib/pull/1260

Furhtermore, a new test runner has been added to make it possible to run tests that are meant to be run with plutip clusters on Blockfrost. The test suite accepts private keys that correspond to a pre-funded address. It takes care of funds distribution for tests that require it, while making sure that no funds are ever lost on temporary addresses.
This PR also includes documentation for the test suite.
https://github.com/Plutonomicon/cardano-transaction-lib/pull/1425

Adding a delay to transaction confirmations to make them more reliable:
https://github.com/Plutonomicon/cardano-transaction-lib/pull/1412

Discussion has been started in the upstream repo, with the aim to make it possible to run Blockfrost with private testnets.
https://github.com/blockfrost/blockfrost-backend-ryo/issues/72

### January 2023

Over the last month strides were made on several outstanding issues focused on Blockfrost integration:

- Implementing getDatumByHash and getScriptByHash queries
https://github.com/Plutonomicon/cardano-transaction-lib/pull/1378/commits

- Implementing utxosAt and getUtxoByOref queries
https://github.com/Plutonomicon/cardano-transaction-lib/pull/1366/commits

- Implementing getChainTip, getEraSummaries, and getSystemStart queries
https://github.com/Plutonomicon/cardano-transaction-lib/pull/1377/commits

- Implementing transaction submission and evaluation queries
https://github.com/Plutonomicon/cardano-transaction-lib/pull/1376/commits

- Implementing retrieval of Tx metadata query
https://github.com/Plutonomicon/cardano-transaction-lib/pull/1368/commits

- Implementing retrieval of info on current epoch
https://github.com/Plutonomicon/cardano-transaction-lib/pull/1372/commits

- Generating fixtures to test JSON decoders for query responses
https://github.com/Plutonomicon/cardano-transaction-lib/pull/1385/commits

- Adding Blockfrost service to our Nix runtime environment (Arion) and Nix development shell (WIP)
https://github.com/Plutonomicon/cardano-transaction-lib/pull/1395

### December 2022

The CTL has undergone some moderate reconfigurations over the last two months. Part of these efforts involved complications stemming from a separate query dependency, while others involved changes to make the project backend more generalizable. For instance, developers made progress:

* considering workarounds for how Blockfrost handles UTXO support 
* designing around Blockfrost's era summaries
* integrating challenges stemming from changes on the Blockfrost end aiming at integrating CIP25

And other issues.

Perhaps more prominent, however, developers focused on configuring the Contract backend. Changes here were probably the most involved over the last month, and they are important in lay grounding for further Blockfrost integration.

### November 2022

Following the Fund9 voting results, MLabs organized a roadmap for integrating Blockfrost endpoints into the API interface of CTL. This piggybacked on early exploratory work we had already done when originally composing our original Fund9 proposal. The timeline identified several key early goals:
* Make Contract runtime and ConfigParams parametrizable with a backend.
* Identify core functionality needed to support multiple backends
* Move every core query layer function to a handle (as in handle pattern)
* Move every Ogmios query function that is not in the core set to a separate namespace (`Contract.Ogmios`)
* Implement stubs for Blockfrost functions in the "core" handle

Issues on the CTL repo were added to organize development here, and an initial issue was assigned.

That said, the main focus since project initialization has revolved around the broader architecture of the CTL project and untying it from a particular query layer. Specifically, some broad changes are needed before we can begin supplementing our reliance on Ogmios, the only chain indexer supported up until this point. Work along these lines included:
* Extending the TxConstraints API to support staking operations (stake credential registration, pool registration, etc)
* Extending CTL types to optionally accept staking credentials
* Add constraints that apply these changes to transactions
* Update the Contract interface to support these changes as well as inline datums.

And similar issues are highlighted throughout the CTL repo.

### October 2022

Fund9 vote results were announced in late September and our CTL Blockfrost Backend proposal was successfully supported by Catalyst voters. We have established a team to work on the project and our currently awaiting the first batch of Fund9 payments before beginning work.

## Further Information

CTL Repo: https://github.com/Plutonomicon/cardano-transaction-lib

MLabs Website: https://mlabs.city

MLabs Twitter: https://twitter.com/MLabs10

MLabs Contact: info@mlabs.city
