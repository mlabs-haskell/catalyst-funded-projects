# Plutarch v2

Cardano features powerful smart contracts. However, the limits of smart contracts are very tight. Transactions must at most be 16 KiB, which limits the size of scripts heavily such that the computational work possible is also strictly limited. These constraints are here for a good reason, and raising them isn’t a viable long-term solution. Unfortunately, however, Plutus Tx (the tool to compile Haskell to Plutus) struggles to help developers meet these constraints.

Plutarch is a typed eDSL in Haskell for writing efficient Plutus Core validators. The v1.0 introduced several optimizations into the development process by offering developers fine-grained control of the Plutus Core they generate. In fact, a ~75% decrease in CPU, memory, and script size is commonly achievable without giving up valuable type information.

Essentially, Plutarch allows Plutus developers to leverage the beneficial features of Haskell without losing the ability to compile. Plutarch achieves this sleight-of-hand by wrapping data structures in a computational context that mimics mutable state. This allows for type-level operations to occur without manipulating UPLC. Our [v2 proposal](https://cardano.ideascale.com/c/idea/414065) looks to expand the feature set of the Plutarch project, increase the number of compilation backends, and all-around make the tool more ergonomic and easy to use.

Project ID: [900157](https://docs.google.com/spreadsheets/d/1bfnWFa94Y7Zj0G7dtpo9W1nAYGovJbswipxiHT4UE3g/edit#gid=917336114)

## Current Status

Bootstrapping. 

## Progress Report

### January 2023

Plutarch v2 

Work towards Plutarch v2 focused heavily on several key areas:

Backend generalization and ergonomics (e.g. primitive types, coercions, and helper function robustness):
https://github.com/Plutonomicon/plutarch-core/commit/b9d3a1e22ed18bc01eda1993e4ce499c6ca63342
https://github.com/Plutonomicon/plutarch-core/commit/ff28aef59dab202993142a42f8015e6c41cb7ab9

As well as, cleanups and efficiency improvements. In particular, fixing the dichotomy in handling of PType and `a PHsEf` which was was much more essential than initially assumed (notably blocking on whether something was PType or `a PHsEf` or not would have downstream consequences that would	result in incomprehensible errors).
https://github.com/Plutonomicon/plutarch-core/commit/c474e50ffedec34ce97a34d48811bc5552f5d620

Reformatting
https://github.com/Plutonomicon/plutarch-core/commit/6bf1d0c56b0fb0b73b78f0377b501fe7fd9cff89

And other major additions to the Core library, Data types, and so on
https://github.com/Plutonomicon/plutarch-core/commit/b9d3a1e22ed18bc01eda1993e4ce499c6ca63342

### December 2022

This month, Plutarch v2 development milestones include:

* Updating Plutarch Nix
* Nix backend output 
* Consideration given to overloading the lambda expression
* Work towards removing `pletFields`

`pletFields` return bound field types, effectively a heterogenous Haskell list where only the used bindings are extracted and  "paid for" in terms of computing resources. Considering the Plutarch learning curve, they have been burdensome and their use is not particularly idiomatic.

Perhaps a more pressing update involves backend output, namely nix language output. This addresses one of the main use cases for Plutarch, ergonomics and auditing. Our Fund9 proposal focused on adding functionality relevant to auditors and other ecosystem participants, and this is a major step in that direction.

Finally, a modest update involves Liqwid, a partner who helped launch the Plutarch project. An issue was merged that made a type export more versatile and easier to incorporate into their project.

### November 2022

Plutarch v2.0 was ramped-up since receiving funding early this month. However, prior to that a final release of Plutarch v1 was merged. This release reflected recent changes to Plutus and fixed several code-quality issues as well as improving ergonomics. Also:
* updating the nix build centered upon our mlabs-tooling.nix flake
* benchmarking improvemetns
* minor tweaks to basic Plutarch data types

On the v2.0 front, work began on expanding Plutarch backend support. Compiling to Nix was an easy first step owing to the decent REPL. A bit more work here will lead to the first major updates before moving on to supporting other backends. 

### October 2022

Fund9 vote results were announced in late September and our Plutarch v2 proposal was successfully supported by Catalyst voters. We have established a team to work on the project and are currently awaiting the first batch of Fund9 payments before beginning work.

## Further Information

Plutarch Repo: https://github.com/Plutonomicon/plutarch-plutus

MLabs Website: https://mlabs.city

MLabs Twitter: https://twitter.com/MLabs10

MLabs Contact: info@mlabs.city
