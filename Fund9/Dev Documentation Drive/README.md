# Dev Documentation Drive

When building a dApp on the Cardano Network, there are several major hurdles to overcome, which are solved through strong documentation in other ecosystems. Very early questions such as 'What tools and libraries should I use to build a production-ready app?' are often tough to answer. This compounds knowledge among experienced developers and prevents new developers from learning the lessons of previous projects.

Our Dev Documentation Drive looks to address this issue. We seek to publish high-quality documentation to ease the learning curve and, overall, reduce development costs and the time needed to bootstrap products. [Dev Documentation Drive](https://cardano.ideascale.com/c/idea/420778) will incorporate tutorials, how-to guides, explanations, and reference material towards this end. They will be easily searchable/discoverable, written clearly, readable, reliable, and accurate.

Project ID: Project ID: [900155](https://docs.google.com/spreadsheets/d/1bfnWFa94Y7Zj0G7dtpo9W1nAYGovJbswipxiHT4UE3g/edit#gid=917336114)

## Progress Reports

### June 2023

We finished work on the developer documentation drive and wrapped up this project. Our closeout report is available [here](https://youtu.be/ZMq5D6y6t1w).

### May 2023

Work over the last month of the docdrive project focused on documenting Plutip, an internal testing tool that relies on generating local clusters. Plutip is one of the key software projects we wished to cover and are happy to approach it.

More specifically, we updated and improved the docs and some misc files of plutip-core
https://github.com/mlabs-haskell/plutip/pull/177

Team members also documented cli options as well as made progress towards an in-depth plutip overview:
https://github.com/mlabs-haskell/plutip/pull/178 
https://github.com/mlabs-haskell/plutip/pull/179

Finally, CTL integration is a major application of the Plutip project and will be incorporated into docdrive. Initial documentation began there as well:
https://github.com/Plutonomicon/cardano-transaction-lib/pull/1494

### April 2023

Efforts towards a broad scope of documentation efforts continued over the last month.

Specifically, team members worked to clarify and improve the documentation for Oura, specifically for filters and events:
https://github.com/txpipe/oura/pull/553

As well as for the Scrolls project:
https://github.com/txpipe/scrolls/pull/140

Moreover, work continued toward covering various bits relevant to the Cardano Ledger, cardano-cli, cardano-api, etc:
https://github.com/pb99u069/pb99u069.github.io/commit/2a0ecb42b1d07528dd81c8b75469df695604c012
https://github.com/pb99u069/pb99u069.github.io/commit/b9610db0cfb8fd54fc857e3c98befe3b61aa120e

### March 2023

Progress on the Dev Documentation Drive occurred on several fronts over the last month. Firstly, Plutarch documentation was updated, including several editorial/clerical fixes:

https://github.com/Plutonomicon/plutarch-plutus/pull/598

Moreover, we are happy to announce a polished version is now hosted via GitHub pages/Emanote, creating searchable and discoverable documentation - the main output of our proposal.

https://plutonomicon.github.io/plutarch-plutus/

Similarly, efforts also focused on clarifying cardano-api and its relationship to cardano-cli and cardano-node. An early version of this is available here:

https://pb99u069.github.io/

Finally, we contributed to filling out the Oura documentation, and our effort can be viewed here:

https://github.com/txpipe/oura/pull/553/files

### February 2023

This month, team members made progress toward documenting the cardano-api, a major topic highlighted in our original proposal. 

While there was a fair amount of information, internal and external, to draw from, it was somewhat challenging to identify/develop generic use cases to highigh as examples. Of course, workable examples are an objective of the project and a key aspect of affective documentation. 

That said, progress this month speficially covered:

* Submitting txs to a Hydra head
* Minting txs
* Paying to a script validator
* Building a simple tx
* Building a script witness
* Withdrawing from a staking address

Note that we posted our work [here](https://github.com/pb99u069/cardano-api-documentation) as a temporary fix for meeting progress requirements. Hosting will likely be updated in the near future.

### January 2023

Progress on the dev documentation drive continued to focus on Plutarch documentation. More specifically, work was done towards establishing hosting/site generation for the documentation:
https://github.com/Plutonomicon/plutarch-plutus/commit/22e9b98b5646f7a59d4d322467b86461c74291c4

Issues with links were addressed
https://github.com/Plutonomicon/plutarch-plutus/commit/985ec6e717dffc67f0bac2136b82f2151a4f0b08

Content was added and edited
https://github.com/Plutonomicon/plutarch-plutus/commit/eb1f957cfc88b90db4aac27e1f8ae1ac0c51d804

And Hercules CI was integrated into the document build, and we tested whether effects were properly picked up.

https://github.com/Plutonomicon/plutarch-plutus/commit/6c36f618e0215ff4ba34383491de9c589b73a107#diff-206b9ce276ab5971a2489d75eb1b12999d4bf3843b7988cbe8d687cfde61dea0

Finally, additional technical writers were onboarded near the end of the reporting period in order to expedite further development.

### December 2022

Documentation work ramped up this month in earnest. Plutarch is likely the most used/referenced tool that MLabs is associated with, so our efforts in December focused here. More specifically we:
* updated and expanded existing Plutrach documentation to reflect recent upgrades
* added explanations to type definitions and design decisions surrounding them
* outlined how newer Plutarch terms can be used
* explained various internal mechanics
* made existing tutorials compatible with CI

We also identified areas in which the current Plutarch documentation is lacking. Namely, this includes in-depth tutorials. Currently, only basic examples are considered in the repo, which implies obvious shortcomings especially as Plutarch is updated to v2. 

Here, we deliberated on which topic to focus on, opting for something higher-level than previously shown - validators, minting policies, etc. Finally, work was assigned and has begun here.

### November 2022

MLabs began work on the Developer documentation drive this month. This involved a fair amount of management and preparatory groundwork. More specifically, we assigned an initial developer/technical writer and began surveying clients and community members -- as well as internally -- about topics and tools they feel are under documented. 

We also deliberated about how best to host the material and implemented a test blog page in case we decided to host the content on our newly redesigned website. This is an appealing choice in light of recommendations from an SEO specialist we consulted. That said, we hope to begin publishing content soon.

### October 2022

Fund9 vote results were announced in late September and our Dev Documentation Drive proposal was successfully supported by Catalyst voters. We have established a team to work on the project and are currently awaiting the first batch of Fund9 payments before beginning work.

## Further Information

MLabs Website: https://mlabs.city

MLabs Twitter: https://twitter.com/MLabs10

MLabs Contact: info@mlabs.city
