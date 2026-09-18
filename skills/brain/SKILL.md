---
name: brain
description: Use the local Letta Context Repository to resume projects and persist meaningful project state across Codex sessions.
---

# Letta project memory

Use the `letta_memory` MCP tools when a user mentions an existing project, asks to continue prior work, asks what remains, or makes a durable project change.

## Resume

1. Call `letta_memory.resolve_project` with the full user message and the current working directory.
2. If it selects a project, use the returned current state immediately. Do not load history for ordinary resume questions.
3. For “what’s left?” / “il reste quoi ?”, answer from the selected project’s `TODO` section. It is the source of truth; do not reconstruct TODO from old conversation.
4. Call `letta_memory.search_memory` only when the user asks for older activity or the current state does not answer a specific historical question.
5. If resolution is ambiguous, ask one concise clarifying question. If no project exists and the user confirms a new project, call `letta_memory.create_project`.

Always pass the actual current working directory to resolution. Treat repository/path matches as stronger evidence than a loose word match. Project aliases may be English or French.

## Persist

Call `letta_memory.update_project` after a meaningful change: completed work, a new or removed task, a decision, a blocker, a changed focus, or an important technical discovery. Send only the changed compact fields and a one-line `activity`; do not save conversational noise, raw logs, secrets, API keys, credentials, or tokens.

At the end of meaningful work, call `letta_memory.consolidate_project` so the current status, TODO, decisions, blockers, next actions, and recent activity are sufficient for a fresh session. The tool commits the memory repository; do not commit unrelated files.

## Scope

The memory repository is local-first and Git-backed. Keep global context small. Project files are current state; `history/` is an optional record of meaningful older activity. Never put the memory contents in this skill.
