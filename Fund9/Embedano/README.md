# Embedano

Cardano has emerged as a secure, decentralized, and scalable root-of-trust for decentralized applications of all shapes and sizes. Therefore, it's hardly surprising  that there’s a lot of demand to run Cardano everywhere. For example, projects like Adosia and Veritree already aggregate data to be published on-chain by using embedded/IoT systems. Use cases such as these are subject to resource constraints like network bandwidth, and there are sure to be even more projects as the community continues to develop. Embedano addresses some challenges to using blockchain tech in these resource-constrained settings.

Specifically, [Embedano](https://cardano.ideascale.com/c/idea/414017) looks to develop an SDK for embedded devices that cover a range of use cases. Similar initiatives -- e.g., Trezor and Ledger -- leave something to be desired in their approached to open source security. Notably,  closed-source code or firmware written in C and Python, neither of which are ideal for hardware wallets.

Embedano looks to deliver Cardano-specific software useful in hardware wallets and products beyond that scope. We expect a majority of this task will involve streaming transactions so constrained embedded devices can offer secure signing capabilities. In turn, embedded devices will be able to sign UTxOs for several applications including sign-in verification (think sites with Google-like single sign-ons except with the Cardadno blockchain), identity verification via Atala Prism, and more.

Project ID: Project ID: [900156](https://docs.google.com/spreadsheets/d/1bfnWFa94Y7Zj0G7dtpo9W1nAYGovJbswipxiHT4UE3g/edit#gid=917336114)

## Current Status

Bootstrapping.

## Progress Report

### January 2023

Embedano

Since our last monthly report, the Embedano core project was established and work has begun toward its initial implementation. More specifically, 

* [a nix dev setup was established](https://github.com/mlabs-haskell/embedano/commit/a4a78ba2470a7d4060de13ae99de384b3dec46eb)
* a QEMU sandbox established
https://github.com/mlabs-haskell/embedano/commit/9283ebe04e438bcc016716370b29fe27acb763b1
* early integration of core utils and serialization functions
https://github.com/mlabs-haskell/embedano/commit/d9a311008831d0470ce79ae8eee1d788d04c331c
* a basic CI established
https://github.com/mlabs-haskell/embedano/commit/3d1e2e272345d7ee472c76d5bd3511124e36ba24
* early drafting of the SDK-API
https://github.com/mlabs-haskell/embedano/commit/159a0b3ba874af7fa5e56564c752f3988b8844f5

Essentially our focus was on building out the fundamental building blocks of the Embedano project, and we will improve upon them in the months ahead.

### December 2022

Embedano work this month continued threads from last month. This included:

* Research solidifying into reliable design decisions
* Summarizing the details of how similar solutions have developed - particularly efforts by Trezor and Vacuumlabs
* Settling on interview questiosn for surveying wallet providers and DApp projects per our SoM document (These also took into consideration implications stemming from CIP-21)

More specifically, team members settled on the core functionality of the Rust SDK. Including:

* Generation, storing and resetting of seed phrase
* Key derivation
* Public payment key queries
* Public staking key queries
* Cardano address queries
* Cardano transaction signing
* Signing of arbitrary data
* Proof of ownership for public keys or addresses
* Seed phrase queries
* Setting seed phrases (for recovery)

As well as some minor additional functionality.

That said, these updates were covered in more detail in our initial [design document](https://github.com/mlabs-haskell/embedano/blob/ba0f1e01e796c0dceb3559a1c227438d1acf3544/design-doc.md#introduction) released this month.

### November 2022

Work on the Embedano project up until this point consisted of organization, documentation, and initial research. A team leader and team members were assigned. After initial funding was received, regular sprints were established, and early meetings were used to introduce devs to the project and accomplish onboarding orientation - the aim of the project, etc.

More tangibly, a repo and internal wiki were initialized and populated with the early research/resources of the project: e.g., API and capabilities research, comparison to existing libraries, an outline of the goals of the SDK, and so on. Trezor was identified as a good comparison project due to its streaming transaction feature and open-source structure. Most important, however, the team specified the Embedano project would provide a wallet SDK that is minimally compliant with CIP-21 and compatible with the ARM Cortex-M series of processors.

### October 2022

Fund9 vote results were announced in late September and our Embedano proposal was successfully supported by Catalyst voters. Because the Embedano proposal received over $75,000, we must submit and receive approval for an SoM. We submitted our SoM and are currently awaiting confirmation from the Challenge and IOG teams.

## Further Information

MLabs Website: https://mlabs.city

MLabs Twitter: https://twitter.com/MLabs10

MLabs Contact: info@mlabs.city
