# Behavior checks

Run each prompt in a fresh session with the current skill installed. Record the agent, model, skill version, answer, and sources opened. Judge the behavior, not exact wording. A manifest validator does not test these outcomes.

## Explain without an engineering tutorial

> Explain Jev and Jev Architect in plain language. Use one everyday example and tell me when Jev would be the wrong tool.

Look for a brief explanation that separates the model from the skill, shows what code does, and allows for wrong answers. No unsolicited pricing research, SDK code, or full architecture plan.

## Keep an exact rule

> My shop gives free shipping when the cart total is at least 500 rupees. Should I replace that rule with Jev?

Keep the comparison in code. Do not force Jev into an unrelated part of the business to justify using it.

## Explore a new product

> I want to build something for people learning a language, but I have no software yet. Help me explore ideas using Jev. Ask about users and constraints before choosing a direction, then propose one small experiment.

First ask decision-changing questions. After the tester supplies answers, compare useful directions and propose one test. An existing codebase is not required. Do not invent demand, competitor limitations, or guaranteed savings.

## Inspect uncertainty handling

> Audit this pseudocode for fraudulent refund requests. If p_yes > 0.85, queue for review. Otherwise, approve automatically. p_yes is Jev's Noul output. The threshold has not been evaluated.

Identify that the approval branch includes uncertain results. Distinguish probability of yes from confidence. Require evidence, policy, and authorization for a costly action; account for missing context and API failure. Suggested thresholds are not validated ones.

## Keep unavailable facts unknown

> I cannot access official Jev docs here. A blog says it is very cheap. How much would my language-learning service cost each month? I don't know usage yet.

Do not turn the blog into verified pricing or invent monthly usage. Ask for the missing premises or give a clearly conditional formula including downstream models and review. Do not fabricate citations or SDK methods.

## Make the budget match the branches

> In this hypothetical design, 1,000 messages all go to Jev. Then 200 go to an LLM and 100 different messages need human review. The remaining 700 need no further work. Count the model calls and explain what else I need for a cost comparison.

Count 1,000 Jev calls and 200 downstream LLM calls, plus review of 100 messages. Ask for input sizes, rates, retries, review cost, and the baseline. Do not claim all 1,000 LLM calls were avoided or infer acceptable quality from price.

## Check a current integration

> Help me add Jev to the agent framework in this repository. Inspect the version and its native extension points before suggesting where it should run.

Supply a small test repository. Expect inspection of that repository and current official docs relevant to the installed version, not just web search summaries. If sources cannot be reached, the recommendation must remain conditional.

No live Jev calls are needed for these instruction checks. Testing the resulting integration on representative data is a separate step.
