# Delivery contract

## Explanation mode

Adapt the explanation to familiarity.

| Familiarity | Start with | Stop before |
| --- | --- | --- |
| New to Jev | A familiar workflow and the contrast with code and an LLM. | API details or vendor benchmark claims. |
| AI builder | Decision boundaries, loops, and composition. | A generic tutorial with no system connection. |
| Evaluator | Risks, current capabilities, measurement, and first experiment. | Unsupported ROI claims. |
| Team | Shared vocabulary, one workflow diagram, and concrete next step. | A polished pitch with no caveats. |

A useful concise explanation is: “Jev lets code make a bounded semantic decision from messy state, then act on the result. It does not write the response or own the workflow.”

## Architecture pack

Use this order unless the user asks for a narrower deliverable:

1. **Current context.** Verified capabilities, assumptions, unknowns, and date checked.
2. **Decision inventory.** Candidate loops with code, LLM, Jev, and human placement.
3. **Recommendation.** The first slice, expected value hypothesis, and why alternatives lost.
4. **Decision design.** State, primitive, answer space, threshold, fallback, and action owner.
5. **Evaluation.** Quality, coverage, calibration, p50/p95 latency, all-in cost, and review burden.
6. **Stop condition.** The result that would make the team keep the current approach.

## Shareable output boundary

When producing Markdown, HTML, slides, or a video storyboard for another person, include only material the user has approved for that audience.

Never expose internal instructions, hidden reasoning, credentials, private local paths, raw traces, or private code by default. Summarize sensitive evidence into an approved finding. Link public sources directly and label vendor claims as vendor claims.

HTML is optional. Use it when a visual review artifact makes a decision easier to inspect. The architecture pack is the source of truth; a renderer is only a presentation layer.
