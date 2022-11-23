# Plutus Specification Langauge 
The [Plutus Specification Language (PSL)](https://cardano.ideascale.com/c/idea/396541) is an embedded DSL for formally 
describing a dApp's behavior from an inter-transaction perspective (i.e., spanning dApp actions across time). In short, the PSL is applied to circumscribe transaction types ([transaction families](https://github.com/mlabs-haskell/plutus-specification-language/blob/mario/families/families/TransactionFamily.md)) and define how, and under what conditions, value flows throughout an application. Developers can use a dApp specification to test whether an implementation functions as designed.

Project ID: [800256](https://docs.google.com/spreadsheets/u/0/d/1bfnWFa94Y7Zj0G7dtpo9W1nAYGovJbswipxiHT4UE3g/htmlview#)

GitHub Repo: https://github.com/mlabs-haskell/plutus-specification-language


## Proposal Roadmap

3 Months: 
- Finish the initial exploratory phase of development 
- Realize a functional specification language accessible to advanced users
- Backtest working dApps to refine design

6 Months: 
- Checking against production EUTXO scripts 
- Expanding the number of use cases covered 
- Several early-stage dApps designing with and incorporating our product throughout their development process

12 Months: 
- Fully-functional, audited, and flexible DSL suitable for specifying any project type 
- Attention turned to addressing "edge-cases" 
- Broadening the range of supported dApp design types


## Current Status

The PSL is in an early prototype state, and a video demo will be posted soon.

Type-level transaction specification completed. 

Initial DApp specced in large part using our eDSL. Currently, generalizing PSL's applicability and deliberating on a second DApp for speccing and PSL development.


## Progress Report

### November 2022

As mentioned in our August and July monthly updates, our Plutus Specification Language incorporates Plutarch and is increasingly integrating this eDSL's type scheme and codebase over time. Towards this end, a significant portion of PSL work involved updating Plutarch to reflect Plutus changes and to make the Nix build more reliable.

That said, other type adjustments were made to Plutarch that support use cases addressed by our Specification Language. For instance:
* fixing V1 script types being re-exported in the V2 API
* correcting the pif operator
* support for generating type class instances
* syntactical plugin to improve ergonomics

### October 2022

Work continued over the last month with generalizing the PSL. Towards this end, the formal methods team began work specifying a second DApp, Seabug. Seabug is an internal MLabs project that produces cNFT derivatives with enhanced ownership values. The derivative minting scheme of the protocol is somewhat complex, making it a good second use case for the PSL. Details can be found [here](https://drive.google.com/file/d/1F7a0lOWKJhEuYZxcK90qN2UN1rVePXRX/view).

The formal methods team was able to specify the complicated transactions of Seabug, providing a greater degree of confidence in the eDSL approach of the PSL and its usefulness for other Cardano DApps, especially when combined with other formal methods tools. Naturally, with transactions specified transaction diagrams were straightforward to generate - a major secondary use case of the project.

Finally, a number of maintenance commits occurred over the last month. These include fixing and updating library dependencies, updating tags, and so on. Some diagramming errors concerning edge-case were addressed and largely resolved.

### September 2022

PSL development last month focused on improving usability - particularly, fine-tuning the transaction diagram experience. Bugs in diagram generation were resolved, and formatting was improved. Transactions were also given the ability to provide greater detail (e.g., displaying lists of relevant UTxOs).

Along these lines, improvements were made to the documentation and the project's approachability. More specifically, the PSL repo was marginally reconfigured for ease of use and streamlining new project onboarding.

Of note, the PSL has been used to largely spec a client project with the intention of building out the language to cover the project in its entirety. With this underway, the PSL team is currently deliberating on integrating with a second project. Once decided, work with a second project will be used to generalize the PSL - a major goal outlined in the original Catalyst proposal.

### August 2022

Recently, transaction families have been defined, and their typing established. This is particularly exciting as this feature was described in the original project outline. This accomplishment also represents early functionality. With transaction families typed, automated transaction diagramming is possible. Alongside prettyprinting, specs will be human-readable and developers will be able to embed them into literate code documents. Automated test generation is now within reach and will be introduced soon.

In the meantime, some ergonomic improvements are needed. Currently, team members are making progress implementing prettyprinting and the necessary data types, and further Plutarch integration will see the PSL become more effective. For example, our PSL may soon be able to derive an unrefined smart contract script from a protocol design. These features seriously improve the developer experience on Cardano.

### July 2022

Cardano was designed with functional programming and high-assurance code at heart. 
Yet, formal method tooling remains sparse despite the arrival of smart contracts. 
MLabs began exploring the formal verification of Plutus applications in October 2021. 
When Fund8 began, we had a basic outline of a dependently-typed spec eDSL and its 
operational semantics, particularly a general framing of transaction families 
and their applications.

Thanks to this groundwork, the PSL progressed quickly, and we began working with example specs soon after receiving funding. We soon realized that the structures of the PSL and [Plutarch](https://github.com/Plutonomicon/plutarch-plutus) overlapped significantly, and we integrated Plutarch to a degree. Specifically, Plutarch was leveraged on the backend to output a reference implementation of a given spec. Optics support was added, and the PSL started seeing limited use on client projects.


## Demo Overview

Video demo coming soon.


## Further Information

PSL GitHub Repo: https://github.com/mlabs-haskell/plutus-specification-language

PSL Transaction Families ReadMe: https://github.com/mlabs-haskell/plutus-specification-language/blob/mario/families/families/TransactionFamily.md

MLabs Website: https://mlabs.city

MLabs Twitter: https://twitter.com/MLabs10

MLabs Contact: info@mlabs.city
