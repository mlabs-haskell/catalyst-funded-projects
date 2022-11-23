# Lambda Buffers

There are no language-agnostic mechanisms for specifying the types of information and values used in Cardano DApps, a detrimental fact to productivity and cross-language environment interoperability. A significant percentage of DApp development effort is spent on dealing with serialization/deserialization issues between on-chain code types, off-chain/frontend, and analytics/databases. This major source of delay in project timelines could be eliminated if types would be language agnostically defined once per DApp; with serialization/deserialization code for multiple targets generated automatically from the agnostic definition.

To make Cardano DApps available across all the aforementioned platforms, structured information needs to be effectively shared in a language-agnostic manner and made available to different language/PAB environments.

Lambda Buffers (formerly [DApp Schemas](https://cardano.ideascale.com/c/idea/421376)) is a configuration language for specifying DApp schemas. The language makes use of code-generation tooling, which using the schemas produces ‘type libraries’ (aka. typelibs) for different language/PAB environments. Each typelib is generated alongside supporting libraries for handling encoding, serialization, and other essential operations. Overall, Lambda Buffers will serve as a language-neutral, extensible mechanism for specifying type definitions and code-generating different language environments.

Project ID: [900152](https://docs.google.com/spreadsheets/d/1bfnWFa94Y7Zj0G7dtpo9W1nAYGovJbswipxiHT4UE3g/edit#gid=917336114)

## Proposal Roadmap

Roadmap revisited and will be posted here following approval.

## Current Status

Bootstrapping.

## Progress Report

### November 2022

Lambda Buffers (name changed) was begun this month and the initial design stage is largely underway. Considering it's still early, the majority of the work has focused on background research. Specifically, several comparable projects were investigated and are under consideration for use in the frontend:
* Dhall
* Protobufs with Text Format
* JSON with JSON schemas

Moreover, general design documents have also been developed internally and a PoC is underway (also internally). This design document focused on many things including generalizing Oracel/DApp data and the compilation chain of the project. The heft, however, revolves around frontend and API considerations.

### October 2022

Fund9 vote results were announced in late September and our Cardano DApp Schemas proposal was successfully supported by Catalyst voters. We renamed the project to "Lambda Buffers" finding it a more representative name. Because the Lambda Buffers proposal was awarded over $75,000, we must submit and receive approval for an SoM. We submitted our SoM and are currently awaiting confirmation from the Challenge and IOG teams.

## Further Information

MLabs Website: https://mlabs.city

MLabs Twitter: https://twitter.com/MLabs10

MLabs Contact: info@mlabs.city
