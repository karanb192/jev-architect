# Decision discovery

Map the workflow before proposing a model call. A decision loop has five parts:

```text
state arrives → semantic judgment → threshold or policy → action → outcome
```

## Inventory candidates

For a new product, start with the person and the unmet need. Ask only what changes the recommendation, such as the current workaround, available context, acceptable mistakes, budget, and response time. Offer a few distinct directions after clarification. Each should name the useful behavior, Jev's specific judgment, what ordinary code or another model does, and the smallest test of user value. Do not assume the user has software already.

Look for decisions in these places:

| Boundary | Typical question | First check |
| --- | --- | --- |
| Before an action | Is this safe enough to run? | Can an exact allowlist decide it? |
| Routing | Which queue, tool, model, or owner should handle this? | Are the choices bounded? |
| Filtering | Is this relevant, suspicious, duplicate, or worth retaining? | Is the label definition stable? |
| Ranking | Which candidates are useful? | Can candidates be scored independently? |
| Verification | Did the task meet the stated condition? | Is there an eventual ground truth? |
| Escalation | Does this case need more context or a person's judgment? | Can code use existing evidence and uncertainty to route it? |

Rank candidates by user value, available evidence, error consequences, latency needs, all-in cost, and integration effort. Keep seconds and money separate rather than adding them into a single value formula. For cost estimates, state the time period and workload. Count Jev calls plus downstream calls on each branch, retries, review, and maintenance; do not count a fallback as a call avoided. Use scenarios when usage or coverage is unknown.

For an existing workflow, compare with the actual baseline. For a new product, compare with the simplest way to serve that need, including a manual prototype. The first test may be whether anyone wants the behavior, before benchmarking models.

## Reject bad fits early

Use code, retrieval, a generative model, or a human instead when:

- an exact rule, calculation, permission check, or lookup gives the answer;
- the task needs prose, code, broad research, planning, or multi-step reasoning;
- the answer space is not bounded;
- a wrong action is irreversible and no sufficient verification or approval exists;
- the call is rare and has neither critical-path latency value nor meaningful risk reduction.

## Find newly feasible loops

Do not only hunt for LLM replacements. Ask: “If semantic judgment were low-latency and inexpensive enough to run on every state change, what would this system start doing?”

Examples of the pattern, not promises of suitability:

- screen each proposed action before execution rather than reviewing the final run;
- select or discard each candidate memory instead of forcing one global winner;
- triage every incoming record before expensive analysis;
- update a product path during an interaction rather than after a batch completes.

Every new loop must pass the same error, threshold, fallback, and outcome tests. Scale multiplies mistakes as well as savings.
