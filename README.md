# Jev Architect

![A systems architect maps a Jev decision workflow from messy state to automated action or human review.](assets/jev-architect-illustration-v2.png)

Most Jev discussions start at the API. The harder question comes first: where does a fast, bounded semantic decision belong in a system?

Jev Architect helps an agent answer that question. It can explain Jev at the user’s level, inspect a workflow or codebase, check current product documentation, separate exact rules from fuzzy decisions, and design a small measured rollout.

It can recommend code, retrieval, a generative model, human review, or Jev. A Jev call is only useful when the decision, failure path, and economics support it.

The skill is built around [TypeSafe Jev](https://typesafe.ai/) and its Choice, Noul, and Score decision primitives.

## What it produces

- A plain-language explanation of Jev tied to the user’s system.
- A ranked map of candidate decision loops, including places Jev does not fit.
- A decision design with state, answer space, threshold, fallback, and action owner.
- A fair experiment that measures quality, coverage, calibration, latency, cost, and review burden.
- A documented boundary between verified current capabilities, assumptions, and unknowns.

## Install

This repository uses the portable Agent Skills layout. Install it with your preferred skill manager or clone it into your agent’s skill directory.

For the skills.sh CLI, install the `jev-architect` skill from the published repository:

```bash
npx skills add karanb192/jev-architect --skill jev-architect
```

### Claude Code

In Claude Code, add the marketplace, then install the plugin:

```text
/plugin marketplace add karanb192/jev-architect
/plugin install jev-architect@jev-architect-marketplace
```

If Claude Code asks to activate plugin changes, run `/reload-plugins`. Then invoke `/jev-architect:jev-architect` or ask Claude to use Jev Architect for the task.

Codex can use the included plugin manifest or the portable skill folder.

## Try it

```text
Use $jev-architect to find where Jev belongs in this support workflow. Check the current documentation for the tools we use, rank the opportunities, and design a first experiment.
```

```text
Use $jev-architect to explain Jev for a product manager, then show one decision loop we could test in our app.
```

```text
Use $jev-architect to audit this Jev design. Check whether the question, answer space, confidence threshold, and fallback are safe.
```

## What it will not do

- Treat Jev as a replacement for every LLM call.
- Promise speed, cost, calibration, or quality without measuring the target workflow.
- Assume an integration is current without checking official documentation and the installed system.
- Put private paths, traces, hidden instructions, or credentials in a shareable report.

## Repository layout

```text
skills/jev-architect/    Portable Agent Skill source
.claude-plugin/          Claude Code plugin and marketplace metadata
.codex-plugin/           Codex plugin metadata
```

## License

[MIT](LICENSE)
