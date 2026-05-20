---
name: repo-memory
description: >-
  Maintain lightweight per-repo memory without making memory always active. Use
  when updating a runbook, theory, learnings, durable project facts, or when the
  user asks what should be remembered for future sessions. Distinct from seance
  or qmd search: this curates memory artifacts; search tools retrieve history.
argument-hint: "[runbook|theory|learning|audit|recall] [note or question]"
arguments:
  - request
license: MIT
effort: low
allowed-tools: Read Write Edit Bash Glob Grep
---

# Repo Memory

Memory is context, not a workflow tax. Do not load or rewrite memory files unless the user asks or the current work produced a durable fact worth preserving.

## Files

Prefer repo-local files under `.claude/memory/`:

- `runbook.md`: commands, setup, gotchas, stable operational facts.
- `theory.md`: current problem thesis and strategy, rewritten holistically when useful.
- `learnings.md`: durable lessons from sessions, failures, and reviews.

Stable agent instructions still belong in `CLAUDE.md` or `AGENTS.md`.

## Modes

### `runbook`

Add commands, environment details, setup steps, and operational gotchas that future agents should reuse.

### `theory`

Capture why the current approach exists and how evidence changed the strategy. Rewrite, do not append, when the theory changes.

### `learning`

Record reusable lessons from a mistake, review finding, or repeated pattern. Keep each learning short and general enough to transfer.

### `audit`

Read current memory files and remove stale, duplicate, or overly specific notes. Do not delete uncertain notes without saying why.

### `recall`

If the answer is in memory files, read them. If the user asks for session history or transcript search, route to `seance` or `qmd` instead of duplicating search behavior.

## Guardrails

- Do not store secrets, tokens, private session material, or raw logs.
- Do not append chronology. Curate concise facts.
- Do not create all files by default; create lazily when there is something useful to save.
