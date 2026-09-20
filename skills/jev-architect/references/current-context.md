# Current context protocol

Use this protocol before recommending Jev inside a named product, agent, framework, SDK, runtime, or platform.

## What to establish

| Fact | First source | Why it changes the design |
| --- | --- | --- |
| Product and version | Local dependency/configuration, then official docs | Features and extension points drift. |
| Deployment surface | User statement, repository, runtime config | Local, hosted, CI, browser, and server surfaces have different controls. |
| Agent action surface | Tool definitions, trace, or official API reference | The action boundary sets the risk and fallback. |
| Native extension points | Official docs, release notes, changelog | A native lifecycle or routing feature can replace a fragile workaround. |
| Current Jev interface and limits | Official TypeSafe docs and API reference | Do not freeze volatile pricing, limits, or feature claims in the skill. |

Treat official documentation, changelogs, release notes, and installed code as primary sources. Community posts, tutorials, and repositories are secondary evidence.

## Question discipline

Research first. Ask only for information unavailable from the target materials and necessary to choose a design.

High-value questions include:

- What action can the system take after this decision?
- What is the cost of a false positive and a false negative?
- How often does this decision happen, and which calls are serial?
- Is the target environment pinned to a version or expected to track latest?
- Which historical outcomes can label success?

Avoid questionnaires. If a safe baseline design is possible, state the assumption and show how the answer would change it.

## Evidence boundary

Every recommendation should distinguish:

- **Verified.** Seen in current official documentation or the inspected system. Include date and link.
- **Assumed.** Reasonable temporary premise that needs user confirmation.
- **Unknown.** Information that could materially change the recommendation but was not available.

If web access is unavailable, say that current docs were not verified. Do not convert recollection into a claim.
