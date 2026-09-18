# LLM Skills

A curated collection of reusable workflow skills for LLM coding agents.

These skills cover evidence-based model selection, long-running work, project memory, context management, and clear communication. They are designed to improve engineering judgment and verification—not replace them.

## Skills

| Skill | Purpose | Invocation |
|---|---|---|
| `advisor` | Consult another model when benchmark evidence justifies the cost | `$advisor` |
| `brain` | Preserve meaningful project state across sessions using Letta | `$brain` |
| `horizon` | Preserve objectives, evidence, and next actions during long-running work | `$horizon` |
| `plain-english` | Add a simple recap to the final response | `$plain-english` |

## Design principles

- Prefer one coherent root agent when delegation adds no value.
- Keep delegated context focused and minimal.
- Use explicit workflows for expensive or high-impact operations.
- Preserve human ownership of decisions, verification, and final integration.
- Use progressive disclosure instead of oversized instruction files.
- Never commit secrets, credentials, private paths, or personal configuration.

## Disclaimer

This is a personal collection of LLM workflow skills. It is not an official repository, and the skills may require adaptation as LLM capabilities evolve.