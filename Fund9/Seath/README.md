# Seath 

Protocols ("DApps") that build on top of Cardano can be viewed as distributed state machines that store their state in many UTXOs. A transaction is then a state transition on a subset of that state, i.e. UTXOs.

A problem that most protocols encounter is that many users often need to use the same UTXOs. When multiple parties attempt to act on the same state, there is a concurrency problem. The concrete issue is that since Cardano is deterministic, a transaction references the input state via the transaction that produced it. This means that of the multiple transactions that act on the same input state, only one can be accepted. The rest will be discarded since the transaction inputs no longer exist (as they've been consumed).

[Seath](https://cardano.ideascale.com/c/idea/422388) proposes improvements to this situation by effectively leveraging an Ouroboros-like solution -- "Ouroboros on Ouroboros." In short, this entails using VRFs, a slot-based ordering system (e.g., distinct from onchain slots), and offchain components (likely Haskell) streamlined alongside onchain counterparts (likely Plutarch). Our approach will fully account for security issues including MEV vectors while amalgamating users' transactions (e.g. state changes) against the Cardano ledger.

Project ID: [900152](https://docs.google.com/spreadsheets/d/1bfnWFa94Y7Zj0G7dtpo9W1nAYGovJbswipxiHT4UE3g/edit#gid=917336114)

## Current Status

Bootstrapping.

## Progress Report

### December 2022

Progress with the Seath project (a.k.a Cardano Throughput Solution) has been swift, and we are excited to report that we have met our first major Proof of Achievement as outlined in the Statement of Milestones form.

In concrete terms, this involves a detailed markdown document describing the design of the protocol. Briefly, Seath:

* describes a deterministic ordering of a live queue of transactions
* leverages UTXO determinism to ensure integrity
* aligns the incentives of transacting parties
* defines a leader-electing mechanism, a crucial component of the protocol
* outlines how to take advantage of Cardano's state machine structure

The document is available [here](https://github.com/mlabs-haskell/seath), and we will further submit a video to this effect to the Developer Ecosystem challenge team for review.

### November 2022

Organization for the Cardano-throughput-solution began in earnest this month. The statement of milestones was finalized, submitted, and approved by the challenge team and IOG. Moreover, the project was earlier renamed Seath, a more appealing and less obvious name than before.

Ramping up production, team members with backgrounds in cryptography were chosen to participate. Furthermore, as outlined in our Statement of Milestones, we began to research the specifics of the protocol design, particularly the slot leader specification. 

### October 2022

Fund9 vote results were announced in late September and our Cardano Throughput Solution proposal was successfully supported by Catalyst voters. We renamed the project to "Seath" -- it's snappier sounding, after all. Because the Seath proposal was awarded over $75,000, we must submit and receive approval for a SoM. We submitted our SoM and are currently awaiting confirmation from the Challenge and IOG teams.

## Further Information

MLabs Website: https://mlabs.city

MLabs Twitter: https://twitter.com/MLabs10

MLabs Contact: info@mlabs.city
