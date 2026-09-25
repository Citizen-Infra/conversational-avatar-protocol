# First participant vertical slice

> **Status: pilot definition, not a protocol decision.** This document records what the first vertical slice will run so that each candidate can be tested against it. It accepts no candidate, and it does not establish that an avatar can generally represent its community. It answers Step 0 of the [candidate sequencing](roadmap.md).

## The pilot

| Question | Answer |
|---|---|
| Avatar | **Bucky Avatar**, a separate participant role for Bucky, CIBC's existing read-only guide to its own records. It shares Bucky's identity and evidence infrastructure but not its prompt, authorization, tools, conversation state, credentials, or audit stream. |
| Participant name | `Bucky, CIBC's AI avatar`, with the representation limits also stated in the session disclosure. |
| Represented community | The Citizen Infrastructure Builders Club (CIBC): a living community, not a published corpus. |
| Mandate issuer | CIBC. |
| Operator | The CIBC steward who authorizes the run. |
| Deliberation platform | Harmonica, through a direct participant adapter. The adapter keeps the semantic envelopes a later binding would need, but is not itself an MCP binding. |
| Session | One private, asynchronous, text-only Harmonica participant thread, started manually by the operator. |
| Audience | Internal only: the authorizing operator and one named CIBC steward reviewer. No members, partners, or external participants. |
| Sources | An explicit source-path allowlist over CIBC's private record, chosen for the session topic and frozen before the run. The allowlist is a private session input and is not published here. |
| Authority | Recorded perspectives only. The avatar may represent recorded decisions, attributed proposals, unresolved tensions, and research, preserving each record's status and uncertainty. It does not vote, decide, commit CIBC, infer consensus, or replace a human representative. |
| Human gates | One approval before the bounded run starts, and a new approval for any stop, correction, or withdrawal. Ordinary addressed turns proceed without per-message approval. |
| Correction and withdrawal | Only the authorizing steward may originate one. It appears as an append-only, participant-visible notice that identifies the original contribution; the original stays in the session record. |
| Citations | Visible in the contribution text, plus a separate structured evidence envelope retained in the pilot evidence bundle. Harmonica's participant message surface currently has no citation metadata field, so the adapter must not claim that capability. |

The pilot starts only after CIBC's existing guide deployment completes its own acceptance, and only once the session topic and source allowlist are chosen.

### Out of scope

Voice or video; ambient group-chat participation; automatic discovery or joining of sessions; voting, ratification, negotiation, or commitments for CIBC; writes back to CIBC's record or learning from the session without review; exposing the private record to an external audience; exposing it as a general MCP resource catalogue; representing participation as a model-selected tool; and building an SDK before the slice works.

## What the pilot exercises

What each candidate can and cannot learn from this pilot, in [roadmap](roadmap.md) order.

| Candidate | Exercised | What the pilot can show, and its limits |
|---|---|---|
| [#1](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/1) Mandate | Yes | A real issuer (CIBC) and operator (the authorizing steward). The runtime validates a current mandate before generation; the evidence bundle records its version. |
| [#10](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/10) Chokepoint | Yes | The frozen allowlist is applied before any search, ranking, count, fragment, or read, and the same gate covers the Harmonica adapter and local preview. The private record contains material that must not reach even this internal audience unless allowlisted, so leakage is a real test. |
| [#6](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/6) Host-controlled participation | Yes | Manual initiation only, addressed turns only, and deterministic silence for ambient mentions and model-initiated participation attempts. |
| [#7](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/7) Conformance and evidence bundle | Yes | Deterministic scenarios (ambient silence, source isolation, duplicate turns, cancellation, delivery ambiguity) before a fresh live-model smoke, and one immutable, content-minimized bundle. |
| [#12](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/12) Handles and receipts | Yes | Replaying a turn request must not produce a second contribution, and a simulated ambiguous delivery must be reconciled rather than regenerated. |
| [#4](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/4) Evidence envelope | Partly | Every substantive contribution gets a schema-valid envelope, but the host cannot receive it: Harmonica has no citation metadata field. The pilot can test whether the envelope is sufficient for review, not whether a platform can render a contribution without parsing prose. |
| [#11](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/11) Capability negotiation | Yes | The runtime checks an adequate host capability profile before generation. The missing citation metadata field is a real capability gap the adapter has to declare rather than paper over. |
| [#2](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/2) Approval state | Yes | The pilot needs more than one start approval: stop, correction, and withdrawal each require a new approval from the authorizing steward. That is the case the candidate says would justify an explicit protocol state. |
| [#13](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/13) Representation mode | Mode only | CIBC is a living community, so the candidate applies. But the avatar represents what CIBC has already recorded and has no community-facing exchange before it speaks, so it is expected to be a mirror representative. The pilot can test whether the mode field is needed; the derivation-basis half should be rejected for now, as the candidate itself anticipates. |
| [#14](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/14) Challenge routing | Not yet | Challenges are not in the current pilot scope. The only other participant is the steward reviewer, so a challenge would have to be simulated. The answerable party (CIBC's stewards) is reachable, which removes the candidate's central risk but also means the pilot cannot test it. |
| [#8](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/8) MCP binding | No | The first adapter is direct. MCP is evaluated only after the slice produces stable envelopes, as the candidate requires. |

## Passing the slice

The slice passes when, among other checks, the avatar is visibly disclosed before its first substantive contribution; a current mandate and adequate host capabilities are validated before any model call; it uses only the frozen allowlist and one pinned snapshot of the record; every substantive contribution is cited or explicitly partial or abstained; record status is preserved and nothing becomes implied consensus; nothing unauthorized leaks, including whether a non-allowlisted record exists; the run stays within its turn and cost bounds and ends cleanly; and a CIBC steward judges the transcript faithful enough to allow the same bounded test again.

Each criterion, and each candidate's pilot evidence, is mapped to a deterministic scenario, the live run, reviewer judgement, or a documented exclusion in [pilot-checks.md](pilot-checks.md).

Passing establishes only that one policy and source set produced one reviewable, faithful participation episode.

## Open before the run

- **Session topic and source allowlist.** The only unresolved pilot input. It blocks the run and stays private.
- **Whether to include a simulated challenge** so that [#14](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/14) gets any evidence from this slice, or to defer it to a pilot with a wider audience.
- **Whether Harmonica can carry citation metadata.** If not, [#4](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/4)'s platform-rendering evidence needs a second platform or a later adapter.
