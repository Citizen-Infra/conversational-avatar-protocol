# Conversational Avatar Protocol

> **Status: pre-spec incubation.** CAP has no stable protocol revision, conformant implementation, or compatibility guarantee.

The Conversational Avatar Protocol (CAP) is an exploration of interoperable, disclosed AI avatars that contribute source-grounded perspectives on behalf of communities in deliberation systems.

CAP is being discovered through a working community-avatar participant pilot. Issues in this repository are protocol candidates, not accepted requirements. No implementation may claim CAP conformance until a versioned protocol and conformance suite are published.

## What belongs here

- Protocol questions that affect interoperability between an avatar runtime and a deliberation platform.
- Public research sources and testable protocol hypotheses derived from them.
- Evidence requirements for the first participant vertical slice.
- Decisions to accept, revise, or reject candidate semantics after implementation evidence exists.
- Versioned schemas, bindings, and conformance material only after the pilot proves their boundary.

## What does not belong here

- Private community records, source policies, participant transcripts, or credentials.
- Product-specific implementation details and operational incidents.
- Model, vector store, storage, repository host, or agent-framework requirements.
- Claims that an avatar may represent a community without a separately validated mandate.
- A reusable SDK before stable implementation seams have emerged.

## Incubation sequence

Research source -> protocol candidate issue -> evidence from a bounded participant vertical slice -> steward decision to accept, revise, or reject -> normative protocol text and conformance checks.

The repository is a coordination and evidence surface, not a substitute for proving the protocol through use.

## Candidate issue contract

Each protocol candidate should state:

- The public source and concrete mechanism.
- The interoperability problem it may solve.
- Why the concern belongs in CAP rather than a runtime, product, or transport binding.
- Evidence the vertical slice must collect.
- Acceptance and rejection criteria.
- Explicit non-goals.
- Security and privacy implications.

Candidate issues remain non-normative until a steward decision records otherwise.

## Initial boundaries

CAP is expected to address avatar identity, representation mandate, participation, evidence, authority, privacy, correction, finality, and platform interoperability.

CAP is not expected to define brain ingestion, retrieval implementation, prompts, models, memory, deployment, or deliberation-record storage. Model Context Protocol (MCP), HTTP, or an in-process library may become bindings without defining what a community avatar is.

Consulting an avatar as a context source is distinct from inviting it as a disclosed participant. The first vertical slice tests participation.

## Research references

The first protocol candidates draw from these public sources:

- [elizaOS Eliza research summary](docs/research/2026-08-28-elizaos-eliza.md), using the pinned source as a pattern library and threat model rather than the pilot runtime.
- [Model Context Protocol research summary](docs/research/2026-08-28-model-context-protocol.md), using the pinned source for protocol design, capability negotiation, authorization, versioning, extensions, and conformance patterns.
- [Team OS Toolkit and Robin research summary](docs/research/2026-08-28-team-os-toolkit.md), using the pinned source for specification, initialization-skill, implementation-choice, and acceptance-test packaging patterns around CAP.
- [Decentralized Deliberation Stack research summary](docs/research/2026-08-28-dds.md), using the pinned source to define the adjacent deliberation-record boundary and a possible future compatibility mapping without making CAP dependent on DDS.
- [Avatar SDK protocol note](https://github.com/harmonicabot/avatar-sdk/blob/main/docs/protocol.md), used as historical source material rather than a specification to adopt unchanged.

## License

Unless a file states otherwise, specification text, schemas, conformance material, bindings, documentation, and code in this repository are licensed under the [Apache License 2.0](LICENSE). Contributions intentionally submitted for inclusion are licensed on the same terms unless explicitly marked otherwise.

The license does not grant permission to use CIBC names or marks except as required to describe the origin of the work.

## Stewardship

CAP is incubated by the [Citizen Infrastructure Builders Club](https://citizeninfra.org/). A contribution or open issue does not establish a CIBC position or an accepted CAP requirement.
