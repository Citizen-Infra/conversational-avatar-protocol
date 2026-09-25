# Candidate sequencing

> **Status: working order, not a commitment.** This document orders the open protocol candidates for design and testing in the first participant vertical slice. It does not accept any candidate, and the order should change when pilot evidence does.

Every candidate asks to accept only what the pilot actually exercises. The order below follows the dependencies the candidates state about each other, so that each one is tested on top of the semantics it assumes.

## Step 0: Define the pilot

Before any candidate can be accepted or rejected, write down the vertical slice itself:

- which avatar participates, and whether it represents a living community or a published corpus;
- which deliberation platform and adapter host it;
- which community issues its mandate, and who operates it.

**Answered in [pilot.md](pilot.md):** Bucky Avatar, representing CIBC, in one private Harmonica participant thread. That document also maps what the pilot can and cannot show for each candidate.

The avatar question also settles part of [#13](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/13) early (see Phase 4).

## Phase 1: Pre-generation gates

These define what must be true before any model is called. Most later candidates reference them.

1. **[#1](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/1) Versioned, revocable representation mandate.** The most referenced candidate: receipts record its version ([#12](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/12)), [#13](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/13) adds a field to it, and [#14](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/14) routes challenges to the issuer or operator it names.
2. **[#10](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/10) One pre-retrieval chokepoint for authority and source scope.** [#4](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/4), [#13](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/13) and [#14](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/14) rely on it for leak prevention. Deterministically testable.
3. **[#6](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/6) Host-controlled participation and deterministic silence.** Fixes who may create a turn. [#8](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/8) depends on participation staying outside model-selected tools.

Start **[#7](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/7)** in this phase as a running requirement-to-check manifest, adding checks for each candidate as it is worked on. The immutable evidence bundle comes at the end.

## Phase 2: Turn identity and output

4. **[#12](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/12) Explicit participation handles and idempotent turn receipts.** [#14](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/14) needs a contribution receipt to reference, and [#8](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/8) needs a handle that survives reconnection.
5. **[#4](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/4) Contribution text separated from a typed evidence and outcome envelope.** [#13](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/13) and [#14](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/14) both build on the envelope.

## Phase 3: Negotiation and approval

6. **[#11](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/11) Host capability negotiation and unsafe-downgrade rejection.** Which capabilities are mandatory depends on what the envelope and receipts must preserve.
7. **[#2](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/2) Human approval as an explicit protocol state.** May reduce to a single start approval, which the candidate itself says should then reject a generic mechanism. [#14](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/14) reuses this state to hold a challenge open, so its scope should be settled first.

## Phase 4: Extensions

8. **[#13](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/13) Mirror or recursive representation in the mandate.** Extends [#1](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/1) and [#4](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/4) and relies on [#10](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/10) and [#11](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/11). Its non-goals exclude corpus-grounded avatars, so if the pilot avatar represents a published corpus rather than a living community, the expected outcome is the "mirror by construction" rejection. That can be decided as soon as Step 0 is.
9. **[#14](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/14) Challenged contributions routed to the answerable party.** Depends on [#1](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/1), [#2](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/2), [#4](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/4), [#10](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/10) and [#12](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/12). Its central risk, an unreachable answerable party, would also be a finding about [#1](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/1).

## Phase 5: After the vertical slice

10. **[#8](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/8) MCP as the first binding.** Explicitly blocked on the vertical slice. Its acceptance criteria need stable envelopes ([#4](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/4)), safe rejection ([#11](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/11)), host-controlled participation ([#6](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/6)) and handles that survive reconnection ([#12](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/12)).
11. **[#7](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/7) Evidence bundle and steward decisions.** Freeze the immutable bundle for the pilot run and record accept, revise or reject for each candidate.

## Dependency summary

| Candidate | Builds on |
|---|---|
| [#1](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/1) Mandate | none |
| [#10](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/10) Chokepoint | none |
| [#6](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/6) Host-controlled participation | none |
| [#7](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/7) Conformance and evidence bundle | all candidates under test |
| [#12](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/12) Handles and receipts | [#1](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/1) |
| [#4](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/4) Evidence envelope | [#1](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/1), [#10](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/10) |
| [#11](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/11) Capability negotiation | [#4](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/4), [#12](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/12) |
| [#2](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/2) Approval state | [#1](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/1) |
| [#13](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/13) Representation mode | [#1](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/1), [#4](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/4), [#7](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/7), [#10](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/10), [#11](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/11) |
| [#14](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/14) Challenge routing | [#1](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/1), [#2](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/2), [#4](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/4), [#10](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/10), [#12](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/12) |
| [#8](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/8) MCP binding | [#4](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/4), [#6](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/6), [#11](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/11), [#12](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/12) |
