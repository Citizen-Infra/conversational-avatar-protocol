# elizaOS Eliza: lessons for CAP

**Source:** [`elizaOS/eliza`](https://github.com/elizaOS/eliza), reviewed at [`a06d108772c430014219b1ed32027e21b86154ac`](https://github.com/elizaOS/eliza/tree/a06d108772c430014219b1ed32027e21b86154ac) on 2026-08-28.

**Status:** Public research summary. The mechanisms below are inputs to CAP's pre-spec incubation, not accepted protocol requirements.

## Verdict

Use Eliza as a pattern library and threat model, not as the required runtime for a conversational avatar.

Eliza is a broad autonomous-agent framework with models, memory, plugins, connectors, scheduling, applications, cloud services, and device capabilities. CAP addresses a narrower interoperability boundary: how a disclosed avatar accepts a representative mandate and participates safely in a deliberation platform.

## Mechanisms worth testing

### Separate descriptive identity from authority

Eliza distinguishes principals such as people, agents, services, and organizations. Identity claims can carry verification, status, provenance, ownership, and revocation. Its general character configuration separately describes name, prompts, style, examples, knowledge, plugins, and settings.

CAP should test whether representative authority needs its own versioned, revocable mandate rather than being implied by an avatar name or prompt. The mandate must distinguish the avatar, represented community, operator, issuer, and host.

Candidate: [#1 Define a versioned, revocable representation mandate](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/1).

### Declare policy at the owner and enforce it at one chokepoint

Eliza's architecture work found that planners, direct handlers, autonomous paths, and plugins could otherwise reach actions through inconsistent permission gates. Its corrective principle is to declare requirements with the capability owner and enforce them at one runtime boundary.

For CAP, the observable requirement may be that every adapter uses the same authority and source-scope decision before retrieval, generation, or delivery. Search, ranking, counts, fragments, and citations should operate only over an already authorized source view.

Candidate: [#10 Enforce authority and source scope at one pre-retrieval chokepoint](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/10).

### Negotiate platform capabilities before participation

Eliza messaging connectors expose versioned capability profiles for controls, fallbacks, size limits, threads, and sensitive input. The interaction host can reject unsupported behavior before rendering or committing an effect.

CAP should test a host capability profile for AI disclosure, citations, correction, withdrawal, context classes, limits, delivery receipts, and finality. Missing capabilities must not silently change a participant into a consultant or strip evidence from a contribution.

Candidate: [#11 Negotiate host capabilities and reject unsafe downgrades](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/11).

### Bind an external effect to durable authority and replay state

Eliza's interactive-message authority binds an actor, audience, agent, connector, room, response shape, authorization decision, expiry, effect, and replay key. State transitions distinguish work that is pending, claimed, committed, or completed.

CAP does not need the entire mechanism, but it should test stable participation and turn identities, retained receipts, and truthful delivery ambiguity. A retry after an uncertain commit must not generate a second contribution automatically.

Candidate: [#12 Use explicit participation handles and idempotent turn receipts](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/12).

### Isolate participant runtimes and make silence testable

Eliza's multi-agent arena gives each seat a separate runtime, identity, store, and inference path. Its evaluations test direct addressing, peer reverb, adversarial extraction, provider failures, latency, and isolation. Its When2Speak work distinguishes speaking from silence and treats trusted addressing differently from textual references.

CAP should prefer deterministic host-controlled turn eligibility over model inference. Ambient context, quoted mentions, peer instructions, and an avatar's own follow-up text should not create another authorized turn.

Candidate: [#6 Keep participation host-controlled and make silence deterministic](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/6).

### Retain one verifiable evidence bundle per run

Eliza evidence bundles bind artifacts to a canonical manifest with hashes, source revision, runner, environment allowlist, timings, and provenance. Its scenario runner combines deterministic fixtures, live-model trajectories, assertions, and bounded waits.

CAP should test an immutable pilot bundle that binds the invitation, mandate, capabilities, source policy, runtime versions, turn receipts, evidence envelopes, failures, and reviewer decision without publishing private source material.

Candidate: [#7 Require traceable conformance checks and one immutable pilot evidence bundle](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/7).

## Patterns not to adopt as CAP requirements

- A full autonomous-agent framework as the protocol runtime.
- A character object that combines authority, prompts, knowledge, plugins, settings, and secrets.
- Autonomous discovery, joining, or continuation of deliberations.
- Writable evaluator memory that promotes an avatar's interpretation into canonical community knowledge.
- Optional authorization that falls back to broad access when context is absent.
- Dynamic plugin installation before stable extension seams and supply-chain controls exist.
- A required model provider, storage adapter, vector database, or deployment topology.

These may be valid implementation choices for some runtimes. They are not evidence of a durable interoperability requirement.

## What remains unproven

The source demonstrates useful mechanisms inside one framework. It does not prove that every mechanism belongs in CAP, that the proposed field boundaries are sufficient, or that independent avatar and platform implementations interpret them consistently.

A bounded participant vertical slice must determine which mechanisms cross the runtime/platform boundary. Candidate issues become normative only after implementation evidence and an explicit steward decision.

## Primary references

- [Repository README](https://github.com/elizaOS/eliza/blob/a06d108772c430014219b1ed32027e21b86154ac/README.md)
- [Core runtime](https://github.com/elizaOS/eliza/blob/a06d108772c430014219b1ed32027e21b86154ac/packages/core/README.md)
- [Character configuration](https://github.com/elizaOS/eliza/blob/a06d108772c430014219b1ed32027e21b86154ac/packages/core/src/types/agent.ts)
- [Access context](https://github.com/elizaOS/eliza/blob/a06d108772c430014219b1ed32027e21b86154ac/packages/core/src/types/access-context.ts)
- [Identity authority contracts](https://github.com/elizaOS/eliza/blob/a06d108772c430014219b1ed32027e21b86154ac/packages/core/src/types/identity.ts)
- [Interactive message protocol](https://github.com/elizaOS/eliza/blob/a06d108772c430014219b1ed32027e21b86154ac/packages/core/src/messaging/interactions/README.md)
- [Scenario runner](https://github.com/elizaOS/eliza/blob/a06d108772c430014219b1ed32027e21b86154ac/packages/scenario-runner/README.md)
- [Evidence bundle](https://github.com/elizaOS/eliza/blob/a06d108772c430014219b1ed32027e21b86154ac/packages/evidence/README.md)
- [Architecture audit](https://github.com/elizaOS/eliza/issues/12086)
