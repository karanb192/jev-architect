# Current context protocol

Use this protocol before relying on current capabilities, economics, or an integration. Basic conceptual explanations do not need live research.

## Start at primary sources

Use the [TypeSafe documentation index](https://docs.typesafe.ai/llms.txt), then open only relevant pages. Direct starting points include [primitives](https://docs.typesafe.ai/primitives), [confidence](https://docs.typesafe.ai/confidence), [building guidance](https://docs.typesafe.ai/concepts/how-to-build-with-system-one), [use cases](https://docs.typesafe.ai/concepts/use-case-map), and the [API reference](https://docs.typesafe.ai/api). Follow the index to the chosen SDK, model information, or a relevant cookbook. If Markdown fails, try the normal page, and vice versa.

Use the target platform's official docs and release notes for integration points. Do not substitute a generic search for opening the source that supports the claim. Cookbook thresholds and results are examples, not universal defaults.

## What to establish

| Fact | First source | Why it changes the design |
| --- | --- | --- |
| Product and version | Local dependency/configuration, then official docs | Features and extension points drift. |
| Deployment surface | User statement, repository, runtime config | Local, hosted, CI, browser, and server surfaces have different controls. |
| Agent action surface | Tool definitions, trace, or official API reference | The action boundary sets the risk and fallback. |
| Native extension points | Official docs, release notes, changelog | A native lifecycle or routing feature can replace a fragile workaround. |
| Current Jev interface and limits | Official TypeSafe docs and API reference | Do not freeze volatile pricing, limits, or feature claims in the skill. |

Treat official documentation, changelogs, release notes, and installed code as primary sources. Community accounts are leads, not verification of current product behavior. Official performance claims still need a matched workload test.

## Question discipline

For an existing system, inspect relevant supplied materials before asking for facts they already contain. For a new idea, first ask who it serves, what problem matters, and what constraints apply. Do not research an imagined stack before the user chooses a direction.

High-value questions include:

- What action can the system take after this decision?
- What is the cost of a false positive and a false negative?
- How often does this decision happen, and which calls are serial?
- Is the target environment pinned to a version or expected to track latest?
- Which historical outcomes can label success?

Avoid questionnaires. If a safe baseline design is possible, state the assumption and show how the answer would change it.

## Evidence boundary

Every recommendation should distinguish:

- **Documented.** Seen in current official documentation. Include date and link; this does not establish performance on the user's data.
- **Measured.** Observed in an actual test. Include workload, baseline, model/version, method, date, and result.
- **Assumed.** Reasonable temporary premise that needs user confirmation.
- **Unknown.** Information that could materially change the recommendation but was not available.

If primary sources are unavailable, say which premise remains unverified. Continue with a conditional design, symbolic cost calculation, or a question for the user. Do not label a secondary-source table “verified,” or turn an assumed price into a firm savings claim later. Competitive or demand claims need their own evidence; otherwise frame them as hypotheses to test.
