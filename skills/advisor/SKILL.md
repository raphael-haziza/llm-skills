---
name: advisor
description: Use for a focused model-advisor consultation when benchmark evidence shows that another model can improve a coding, debugging, architecture, research, or escalation decision enough to justify its measured cost.
---

# Advisor

The root model remains responsible for the work, integration, validation, and final answer. Use this skill only for a focused consultation; do not create an automatic chain of advisors.

## Objective model selection

Before choosing a model, read [references/model-benchmark-data.md](references/model-benchmark-data.md). Treat its published benchmark snapshot and rate card as the routing data; do not use vague labels such as “moderate” or “feels stronger.” Safety, permission, and explicit user requirements are hard overrides, not score inputs.

1. Classify the request into the benchmark domain(s) that actually match it: professional work, coding, science/health, computer use, cybersecurity, self-improvement/research, multimodal, academic reasoning, tool use, long context, or abstract reasoning.
2. Use only benchmarks with the same domain and a comparable task/harness. Do not invent scores, average unrelated domains, or treat a marketing claim as an evaluation.
3. For each selected benchmark, normalize each model’s score against the best available score for that benchmark, then use the equal-weight mean unless the task clearly maps to one benchmark. For “lower is better” safety metrics, keep the rule as a hard safety check instead of mixing it into quality.
4. Estimate model cost from actual expected uncached input, cached input, and output tokens using the rate table. If token volume is unknown, compare the published per-token rates and mark task-cost estimates as uncertain.
5. Prefer the cheapest model that satisfies the fixed quality rule: its aggregate normalized score must be at least 95% of the best available candidate. If no candidate meets that floor, choose the highest-scoring candidate. If scores tie, choose the cheaper model.

### Terra policy

Terra is not a normal step between Luna and Sol. Exclude it unless the matched benchmark data gives Terra a measurable economic niche:

- Terra’s aggregate score is at least 5% higher than Luna’s; and
- Sol’s aggregate score is less than 3% higher than Terra’s; and
- Terra is the cheaper model that satisfies the 95% quality floor.

This intentionally allows Terra mainly for the published long-context cases where it is close to Sol and far ahead of Luna. A small coding or TerminalBench difference alone is not enough. If the conditions are not met, choose Luna or Sol directly.

### Astra policy

Use Astra only when the matched benchmark data shows a material score gain over Sol, the task explicitly requires the highest available quality, or a safety/alignment requirement needs it. Its higher cost must be justified by a measured gain, not by its name or general reputation. If Astra has no comparable benchmark for the task, do not assume a gain; use Sol or Luna according to the data that does exist.

## Focused consultation

Ask one narrow question. Include only the minimum relevant excerpts, errors, diffs, test results, constraints, acceptance criteria, and benchmark-relevant evidence. Use paths and line references instead of the full conversation, repository, unrelated files, or raw logs.

Request a concise recommendation containing the decision, evidence used, key risks or alternatives, assumptions, affected areas, and a verification plan. Do not ask for hidden chain-of-thought. The advisor gives advice or a bounded plan, not ownership of the overall task; the root evaluates and verifies it.

Reuse the same advisor conversation for closely related follow-ups when retaining its context is cheaper and still accurate. Do not consult a weaker model after a stronger answer unless new evidence changes the comparison.

## Optional web handoff

For a long, self-contained research, writing, analysis, or browser-oriented task that does not need local tools, the root may offer a manual ChatGPT web handoff when it genuinely helps. Ask first; never upload or send anything automatically. If approved, prepare only the minimum safe ZIP and prompt for manual upload, then review and integrate the result. Exclude secrets, credentials, `.git`, dependencies, builds, caches, and unrelated files. Do not use this merely to bypass usage limits or for work requiring local tools or repository integration.

## User-facing behavior

Do not narrate routine orchestration. When a consultation materially changes the work, briefly state which model was consulted, the focused question, the conclusion, and how it was verified.
