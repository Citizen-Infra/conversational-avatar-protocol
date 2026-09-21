# Mirror and recursive representation: what a mandate authorizes

**Source:** [Andrew Sorota, "The Mirror and the Loop"](https://informationaldemocracy.substack.com/p/the-mirror-and-the-loop), Informational Democracy, a working group of the Max Planck Institute for Political and Social Science, published 2026-09-15 and retrieved 2026-09-20. It develops [Jane Mansbridge, "Recursive Representation in the Representative System"](https://www.hks.harvard.edu/publications/recursive-representation-representative-system) (2017).

**Unlike the other summaries in this folder, this source cannot be pinned to a revision.** It is a Substack essay with no commit history, and the publication may be edited without notice. Quotations below are from the 2026-09-20 retrieval. Anything CAP takes from it should be restated in CAP's own words in a candidate issue rather than cited as a stable external definition.

**Status:** Public research summary. Political theory, not a protocol specification. It is not evidence that anyone outside this project has considered community avatars, and the essay never mentions them.

## Verdict

The essay supplies the distinction CAP is missing between *who authorized an avatar* and *what kind of representation they authorized*. That gap is real and currently invisible at the protocol boundary: two avatars holding identical valid mandates under #1 can produce contributions that assert different things.

It supplies no mechanism. The essay is about individuals represented by their own agents in political life, which is not CAP's case, and the transfer to a community avatar has to be argued rather than assumed. Candidate issue #13 makes that argument and states the conditions under which it should be rejected.

## What the essay argues

An AI agent can now learn a person's preferences and carry them into politics on their behalf. Sorota argues that building it to do only that is a mistake, and names the two designs.

**Mirror representation** takes the represented party's positions as fixed inputs and reflects them outward with maximal fidelity. It is the natural reading of John Adams's representative assembly as "in miniature an exact portrait of the people at large".

**Recursive representation**, after Mansbridge, is an iterated exchange in which representative and represented each "update, revise, and respond", and **both are changed**. Applied to an agent, the rule is directional: inwardly it challenges the represented party and surfaces standpoints they did not hold; outwardly, toward institutions and other agents, it is maximally faithful to what those exchanges produced. Sorota calls the result "deliberately two-faced".

The second boundary is what keeps recursion from becoming paternalism. The agent never constructs its own wisdom that diverges from the represented party's views; it makes other standpoints available and remains faithful to what the party then holds.

## The constraint that makes it testable

The essay's operative limit, and the reason this is not an aspiration:

> Agentic representatives cannot **do** representative thinking for anyone — this kind of work cannot be outsourced — but they can supply what that thinking needs by **making the absent present**.

"Representative thinking" is Arendt's, from "Truth and Politics" (1967): making present to one's mind the standpoints of those who are absent, while retaining one's own judgment.

The division of responsibility this implies is directly usable. The system is answerable for **supplying the absent standpoint**. The represented party is answerable for the thinking. Any requirement written the other way — that the represented party's view must change — grades the wrong party and cannot be met by a runtime honestly.

## Why the default is mirroring

Sorota names three mechanisms, and they need different answers:

| Mechanism | What it is |
|---|---|
| Design | Agents are trained substantially on human approval signals; preference-adherence is a quantifiable training metric |
| Political economy | An engagement-driven information economy, in which sycophancy retains users |
| Normative | Under an aggregative view of democracy, an agent that does anything other than mirror "might be accused of corrupting democracy" |

The third matters most for CAP. It means a recursive avatar is open to the charge that it distorted its community's position, and that the charge is unanswerable unless something in the record shows what the contribution was derived from. This is the argument for the derivation basis in #13, and it is a protocol concern rather than a presentation one: the accusation is about what the contribution asserts, not how it was displayed.

## The relevant empirical finding

Collective Intelligence Project, Global Dialogues index, February 2026: **44.5 percent of people report feeling more certain of their beliefs after interacting with AI, against 4.8 percent who report feeling less certain** — roughly three times less likely to induce doubt than social media. <https://globaldialogues.ai/cadence/february-2026>

Read carefully, this is a finding about individuals interacting with general assistants, not about community avatars, and it should not be cited as evidence about avatars. What it does establish is that mirroring is the observed default at scale rather than a theoretical worry, which is the reason to make the mode explicit rather than assume a sensible one.

## Where this lands on CAP's boundaries

| Concern | Home |
|---|---|
| Which representation mode a community authorized | CAP mandate (#1, extended by #13) |
| What an outward contribution was derived from | CAP evidence envelope (#4, extended by #13) |
| Whether a platform can render or must reject the distinction | CAP capability negotiation (#11) |
| How a runtime conducts an inward challenge | Avatar runtime — explicitly outside CAP |
| Whether an inward challenge was any good | Nobody's protocol; a deliberation-quality question |
| Prompts, models, memory, retrieval | Avatar runtime — already excluded by the repository README |

## What CAP should not copy prematurely

- **The individual-agent frame.** The essay's subject is one person represented by their own agent. A community avatar represents a collective that deliberates internally, which is a different object with different failure modes. The transfer is an argument, not an inheritance.
- **Recursion as a requirement.** Nothing here shows a community avatar *should* engage recursively. The candidate makes the mode explicit and declines to prefer one.
- **The certainty statistic as an avatar measurement.** It measures individuals using general assistants. Citing it as evidence about avatar behaviour would be a category error.
- **Arendt or Mansbridge as normative text in a protocol.** A specification should define observable obligations. The lineage belongs in research summaries and rationale, not in normative clauses.
- **Any quality judgement about the inward exchange.** The moment a protocol asks whether a challenge was adequate, it needs a judge, and CAP has no basis for one.

## What remains unproven

No reviewed source shows that a community avatar can recursively engage the community it represents, or that a community wants one that does. The plausible outcome of the first vertical slice is that community avatars are **mirror representatives by construction** — an avatar grounded in a fixed corpus has no living party to put a counter-standpoint to, and a community that has recorded its positions may regard re-interrogation as overreach rather than diligence.

That would be a useful negative result, and #13 is written so it can be rejected on those grounds rather than quietly widened to fit.

No source shows that a derivation basis can be carried without leaking the internal deliberation it points at. That is the privacy question the vertical slice has to answer before the envelope half of #13 is accepted.

## Adjacent work

A criterion of the same shape is open on the Open Facilitation Library side, at [`Open-Facilitation-Library/method-specs#28`](https://github.com/Open-Facilitation-Library/method-specs/issues/28): whether a facilitated session put in front of each participant a standpoint they did not already hold. A disclosed CAP avatar is one mechanism for satisfying it. No dependency is proposed in either direction; the two projects should know the other's framing exists.

The same publication produced [Théophile Pénigaud, "Orphan Reasons: Who Is Responsible When AI Decides?"](https://informationaldemocracy.substack.com/p/orphan-reasons-who-is-responsible) (2026-09-01), which bears on the evidence envelope in #4 from the accountability side: asking a model to justify itself returns a new prediction rather than an account, so provenance must be deterministic. It is summarised at [`2026-09-21-penigaud-orphan-reasons.md`](2026-09-21-penigaud-orphan-reasons.md), which bears on the mandate in #1 and the evidence envelope in #4.

## Primary references

- [Andrew Sorota, "The Mirror and the Loop"](https://informationaldemocracy.substack.com/p/the-mirror-and-the-loop) — the source, retrieved 2026-09-20
- [The parent provocation, "What is a citizen in the age of agents?"](https://informationaldemocracy.substack.com/p/provocation-sorota) — not reviewed
- [Jane Mansbridge, "Recursive Representation in the Representative System"](https://www.hks.harvard.edu/publications/recursive-representation-representative-system) (2017) — the concept's origin, not reviewed directly
- [Collective Intelligence Project, Global Dialogues, February 2026](https://globaldialogues.ai/cadence/february-2026) — the certainty finding
- [arXiv:2510.15144](https://arxiv.org/abs/2510.15144) — cited in the essay for the finding that models can mimic stated views but struggle to predict reasoning in unfamiliar situations; not reviewed directly
