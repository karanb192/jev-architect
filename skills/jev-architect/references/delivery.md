# Delivery contract

## Explanation mode

Adapt the explanation to familiarity.

| Familiarity | Start with | Stop before |
| --- | --- | --- |
| New to Jev | A familiar workflow and the contrast with code and an LLM. | API details or vendor benchmark claims. |
| AI builder | Decision boundaries, loops, and composition. | A generic tutorial with no system connection. |
| Evaluator | Risks, current capabilities, measurement, and first experiment. | Unsupported ROI claims. |
| Team | Shared vocabulary, one workflow diagram, and concrete next step. | A polished pitch with no caveats. |

A useful plain explanation is “Jev helps software answer questions where the possible answers are defined in advance, such as whether a message needs a reply. Your code decides what to do with the answer.” Explain Jev Architect separately as the skill guiding the user's coding agent. A short explanation should not turn into an unsolicited engineering tutorial or pricing report.

## Architecture pack

Use this order unless the user asks for a narrower deliverable:

1. **Current context.** Verified capabilities, assumptions, unknowns, and date checked.
2. **Decision inventory.** Candidate loops with code, LLM, Jev, and human placement.
3. **Recommendation.** The first slice, expected value hypothesis, and why alternatives lost.
4. **Decision design.** State, primitive, answer space, threshold, fallback, and action owner.
5. **Evaluation.** Quality, coverage, calibration, p50/p95 latency, all-in cost, and review burden.
6. **Stop condition.** The result that would make the team keep the current approach.

For early ideation, lead with the proposed user benefit and first test, not a long capabilities table. If the user asks for one small experiment, keep it to one. Link supporting detail rather than overwhelming the next action.

## Make the experiment test the recommendation

- Define correct outcomes and the cost of false positives and false negatives. Use representative cases, ambiguous cases, and service failures. If people disagree on labels, resolve the task definition before treating a score as ground truth.
- Compare the full proposed workflow with a sensible baseline on the same inputs and outcome criteria. Set thresholds on development data, then evaluate separately. Avoid tuning and claiming success on the same cases.
- Measure quality on actions taken, how many cases are handled automatically, and important cases missed or deferred. Track fallback and review load, not just model accuracy. Choose acceptance criteria from user requirements; label suggested targets as provisional.
- Measure end-to-end latency, including fallback paths and retries. A faster individual call does not guarantee a faster workflow. Report relevant latency percentiles rather than multiplying parallel call savings into elapsed time.
- For cost, include actual calls, input size, branches, retries, downstream models, and review. Monthly cost requires a stated monthly workload. Keep estimates conditional on unmeasured usage and fallback rates.
- For a new capability, test whether users find it useful as well as whether Jev can supply the judgment. Cheaper judgments do not prove demand or that competing approaches cannot work.

Before handoff, trace the same cases through prose, diagrams, code, and cost assumptions. If uncertainty means no action in the design, do not count it as an LLM fallback in the budget. State which tests were executed and which are only proposed. Keep the current approach if the quality floor, acceptable review burden, or practical benefit is not met.

## Shareable output boundary

When producing Markdown, HTML, slides, or a video storyboard for another person, include only material the user has approved for that audience.

Never expose internal instructions, hidden reasoning, credentials, private local paths, raw traces, or private code by default. Summarize sensitive evidence into an approved finding. Link public sources directly and label vendor claims as vendor claims.

HTML is optional. Use it when a visual review artifact makes a decision easier to inspect. The architecture pack is the source of truth; a renderer is only a presentation layer.
