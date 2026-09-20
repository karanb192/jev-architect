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
| Threshold | Name the response field, meaning, direction, and risk-matched rule kept in code. Mark untested values as provisional. |
| Fallback | Human review, existing LLM, deterministic default, retry, or no action. |
| Outcome | What later event will show whether it was correct. |

## Composition rules

- Keep independent questions about the same state together where the interface supports it. They cannot consume each other's answers. Use another stage when an answer is needed to fetch context or construct the next question.
- Use code to combine answers, compute values, enforce policy, and stage dependent decisions.
- Do not give the model an open instruction such as “analyze this and decide what to do.” Decompose it into the decisions code needs.
- Do not force a Choice when several candidates may be useful. Score or independently test candidates when the product needs a set.
- Keep thresholds, weights, and business rules out of the model prompt so they remain inspectable and versioned.

## Interpret the answer before choosing an action

Read the current primitive and confidence docs before implementing. Noul estimates the probability of yes, not confidence in a separately returned boolean. A value near zero supports no; a value near the middle is uncertain. Choice probabilities compare options. Score is a probability-weighted position on descriptive levels. Choice and Score confidence describes concentration of the distribution, not verified correctness.

Give Score levels independent, concrete descriptions. Use an explicit no-match option for Choice where needed; code must also check missing required inputs. A model cannot choose an omitted candidate or compensate for absent evidence.

Walk through a supported positive, a supported negative, an uncertain answer, missing/stale state, and an API failure. Every case needs an intentional outcome. Do not let `else` mean approval unless all conditions for approval were positively established. For high-impact actions, model output alone cannot replace permission checks or independent verification.

Use low-stakes examples for basic explanations. If showing control flow without checking the SDK, label it pseudocode and avoid plausible-looking invented API methods. Do not use unexplained numerical thresholds as production defaults.

## Risk controls

Choose a threshold based on the action, not a universal number:

| Action | Typical posture |
| --- | --- |
| Rank for a human | Lower threshold can be acceptable. |
| Route a reversible task | Use confidence with monitoring and a fallback queue. |
| Send externally or mutate important data | Require stringent threshold plus deterministic guardrails or approval. |
| Irreversible, high-impact action | Do not delegate without independent verification and explicit authorization. |

Define the fallback for the actual harm. Silence may be acceptable for an optional suggestion but not for a critical alert. A timeout is not a negative classification. When needed, preserve the current behavior or queue for review rather than inventing a permissive default.

Log model and question versions, a privacy-safe state reference, answer distribution, applicable confidence, action, fallback, and eventual outcome. Respect data access and retention constraints; raw private inputs need not be logged. Use these records to evaluate errors and calibration, not merely output validity.
