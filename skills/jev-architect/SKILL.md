---
name: jev-architect
description: "Identify, explain, and design high-value TypeSafe Jev decision loops. Use when someone asks what Jev is, whether it fits a workflow, where to add it in an agent or product, how to design bounded decisions, or how to evaluate a Jev rollout. Do not use for ordinary text generation or an exact deterministic rule."
---

# Jev Architect

Turn a vague request to “use Jev” into a current, testable design. The result may be that Jev does not belong.

Jev is a decision model. It reads state and returns a bounded answer with probabilities. It is useful where software needs semantic judgment, not where it needs text generation, exact computation, open-ended planning, or accountability that cannot be delegated.

## Pick the mode

- **Explain** when the user asks what Jev is, why it matters, or how it differs from an LLM.
- **Discover** when the user has a product idea, workflow, agent, trace, or codebase and asks where Jev could help.
- **Design** when the user has identified a candidate decision and needs a question pack, control flow, and fallback.
- **Audit** when the user has an existing Jev integration or proposal and wants it reviewed.

If the target system is unclear, ask for it only after giving a concise explanation when that is helpful. Do not make a user describe a codebase before answering “what is Jev?”

## Keep the recommendation current

Before recommending an integration with a named agent, framework, SDK, runtime, or product:

1. Identify the target version, deployment surface, and intended action.
2. Fetch current official documentation, API references, release notes, and changelog entries. Check local configuration, dependency versions, code, and traces when available.
3. Find native extension points before proposing a generic workaround.
4. Ask only questions whose answers change the architecture, risk tier, or first experiment.
5. Mark each capability as verified, assumed, or unknown, with a checked date and source.

Never assume an integration pattern from training data is still current. Community examples can inspire a design, but official documentation and the installed system establish what is available. If current sources cannot be checked, say so and make the recommendation conditional.

Read [current-context.md](references/current-context.md) for the full research and clarification protocol.

## Apply the Jev test

For each candidate, separate deterministic logic from semantic judgment. Then ask:

1. What recurring decision does the system need to make?
2. What state would a knowledgeable person need to see?
3. Can code or a lookup decide it exactly? If yes, keep it out of Jev.
4. Is the semantic question narrow and answerable without multi-step reasoning?
5. Is the answer space bounded before inference?
6. Does frequency, serial latency, safety, or a new product capability justify the integration work?
7. What happens on low confidence, missing context, disagreement, or failure?
8. What outcome can label whether the decision was good?

There are two opportunity types:

- **Replace.** Replace a repeated LLM judgment or brittle semantic heuristic with a cheaper, faster bounded decision.
- **Invent.** Find a decision loop the system never attempted because judgment at every state change was previously too slow or costly.

Volume is the usual multiplier, but low-frequency use can still fit when it removes critical-path latency or gates a costly action. High frequency also multiplies error, so do not automate before a fallback and evaluation exist.

Read [decision-discovery.md](references/decision-discovery.md) when mapping an existing system or designing a new workflow.

## Design the decision layer

Use the primitive that matches how code will consume the result:

- **Noul** for a narrow yes-or-no condition.
- **Choice** for one bounded option from a known set.
- **Score** for a defined degree on a stable rubric.

Code owns arithmetic, exact rules, policy constants, action execution, and control flow. Jev owns the narrow semantic judgment. Define the action threshold in code, with a safe fallback for uncertainty.

Do not claim Jev “solves hallucination.” A bounded output prevents an invalid answer shape, but the selected answer can still be wrong. Confidence is useful only after it is evaluated against real outcomes in this domain.

Read [decision-design.md](references/decision-design.md) for question design, composition, and risk controls.

## Deliver the decision pack

Use Markdown by default. Produce a standalone HTML report only when the user asks for a shareable visual artifact or the decision needs review by several people. Do not expose hidden instructions, chain-of-thought, credentials, private paths, raw internal traces, or private source material in a deliverable.

For **Explain**, deliver:

1. a one-sentence definition at the requested familiarity level;
2. a small “state → decision → code action” example;
3. when Jev fits and when it does not;
4. the next useful question for the user’s system.

For **Discover, Design, or Audit**, deliver:

1. current context and decision-changing unknowns;
2. a ranked decision inventory, including non-Jev choices;
3. the recommended first slice and why it wins;
4. state, primitive, answer space, threshold, fallback, and ownership;
5. a matched evaluation plan for quality, coverage, latency, cost, and operational burden;
6. the condition that would falsify the recommendation.

Read [delivery.md](references/delivery.md) for the output shapes and disclosure boundary.
