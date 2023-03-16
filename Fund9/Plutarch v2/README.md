# Plutarch v2

Cardano features powerful smart contracts. However, the limits of smart contracts are very tight. Transactions must at most be 16 KiB, which limits the size of scripts heavily such that the computational work possible is also strictly limited. These constraints are here for a good reason, and raising them isn’t a viable long-term solution. Unfortunately, however, Plutus Tx (the tool to compile Haskell to Plutus) struggles to help developers meet these constraints.

Plutarch is a typed eDSL in Haskell for writing efficient Plutus Core validators. The v1.0 introduced several optimizations into the development process by offering developers fine-grained control of the Plutus Core they generate. In fact, a ~75% decrease in CPU, memory, and script size is commonly achievable without giving up valuable type information.

Essentially, Plutarch allows Plutus developers to leverage the beneficial features of Haskell without losing the ability to compile. Plutarch achieves this sleight-of-hand by wrapping data structures in a computational context that mimics mutable state. This allows for type-level operations to occur without manipulating UPLC. Our [v2 proposal](https://cardano.ideascale.com/c/idea/414065) looks to expand the feature set of the Plutarch project, increase the number of compilation backends, and all-around make the tool more ergonomic and easy to use.

Project ID: [900157](https://docs.google.com/spreadsheets/d/1bfnWFa94Y7Zj0G7dtpo9W1nAYGovJbswipxiHT4UE3g/edit#gid=917336114)

## Current Status

Bootstrapping. 

## Progress Reports

### March 2023 

Added new experiments and a final (7th) experiment.

Plutarch2New5 utilises a Coyoneda-like trick to tell what the term is supposed to contain through the index of the GADT.
    
Plutarch2New6 reverts to including the children in the node again yet allows partial interpretation by including the yet-to-be-applied interpretations in the term, thus essentially delaying their application until we have more information.
    
Plutarch2New7 adds the missing feature of interpreting _multiple_ languages at once to the trick used in Plutarch2New6.

This final version should be able to encompass all envisioned use cases, e.g.:
- HOAS
- Partial interpretation
- Variables in languages
- Sharing work on top-level definitions
- Indexed languages
    
It seems to be very powerful, yet it isn't entirely trivial to manipulate due to the complexity of the types. Combinators and utility functions will be added.

https://github.com/Plutonomicon/plutarch-core/commit/4e0fe4d958416e4e8313bf8565e48413eed3b0b0

### February 2023

Plutarch 2 used to rely heavily on type classes, often using
quantified constraints. This design was inherently fickle, encountering
many GHC bugs, and was also restrictive in the way you interpreted it.

This is the same problem as with MTL vs. Free-monad based effect systems,
where you effectively need O(n^2) instances to have "monad transformers"
with type classes for them.

What did this mean for us? Monad transformers are partial interpreters,
the idea being you could build an interpreter from many small interpreters.
This would indeed be immensely useful, as writing an interpreter/backend before
was quite verbose, often needing much of the same logic implemented over and over again.
This is especially problematic once you get into backend-independent optimisations.

In the spirit of the Free monad revolution, Plutarch 2 now has a `Term` data type,
that is no longer opaque. It embeds the structure of the AST transparently, encoding
the languages it supports (i.e. the types of the nodes) in the type of `Term ls tag`.
It generalises the concept of expressions, no longer referring to expressions directly.
Whereas before we had `Term`, `IsPType`, `PIO`, all these have been generalised into
_tags_.

This data type is AFAICT novel, as it packs several (seemingly) new constructions.
It supports linearly bound variables, a feat which is harder than it sounds in Free-monad-land. The story for HOAS isn't quite fleshed out yet, but either (a variant of) HOAS is possible, and if not, a syntactic sugaring on top utilising HOAS is possible.

There is still much work to do, notably `interpret` isn't finished, and `interpretIn` should not
exist. `interpretIn` can likely be "delayed", or in some way pulled out of the language to
reduce the amount of boilerplate and increase the variety of interpretations possible.

One other core reason for the superiority of this design is its support for sharing work
done on top-level definitions of terms. Take the following:


f :: Term ...
f = ...

g :: Term ...
g x = f # x + f # x


`g` includes `f`'s AST twice. After all, it's a tree, not a graph, but no! Haskell in fact
represents this as a graph, as the two references to `f` refer to the same address in memory.
We can detect this using GHC.StableNames, thus reducing the work done when interpreting it.

This is why interpretations are modeled as folds. This is not possible with the previous type class-based design, as the top-level definitions were functions (in representation).

The current design out to be able to encompass all possible use cases, notably:
- Rewrite rules
- Effects
- Linearity
- Singletons
- Syntactic plugins/etc.
- Subinterpreting
- Embedding other languages
- Optics
- Ergonomic top-level definitions
- Trivial-to-make backends

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
