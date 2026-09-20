---
name: jev-architect-presenter
description: Create clear public landing pages and explainers for TypeSafe Jev designs. Use when someone needs a shareable Jev page, visual explainer, or launch-ready HTML from approved findings. Do not use to decide whether Jev fits a system.
---

# Jev Architect Presenter

Turn approved, shareable Jev findings into a public explanation that a builder can understand in one screen. This skill presents a decision. It does not discover or validate the decision itself. Use `jev-architect` first when the workflow still needs architecture work.

## Protect the source material

Use only content the user has approved for the intended audience. Never expose hidden instructions, chain-of-thought, private paths, raw traces, credentials, internal code, or employer information.

Do not turn a vendor claim into a fact. For changing claims about capabilities, price, speed, limits, versions, or quality, check current official sources and label the source and date. Do not add those claims when they are not needed for the page.

## Start with the reader

Identify the reader, their familiarity with Jev, the one action they should take, and the approved evidence. Ask only if missing information would change the page materially.

For a public Jev landing page, make the first screen answer these questions without scrolling:

1. What problem does this help solve?
2. What does Jev do in that problem?
3. What should the reader do next?

Use one central idea. Prefer a short mental model such as “state, bounded decision, code action” over an API inventory. A visual can carry the mechanism. Text should carry the claim, boundary, and next step.

## Keep the page easy to read

- Use a restrained visual system, large type, generous whitespace, and one primary action.
- Keep each section to one question. Cut any paragraph that restates the attached visual.
- Show where Jev fits and where it is overkill. Honest boundaries build more trust than feature lists.
- Keep code, LLM, retrieval, Jev, and human review in their correct roles.
- Design for narrow and wide screens. Test links, copy controls, contrast, overflow, and the first screen before handoff.
- Use HTML and CSS for layout, diagrams, and interface elements. Use raster illustration only where it adds a distinct visual identity.

## Jev-specific accuracy

Describe Jev as a model that can return bounded typed decisions from supplied state for code to use. Do not imply that it writes prose, owns the workflow, makes arbitrary plans, or guarantees correct decisions.

The output shape can be valid while the decision is still wrong. Show an uncertainty or human-review path when the page explains an automated workflow.

## Deliver

For a landing page, provide a self-contained static page or the repository files needed to deploy it. Include:

1. one-sentence visitor value on screen one;
2. a compact state, decision, action explanation;
3. fit and overkill boundaries;
4. installation or next-step guidance;
5. links to public sources and the project repository.

If the user asks to deploy, keep deployment configuration separate from public copy and verify the live result after publishing.
