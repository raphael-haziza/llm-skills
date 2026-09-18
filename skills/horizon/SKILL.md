---
name: horizon
description: Preserve the objective, evidence, state, and next actions across long-running Codex work and context compaction. Use for multi-step, tool-heavy, research, reverse-engineering, or multi-hour tasks; skip short tasks.
---

# Horizon

Use this skill for a long-running objective, or when the user explicitly invokes `$horizon`. It improves continuity around compaction; it does not control Codex’s internal compaction mechanism or inspect its opaque compacted items.

## Establish one authoritative state

At the beginning, define a compact Horizon Contract:

- **Goal:** the user’s actual outcome, preserved in their terms.
- **Definition of done:** observable acceptance checks and required evidence.
- **Non-goals:** tempting work that is outside the request.
- **Current facts:** verified findings only, with paths, commands, or artifact references.
- **Hypotheses:** unresolved explanations, each separated from facts and paired with a discriminating test.
- **State:** completed milestones, current position, blockers, external dependencies, and the next concrete action.

For genuinely long work, keep this in one concise, clearly named project state file or existing work log. Do not create a state file for a short task, and never use it as a substitute for the real project artifacts.

## Make every investigation cycle discriminating

Before a substantial probe, script, experiment, subagent request, or manual capture, record four things:

1. The exact unresolved question or hypothesis it addresses.
2. The evidence or artifact it will inspect.
3. The result that would support or reject the hypothesis.
4. The next decision that each result would cause.

Do not create another probe merely because the previous one was inconclusive. First explain why the next probe can distinguish the remaining possibilities. Keep an evidence ledger with `proven`, `disproven`, `unresolved`, and `invalid` states. An empty dump, failed command, malformed output, or unverified screenshot is `invalid`, not evidence.

For research or reverse engineering, maintain a claim/evidence/confidence/missing-test distinction. Prefer a new discriminating experiment over broad exploration when several explanations remain possible.

## Checkpoint before context pressure

After a major milestone and before a likely compaction, update the state with only what must survive:

```text
Goal / acceptance gate:
Verified since the previous checkpoint:
Current conclusion or hypothesis:
Evidence and artifact locations:
Completed work that must not be repeated:
Open questions and missing proof:
External dependency or user action required:
Next action and expected signal:
Stop or reassessment condition:
```

Preserve the original acceptance gate, important user decisions, constraints, failed approaches, and the exact next action. Replace raw logs, repeated explanations, and stale plans with short summaries and file or artifact references. Keep facts, hypotheses, and guesses visibly distinct.

## Resume after compaction or interruption

Before doing new work:

1. Re-read the Horizon Contract and the current state file if one exists.
2. Inspect the actual filesystem, artifacts, process state, and relevant tests; do not trust memory for completion status.
3. Reconcile the checkpoint with the current state. Mark stale assumptions instead of silently continuing them.
4. Restate the next acceptance-relevant action internally, then perform it rather than re-planning the entire task.

Do not repeat completed searches, installations, experiments, manual instructions, or tests unless their evidence is missing, invalidated, or the user changed the requirements. If a step depends on the user or an external process, prepare the exact next action, do useful independent work if available, and otherwise wait or surface the dependency—never burn turns repeating the same request.

## Control drift, delegation, and loops

Use one coherent root agent by default. If delegation is useful, keep an owner/question/result ledger, give each helper one bounded non-overlapping question, and do not start another helper for the same evidence gap until the previous result has been integrated. Reuse a focused helper when its retained context is cheaper than repeating it.

Detect drift explicitly:

- If the same action or plan produces the same result twice, stop repeating it and reassess the approach.
- If three consecutive checkpoints add no new verified evidence, pause autonomous continuation and surface the blocker or ask for a focused decision.
- If scratch code or temporary probes accumulate without changing the hypothesis set, stop adding tooling and consolidate or delete invalid artifacts when safe.
- If generated tests pass but the real acceptance path is unverified, do not call the task complete.
- Do not let subagent reviews, new internal tests, or cleanup findings replace the user’s original outcome.

## Completion

Before declaring success, compare the result with the original acceptance gate, run the most direct real-world verification available, and record what remains uncertain. A long duration is not evidence of progress, and a passing auxiliary test is not proof of the user-visible outcome.