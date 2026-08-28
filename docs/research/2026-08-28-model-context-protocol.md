# Model Context Protocol: lessons for CAP

**Source:** [`modelcontextprotocol/modelcontextprotocol`](https://github.com/modelcontextprotocol/modelcontextprotocol), reviewed at [`d8fdc88fb970313247d8a180ac1ec3f6a10a8885`](https://github.com/modelcontextprotocol/modelcontextprotocol/tree/d8fdc88fb970313247d8a180ac1ec3f6a10a8885) against the 2026-07-28 specification on 2026-08-28.

**Status:** Public research summary. The mechanisms below are inputs to CAP's pre-spec incubation, not accepted protocol requirements.

## Verdict

MCP is a strong candidate for CAP's first transport binding, but it does not define what a community avatar is or when one is authorized to participate.

CAP should standardize avatar-specific semantics while reusing mature protocol machinery such as JSON-RPC envelopes, per-request versioning, capability negotiation, JSON Schema, HTTP authorization, cancellation, and conformance testing.

## Protocol principles worth adopting

MCP's published design principles favor:

- Convergence over multiple permanent ways to solve one problem.
- Composable primitives over use-case-specific core features.
- Interoperability across participants with unequal capabilities.
- Stability over protocol velocity.
- Demonstrated implementations over design-by-committee.
- Standardizing patterns that already work across implementations.

This supports CAP's pilot-first sequence. Candidate semantics should be exercised in a bounded participant run before they become normative protocol text.

## Mechanisms worth testing

### Assign explicit control ownership

MCP distinguishes application-controlled resources, user-controlled prompts, and model-controlled tools. The distinction makes the expected initiator of an operation explicit.

CAP should test equivalent ownership for avatar discovery, participation requests, session acceptance, addressed turns, evidence retrieval, correction, withdrawal, and finality. Joining or continuing a deliberation should not be an ordinary model-selected tool call.

Candidate: [#6 Keep participation host-controlled and make silence deterministic](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/6).

### Keep transport requests self-describing and domain state explicit

The modern MCP protocol carries version, client identity, and capabilities on each request rather than depending on an initialization session. Longer-lived application state uses explicit handles.

CAP should test an explicit participation handle that binds the accepted avatar, mandate, host, audience, authority, source policy, snapshot, and limits. Each turn should carry stable identity across retries and transport reconnections.

Candidate: [#12 Use explicit participation handles and idempotent turn receipts](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/12).

### Make human input a protocol state

MCP multi-round-trip requests can return an input-required result and resume only after the client supplies an authorized response. The transport does not need to remain open while waiting.

CAP should test whether operator approval, source-scope selection, requested authority outside the mandate, correction, withdrawal, or delivery reconciliation need an equivalent state. Consent generated in model prose is not a substitute.

Candidate: [#2 Make human approval an explicit protocol state](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/2).

### Negotiate capabilities and reject unsafe fallback

MCP advertises protocol versions and optional extensions through capabilities. Unsupported behavior must either use a documented fallback or reject the request.

For CAP, some fallbacks are semantically unsafe. A platform that cannot preserve disclosure, evidence, correction, or finality must reject participation rather than silently downgrade the avatar's role.

Candidate: [#11 Negotiate host capabilities and reject unsafe downgrades](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/11).

### Separate visible content from structured results

MCP tools can return human-readable content and schema-validated structured content. It also distinguishes protocol failures from errors or outcomes produced by an invoked operation.

CAP should test separate participant-visible text and a typed evidence, provenance, support, limitation, and delivery envelope. Platforms should not parse model prose to discover citations or decide whether a turn abstained.

Candidate: [#4 Separate contribution text from a typed evidence and outcome envelope](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/4).

### Bind credentials to their intended resource

MCP's HTTP authorization work uses protected-resource metadata, resource indicators, issuer validation, PKCE, and token audience validation. Token passthrough is prohibited because a credential issued for one resource must not become authority over another.

A CAP binding should preserve separate service, operator, host, and evidence-source authorization. Transport authentication still does not prove a representation mandate or authorize a private source for a particular audience.

Candidates: [#1 Define a versioned, revocable representation mandate](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/1) and [#10 Enforce authority and source scope at one pre-retrieval chokepoint](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/10).

### Trace normative requirements to executable checks

MCP requires observable normative behavior in standards-track changes to map to conformance checks or documented exclusions. SDK support claims are then evaluated against applicable tests rather than a reference implementation's existence.

CAP should test the same traceability for both avatar and platform obligations. A valid avatar envelope is insufficient if the platform strips disclosure; a valid host request is insufficient if the avatar retrieves outside its accepted scope.

Candidate: [#7 Require traceable conformance checks and one immutable pilot evidence bundle](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/7).

## Candidate first binding

An MCP binding could reuse:

- JSON-RPC request, result, error, and notification envelopes.
- Standard input/output and Streamable HTTP transports.
- Per-request protocol version metadata and server discovery.
- Reverse-domain extension identifiers and capability negotiation.
- JSON Schema inputs and outputs.
- Cancellation, progress, and multi-round-trip input.
- OAuth protected-resource discovery and audience-bound tokens.
- Optional long-running tasks when observed latency requires them.

Avatar description, participation requests, addressed turns, correction, and withdrawal should be host-controlled CAP extension operations rather than generic model-selected MCP tools.

Candidate: [#8 Evaluate MCP as the first CAP binding without making MCP the definition](https://github.com/Citizen-Infra/conversational-avatar-protocol/issues/8).

## What MCP does not solve

MCP does not define:

- Whether an avatar may represent a community.
- Who issued or may revoke that mandate.
- Which evidence sources are authorized for a deliberation audience.
- How decisions, proposals, tensions, and research remain distinct.
- Mandatory participant disclosure.
- Contribution correction, withdrawal, supersession, or deliberation finality.
- The difference between consulting a context source and inviting a representative participant.

Those are candidate CAP semantics, not missing MCP core features.

## Patterns not to copy prematurely

- Exposing a private evidence corpus as a general resource catalogue.
- Using client or server identity as proof of representative authority.
- Adding every MCP primitive to the first binding.
- Supporting legacy protocol eras before CAP has shipped consumers.
- Maintaining several speculative bindings before one works.
- Treating generic asynchronous tasks as the complete deliberation-session lifecycle.

## What remains unproven

The participant vertical slice must first produce stable, typed semantic envelopes. Only then can the project test whether they map cleanly to an MCP extension without changing control ownership or leaking implementation details.

MCP becomes the first binding only if it removes transport work while preserving CAP semantics. It remains optional for other implementations.

## Primary references

- [MCP 2026-07-28 specification](https://github.com/modelcontextprotocol/modelcontextprotocol/blob/d8fdc88fb970313247d8a180ac1ec3f6a10a8885/docs/specification/2026-07-28/index.mdx)
- [Architecture](https://github.com/modelcontextprotocol/modelcontextprotocol/blob/d8fdc88fb970313247d8a180ac1ec3f6a10a8885/docs/specification/2026-07-28/architecture/index.mdx)
- [Versioning and compatibility](https://github.com/modelcontextprotocol/modelcontextprotocol/blob/d8fdc88fb970313247d8a180ac1ec3f6a10a8885/docs/specification/2026-07-28/basic/versioning.mdx)
- [Tools](https://github.com/modelcontextprotocol/modelcontextprotocol/blob/d8fdc88fb970313247d8a180ac1ec3f6a10a8885/docs/specification/2026-07-28/server/tools.mdx)
- [Authorization](https://github.com/modelcontextprotocol/modelcontextprotocol/tree/d8fdc88fb970313247d8a180ac1ec3f6a10a8885/docs/specification/2026-07-28/basic/authorization)
- [Extensions](https://github.com/modelcontextprotocol/modelcontextprotocol/blob/d8fdc88fb970313247d8a180ac1ec3f6a10a8885/docs/extensions/overview.mdx)
- [Design principles](https://github.com/modelcontextprotocol/modelcontextprotocol/blob/d8fdc88fb970313247d8a180ac1ec3f6a10a8885/docs/community/design-principles.mdx)
- [Multi-round-trip requests](https://github.com/modelcontextprotocol/modelcontextprotocol/blob/d8fdc88fb970313247d8a180ac1ec3f6a10a8885/seps/2322-MRTR.md)
- [Conformance traceability](https://github.com/modelcontextprotocol/modelcontextprotocol/blob/d8fdc88fb970313247d8a180ac1ec3f6a10a8885/seps/2484-conformance-tests-required-for-final-seps.md)
- [Stateless MCP](https://github.com/modelcontextprotocol/modelcontextprotocol/blob/d8fdc88fb970313247d8a180ac1ec3f6a10a8885/seps/2575-stateless-mcp.md)
