# Plutus Specification Langauge 
The [Plutus Specification Language (PSL)](https://cardano.ideascale.com/c/idea/396541) is an embedded DSL for formally 
describing a dApp's behavior from an inter-transaction perspective (i.e., across dApp actions and interactions). In short, the PSL is used to circumscribes transaction types ([transaction families](https://github.com/mlabs-haskell/plutus-specification-language/blob/mario/families/families/TransactionFamily.md)) and define how, and under what conditions, value flows throughout an application. Developers can then use a dApp specification to test whether an implementation functions as designed.

Project ID: [800256](https://docs.google.com/spreadsheets/u/0/d/1bfnWFa94Y7Zj0G7dtpo9W1nAYGovJbswipxiHT4UE3g/htmlview#)

GitHub Repo: https://github.com/mlabs-haskell/plutus-specification-language


## Proposal Roadmap

3 Months: 
- Finish the initial exploratory phase of development 
- Realize a functional specification language usable by advanced users
- Backtest working dApps to further guide design

6 Months: 
- Checking against production EUTXO scripts 
- Expanding the number of use cases covered 
- Several early-stage dApps designing with and incorporating our product throughout their development process

12 Months: 
- Fully-functional, audited, and flexible DSL suitable for specifying any project type 
- Attention turned to addressing "edge-cases" 
- Broadening the range of supported dApp design types


## Current Status

The PSL is in an early prototype state, and a video demo should be posted soon.

Type-level transaction specifcation established 

Above supports automatic generation of transaction diagrams. Automated test generation coming soon.



## Progress Report

### August 2022

Recently, transaction families have been defined, and their typing established. This is particularly exciting as the feature was described in the original concept of the project. The accomplishment also ushers in early functionality. With transaction families typed, automated transaction diagramming is now within reach, and automated test generation will soon follow.

In the meantime, some ergonomic improvements are required. Currently, team members are making progress with Pretty Printing and the necessary data types, and further Plutarch integration will see the PSL become even more useful. For example, the PSL may soon be able to support automatically deriving a rough smart contract script from a dApp specification.

### July 2022

Cardano was designed with functional programming and high-assurance code at heart. 
Yet, formal methods tools remain sparse despite the arrival of smart contracts. 
In lieu of this, MLabs began exploring formally verifying Plutus in October 2021. 
When Fund8 began, we had a basic outline of a dependently-typed eDSL and its 
operational semantics, particularly a general framing of transaction families 
and their applications.

Because of this initial work, we were able work example specs fairly soon after receiving funding. It became clear the structures PSL and Plutarch overlapped significantly, so they were integrated to a minor degree. Specifically, Plutarch was leveraged on the backend to output a reference implementation of a given spec. Optics support was added, and the PSL started being used in a limited way with client projects.


## Demo Overview

Video demo coming soon.


## Further Information

PSL GitHub Repo: https://github.com/mlabs-haskell/plutus-specification-language

PSL Transaction Families ReadMe: https://github.com/mlabs-haskell/plutus-specification-language/blob/mario/families/families/TransactionFamily.md

MLabs Website: https://mlabs.city

MLabs Twitter: https://twitter.com/MLabs10

MLabs Contact: info@mlabs.city
