# Jev Architect

An agent skill to help you decide what to build with Jev, where it could improve existing software, and what to test before committing to it.

[Explore the examples](https://jev-architect.karanbansal.in/) · [Install](#install) · [Try a prompt](#try-it)

![A systems architect maps a Jev decision workflow from messy state to automated action or human review.](assets/jev-architect-illustration-v2.png)

[Jev](https://typesafe.ai/) answers questions with defined possible outcomes. For example, it could judge whether a message needs a reply. Your code could then add that message to a reply queue, with a person deciding what to say.

Jev Architect guides your coding agent through choosing and testing those uses. Bring a problem, an idea, or a codebase. You don't need existing software to begin.

- **Explore a new idea.** What useful tool could you build if checking every message or event were affordable? Start with who it helps and test that premise.
- **Improve an existing workflow.** Compare Jev with the approach you use today, including mistakes, waiting time, cost, and review work.

The answer can be “keep it in code.” A free-shipping rule based on cart total needs an exact comparison, not a model call.

## What to expect

Ask for an explanation and get one at your level. Ask for ideas and the agent first clarifies the users, problem, and constraints. For a concrete design, it works out the context Jev needs, the question to ask, and what code should do when the answer is uncertain or the request fails.

The next step is a small experiment with a baseline and a reason to stop if Jev isn't useful. Suggested designs are hypotheses, not evidence of speed, savings, or accuracy.

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

If Claude Code asks to activate plugin changes, run `/reload-plugins`. Then invoke `/jev-architect:jev-architect` with your request or ask Claude to use Jev Architect.

To update an existing installation, run these commands in your terminal, then start a fresh Claude Code session. Use the scope you originally installed in if it wasn't the default user scope.

```bash
claude plugin marketplace update jev-architect-marketplace
claude plugin update jev-architect@jev-architect-marketplace
```

See [Claude Code's plugin documentation](https://code.claude.com/docs/en/discover-plugins) for installation scopes and reload behavior.

Codex can use the included plugin manifest or the portable skill folder.

## Try it

Start with a problem, even if you haven't built anything yet.

```text
Use Jev Architect. I often miss messages that need a reply. Help me explore tools I could build to solve this. Ask how I handle messages today, suggest a few ideas, and explain where Jev could help. Pick one small test before I start building.
```

Or compare it with something you already use.

```text
Use Jev Architect. I use a language model to flag messages that need a reply. Could Jev reduce the time or cost without missing important requests? Ask about my setup and help me design a comparison.
```

For a first explanation or a design review, try either of these.

```text
Use Jev Architect to explain Jev in plain language, with one everyday example and one case where I should not use it.
```

```text
Use Jev Architect to audit this design. Check the question, possible answers, thresholds, and what happens on uncertainty, missing context, or an API failure.
```

### Why does it sometimes browse?

Basic explanations use the skill's built-in concepts. Current prices, API details, and recommendations for a named tool require checking official documentation. If those sources aren't available, the recommendation should stay conditional. A source stating a capability is not proof that it works well on your data.

## What it will not do

- Treat Jev as a replacement for every LLM call.
- Promise speed, cost, calibration, or quality without measuring the target workflow.
- Assume an integration is current without checking official documentation and the installed system.
- Treat confidence as permission to act, or valid output as proof of a correct decision.
- Put private paths, traces, hidden instructions, or credentials in a shareable report.

This repository provides instructions for your agent. Installing it does not connect to Jev or run a benchmark. Building an integration requires separate API access and evaluation. This is an independent project, not an official TypeSafe skill.

## Repository layout

```text
skills/jev-architect/    Portable Agent Skill source
.claude-plugin/          Claude Code plugin and marketplace metadata
.codex-plugin/           Codex plugin metadata
tests/behavior.md        Prompts and expected behavior for manual checks
```

Use the [behavior checks](tests/behavior.md) to test the skill in your agent. They test the advice it gives, not Jev's model performance.

## License

[MIT](LICENSE)
