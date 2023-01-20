# Dev Documentation Drive

When building a dApp on the Cardano Network, there are several major hurdles to overcome, which are solved through strong documentation in other ecosystems. Very early questions such as 'What tools and libraries should I use to build a production-ready app?' are often tough to answer. This compounds knowledge among experienced developers and prevents new developers from learning the lessons of previous projects.

Our Dev Documentation Drive looks to address this issue. We seek to publish high-quality documentation to ease the learning curve and, overall, reduce development costs and the time needed to bootstrap products. [Dev Documentation Drive](https://cardano.ideascale.com/c/idea/420778) will incorporate tutorials, how-to guides, explanations, and reference material towards this end. They will be easily searchable/discoverable, written clearly, readable, reliable, and accurate.

Project ID: Project ID: [900155](https://docs.google.com/spreadsheets/d/1bfnWFa94Y7Zj0G7dtpo9W1nAYGovJbswipxiHT4UE3g/edit#gid=917336114)

## Current Status

Bootstrapping.

## Progress Report

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
