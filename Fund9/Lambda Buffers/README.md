# Lambda Buffers

There are no language-agnostic mechanisms for specifying the types of information and values used in Cardano DApps, a detrimental fact to productivity and cross-language environment interoperability. A significant percentage of DApp development effort is spent on dealing with serialization/deserialization issues between on-chain code types, off-chain/frontend, and analytics/databases. This major source of delay in project timelines could be eliminated if types would be language agnostically defined once per DApp; with serialization/deserialization code for multiple targets generated automatically from the agnostic definition.

To make Cardano DApps available across all the aforementioned platforms, structured information needs to be effectively shared in a language-agnostic manner and made available to different language/PAB environments.

Lambda Buffers (formerly [DApp Schemas](https://cardano.ideascale.com/c/idea/421376)) is a configuration language for specifying DApp schemas. The language makes use of code-generation tooling, which using the schemas produces ‘type libraries’ (aka. typelibs) for different language/PAB environments. Each typelib is generated alongside supporting libraries for handling encoding, serialization, and other essential operations. Overall, Lambda Buffers will serve as a language-neutral, extensible mechanism for specifying type definitions and code-generating different language environments.

Project ID: [900152](https://docs.google.com/spreadsheets/d/1bfnWFa94Y7Zj0G7dtpo9W1nAYGovJbswipxiHT4UE3g/edit#gid=917336114)

## Proposal Roadmap

Roadmap revisited and will be posted here following approval.

## Progress Report

### February 2023

Progress was brisk last month on the Lambda Buffers (formerly dApp Schemas) project.

Reworking the Compiler to include well-defined and precise error messages at the API level:
https://github.com/mlabs-haskell/lambda-buffers/pull/48
https://github.com/mlabs-haskell/lambda-buffers/pull/47
https://github.com/mlabs-haskell/lambda-buffers/pull/39

As well as its frontend integration that gives a CLI to interact with the system:
https://github.com/mlabs-haskell/lambda-buffers/pull/35
Kind checking is made available via the CLI tools (lbf and lbc):
https://github.com/mlabs-haskell/lambda-buffers/pull/32

Team members also focused on refining the internal representation of the Proto APPI types to make it more convenient to work with:
https://github.com/mlabs-haskell/lambda-buffers/pull/23
https://github.com/mlabs-haskell/lambda-buffers/pull/26

Compiler checks for Typeclasses and instance clauses:
https://github.com/mlabs-haskell/lambda-buffers/pull/29
https://github.com/mlabs-haskell/lambda-buffers/pull/44

### January 2023

Much progress was made over the last month, and development to date has been brisk. Most recently, progress focused on the compiler design/specs, the Frontend CLI, and documentation.
* Frontend https://github.com/mlabs-haskell/lambda-buffers/pull/11
* Kind checker - initial proposal https://github.com/mlabs-haskell/lambda-buffers/pull/10
* Update Compiler documentation https://github.com/mlabs-haskell/lambda-buffers/pull/13

Research needed to explore the implementation space was done in
* Typeclass Constraint Solver - https://github.com/mlabs-haskell/lambda-buffers/pull/9
* Codegen Patterns experiments - https://github.com/mlabs-haskell/lambda-buffers/pull/8
* Experimental directory and Prolog checker - https://github.com/mlabs-haskell/lambda-buffers/pull/3
* Kind checking a-la Vlad using unification-fd library - https://github.com/mlabs-haskell/lambda-buffers/pull/9

At the moment the report has a MVP of the LambdaBuffers Frontend component in https://github.com/mlabs-haskell/lambda-buffers/tree/main/lambda-buffers-frontend. The component is able to parse text documents with .lbf extension specifying LambdaBuffers schemas, report on any relevant errors, mostly in terms of module resolution and format the document which is necessary for both testing and code quality. The component is tested and export a lambda-buffers-frontend-cli command line tool that supports above mentioned features.

The LambdaBuffers Compiler in https://github.com/mlabs-haskell/lambda-buffers/tree/main/lambda-buffers-compiler currently implements the so called 'kind checking and inference' which ensures that the type definitions provided by the Frontend are indeed valid and is able to annotate each type term/expression with appropriate kind signatures. This is essential work that happens before type class checking and Codegen. A big milestone was achieved as the Compiler is now able to operate on the https://github.com/mlabs-haskell/lambda-buffers/blob/main/lambda-buffers-proto/compiler.proto API specification itself.

We did a deep dive into Codegen as well, implemented a user-friendly framework with the aim of facilitating low-overhead, robust yet flexible implementation of Codegen modules. The underlying idea is that Codegen modules provide 'rule patterns' they support and know how to generate code from. This both enables gradually building such modules and having an API based structured 'capability reporting'. This effort also informed greatly on the process of type class checking which will be implemented as part of the Compiler component. This work is still experimental, but soon to be merged in the repo.

### December 2022

As covered in our internal design documents, decentralized applications tend to require the same types to be defined and synchronized across various parts of their architecture (on-chain, off-chain, frontend, analytics, etc.), each of which may be implemented in different languages. The Lambda Buffers project seeks to provide users with a way to define their applications’ types in an ergonomic frontend language, and then automatically generate corresponding type definitions in a wide range of target languages. 

This month, many architectural decisions were pushed to the forefront of the Lambda Buffers project. The focus largely revolved around cementing a structure for the intermediate language that will ultimately oversee the codegen of the library. Care was taken to ensure types can be reliably represented in the target language while ensuring that complexity does not expand uncontrollably.

More specifically, team members: 

* Decided against relying on ProtBufs
* Clarified the type formats the project would rely on and whether or not to incorporate recursive types
* Hashed out a rough representation of type schemata

Initial PRs involving constraint solvers, specification documents, and were also submitted.

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
