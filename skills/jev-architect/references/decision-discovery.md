# Decision discovery

Map the workflow before proposing a model call. A decision loop has five parts:

```text
state arrives → semantic judgment → threshold or policy → action → outcome
```

## Inventory candidates

Look for decisions in these places:

| Boundary | Typical question | First check |
| --- | --- | --- |
| Before an action | Is this safe enough to run? | Can an exact allowlist decide it? |
| Routing | Which queue, tool, model, or owner should handle this? | Are the choices bounded? |
| Filtering | Is this relevant, suspicious, duplicate, or worth retaining? | Is the label definition stable? |
| Ranking | Which candidates are useful? | Can candidates be scored independently? |
| Verification | Did the task meet the stated condition? | Is there an eventual ground truth? |
| Escalation | Is confidence high enough to proceed? | Is the fallback safe and affordable? |

Rank each candidate by its expected value, not novelty:

```text
value hypothesis = frequency × per-call cost or latency avoided × usable coverage
                 + value of the newly possible capability
                 − error cost − review cost − integration cost
```

This is an estimation tool, not a claim of savings. Record the numbers and assumptions that support it.

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
