# Proposed projects

Project ideas proposed by client teams and mentors. These are projects that fit the EPF scope and would be the most valuable to the team.

If you are interested in the project, take your time to learn about it, the team it's coming from and related area of the protocol. Reach out to client organizers if you have any questions or need connection to a mentor.

## Previous cohorts

In project ideas from previous cohorts, you might find some up-to-date ideas which haven't been solved yet.

- [Project ideas in the sixth cohort](https://github.com/eth-protocol-fellows/cohort-six/blob/master/projects/project-ideas.md), [Projects executed](https://github.com/eth-protocol-fellows/cohort-six/blob/master/projects/)
- [Project ideas in the fifth cohort](https://github.com/eth-protocol-fellows/cohort-five/blob/master/projects/project-ideas.md), [Projects executed](https://github.com/eth-protocol-fellows/cohort-five/blob/master/projects/)
- [Project ideas in the fourth cohort](https://github.com/eth-protocol-fellows/cohort-four/blob/master/projects/project-ideas.md), [Projects executed](https://github.com/eth-protocol-fellows/cohort-four/blob/master/projects/)
- [Project ideas in the third cohort](https://github.com/eth-protocol-fellows/cohort-three/blob/master/projects/project-ideas.md), [Projects executed](https://github.com/eth-protocol-fellows/cohort-three/blob/master/projects/)
- [Project ideas in the second cohort](https://github.com/ethereum-cdap/cohort-zero/issues?q=is%3Aopen+is%3Aissue+label%3A%22help+wanted%22)
- [Project ideas in the first cohort](https://github.com/ethereum-cdap/cohort-one/issues?q=is%3Aissue+Project+idea)

## Ongoing wishlists

These are collections of projects proposed by some teams and might not be fully updated.

### Protocol Security tooling wishlist

By Fredrik

Ongoing wishlist of ideas for tools that will help with securing the protocol.

https://security.ethereum.org/wishlist

### PandaOps tooling wishlist

By Pari

Ongoing wishlist of ideas for tools that help with development and testing of the protocol.

https://github.com/ethpandaops/tooling-wishlist

### RIG Opened Problems

By Barnabé Monnot

Explore Robus Incentives Group Opened Problems. Most relevant for EPF are tagged https://efdn.notion.site/ROPs-RIG-Open-Problems-c11382c213f949a4b89927ef4e962adf

## Proposed by client teams

Client teams will submit cohort 7 project ideas via pull request to this document. If you represent a client or research team and want to propose a project, open a PR adding a section here or reach out to the cohort organizers on Discord.

### Erigon: aglean — Lean client permutations and stability

By Giulio Rebuffo / Erigon

[aglean](https://github.com/erigontech/aglean) is a Python Lean Ethereum consensus client together with an AI-driven cross-language generation framework. Today the repository already has a working Python implementation, fixture verification, and a live local-devnet sync path. The next step is to develop it further into a stronger EPF project by adding actual implementation permutations and improving overall stability.

This project is about turning aglean from a one-shot client-porting demo into a more serious client-diversity engine. In particular, the work could include:

- defining real interchangeable subspec permutations instead of a single baseline implementation,
- improving stability and reproducibility of generated clients and verification runs,
- strengthening fixture and devnet-based test harnesses for correctness and interoperability,
- and making it easier to try architectural alternatives without rewriting the entire client.

Examples of such alternatives include different storage backends, sync strategies, and other subsystem-level design choices that can expand the permutation space while keeping the same protocol behavior.

This project is a good fit for fellows interested in Lean Ethereum, client diversity, testing infrastructure, and AI-assisted client implementation.

### Ream: Black Box Interop Testing Post Quantum Lean Ethereum

By Kolby ML and Derek Sorken

The Ream team maintains the shared testing infrastructure for the post quantum movement for Ethereum (lean consensus) at https://hive.leanroadmap.org/, a black box testing framework that tests post quantum clients against a common suite of scenarios.

The project would be fully in Rust 🦀 and can be found on https://github.com/ethereum/hive.

Every lean consensus client shipping runs through this testing framework, which means the work you do on this project directly impacts the lean ecosystem as it allows the post quantum effort to confidently scale devnets to larger validator sets and how quick teams can ship devnets against an evolving Post Quantum Ethereum spec (https://github.com/leanEthereum/leanSpec).

This project would extend the testing infrastructure: adding new scenarios (spec tests, checkpoint tests, signature aggregation interop, state transition cross-checks, key lifecycle edge cases), onboarding new client implementations if required, and improving the framework itself which involves adding fixtures, runtime errors, handling test failures, and maintaining dashboards that show the state of the clients' performance in the tests.

### Ream: Operating and Scaling PQ Interop Devnets

By Shariq Naiyer and Unnawut

The Ream team wants to operate and scale the post quantum interop devnets, which involves deploying post quantum clients (lean consensus clients) in realistic configurations, running them under load, and observing how they behave together, reporting findings, surfacing bugs from these runs and fixing them.

Tooling to play around be found at https://github.com/ReamLabs/leanstart 🦀.


### Ream: Execution Layer Integration for the Lean Chain

By Kolby ML and Shariq Naiyer

The Post Quantum spec is currently consensus-only. Ream's blocks carry only attestations, and there is no way for a wallet to submit a transaction against a lean network.

What made Ethereum different from what came before was that, for the first time, people could write programs backed by the same fundamental principles as Bitcoin. We think it would be cool to show that the same is true under PoC post-quantum testnet where users can send transactions and deploy smart contracts on a chain finalized in seconds, backend by post quantum security in Rust 🦀.

This project involves embedding reth (https://github.com/paradigmxyz/reth) directly into the Ream (https://github.com/ReamLabs/ream) binary as a library and driving it from inside the lean stack via reth's Execution Extensions (ExEx) framework. One process, no HTTP bridge between an Execution and Consensus. The success bar is a working "wallet → tx → block → confirmation" demo on a local lean devnet running as a single `ream lean_node` binary with reth embedded.

### Ream: Minimal PeerDAS Data Availability Client

By Shariq Naiyer and Kolby ML

Data Availability is the guarantee that the data behind a transaction has been published somewhere any node can fetch and verify it. Currently there are only execution and consensus clients and DA is often bundled with a consensus client. We want to build a dedicated DA client that can plug into a minimal beacon client and a generic interface so it could plug into a post quantum consensus client in Rust 🦀.

This project builds a standalone `ream da-node` binary fully dedicated to the data layer: a Data layer client that custodies and serves the full 128 columns, and does the minimal amount of non-DAS work possible. No fork choice, no execution, no validator, just the data layer, decoupled from any one consensus runtime and runnable alongside a minimal consensus node.

### Grandine: Lean Client

By Saulius Grigaitis

Grandine's [Lean Client](https://github.com/grandinetech/lean), written in Rust, is currently under active development with the goal of building a high-performance Ethereum lean client. In the short term, the project will focus on participating in upcoming devnets and validating interoperability. Longer term, the work will center on performance optimization, efficiency improvements, and production readiness.

### Grandine: Stable Containers (EIP-7688)

By Saulius Grigaitis

Stable Containers (EIP-7688) proposal is a strong candidate for inclusion in upcoming Ethereum hard forks. This project focuses on implementing EIP-7688 support in Grandine’s high-performance [SSZ library](https://github.com/grandinetech/grandine/tree/develop/ssz) and validating the implementation through extensive testing on Ethereum testnets.

### Grandine: FOCIL (EIP-7805)

By Saulius Grigaitis

EIP-7805 introduces FOCIL, a promising new feature for Ethereum. While several teams already maintain early implementations, dedicated testnets are expected to launch soon. Grandine aims to develop a robust and production-oriented FOCIL implementation, ensure compatibility with the broader ecosystem, and actively participate in upcoming testnet experiments. This work will contribute to validating and refining the proposal through real-world deployment and interoperability testing.

### Grandine: Disk Usage Optimization for State Storage

By Saulius Grigaitis

Grandine currently stores full Ethereum states every 32 epochs, resulting in redundant on-disk data and slower state reconstruction. In memory, Grandine already leverages structural sharing to eliminate overlapping data efficiently. This project aims to extend similar deduplication and delta-encoding techniques to persistent storage, significantly reducing disk usage while accelerating state transitions and historical state lookups. The work will also explore alternative database backends and storage architectures to further improve performance and scalability.

### Grandine: Attestation Packer

By Saulius Grigaitis

Grandine uses a sophisticated [attestation packer](https://github.com/grandinetech/grandine/blob/eeb33a92284751b71a0f44f410308235657c55f3/operation_pools/src/attestation_agg_pool/attestation_packer.rs) built around advanced solver-based optimization techniques. Originally developed for previous Ethereum hard forks, the attestation packer now requires updates to support the upcoming Glamsterdam hard fork. This project is particularly well suited for contributors interested in scientific computing, optimization, and packing algorithms, with opportunities to work on high-performance algorithm design in a real-world Ethereum client.

### Grandine: Standalone Validator Client

By Saulius Grigaitis

Grandine currently includes only a built-in Validator Client. Developing a standalone Validator Client would help attract users and operators who prefer a separate Validator Client architecture for flexibility, security, or operational reasons.

### Grandine: Execution Layer (EL) Client Integrations

By Saulius Grigaitis

We are already working on integrating Grandine with the Nethermind EL client to maximize performance by bypassing the HTTP-based Engine API. We now propose extending this work to support integrations with additional EL clients. In parallel, we plan to explore inverse integrations—embedding EL functionality directly into Grandine (for example, integrating Reth into Grandine). This work includes low-level optimizations such as replacing HTTP Engine API calls with efficient native function interfaces to reduce latency and improve overall performance.

### Grandine: zkVMs for Beacon Chain

By Saulius Grigaitis

We are experimenting with zkVMs (zero-knowledge virtual machines) to enable provable execution of the Beacon Chain state transition function. Early results using SP1 and RISC Zero demonstrate promising performance for networks with tens of thousands of validators. This project aims to scale the work further to support substantially larger validator sets while continuing to evaluate performance, proving costs, and architectural trade-offs.

### Grandine: Documentation

By Saulius Grigaitis

Grandine’s documentation requires a comprehensive refresh and expansion. This project is ideal for contributors who want to gain a deep understanding of Grandine’s architecture, features, and workflows while improving the developer and operator experience through clear, comprehensive, and up-to-date documentation.
