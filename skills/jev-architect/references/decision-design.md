# Decision design

## Question pack

For every proposed Jev decision, specify:

| Field | Required content |
| --- | --- |
| Decision | One named property, not a bundle of tasks. |
| State | Only the current information needed to judge it. |
| Primitive | Noul, Choice, or Score. |
| Answer space | Complete, bounded options or rubric. Include abstain, other, or missing-data handling where needed. |
| Criteria | Plain distinction between answers. |
| Consumer | The code path that uses the answer. |
| Threshold | Risk-matched confidence or score rule kept in code. |
| Fallback | Human review, existing LLM, deterministic default, retry, or no action. |
| Outcome | What later event will show whether it was correct. |

## Composition rules

- Keep independent questions about the same state together where the interface supports it.
- Use code to combine answers, compute values, enforce policy, and stage dependent decisions.
- Do not give the model an open instruction such as “analyze this and decide what to do.” Decompose it into the decisions code needs.
- Do not force a Choice when several candidates may be useful. Score or independently test candidates when the product needs a set.
- Keep thresholds, weights, and business rules out of the model prompt so they remain inspectable and versioned.

## Risk controls

Choose a threshold based on the action, not a universal number:

| Action | Typical posture |
| --- | --- |
| Rank for a human | Lower threshold can be acceptable. |
| Route a reversible task | Use confidence with monitoring and a fallback queue. |
| Send externally or mutate important data | Require stringent threshold plus deterministic guardrails or approval. |
| Irreversible, high-impact action | Do not delegate without independent verification and explicit authorization. |

Confidence is a prediction, not a warranty. Log the question version, state version, answer, confidence, action, fallback, and eventual outcome so calibration can be checked.
