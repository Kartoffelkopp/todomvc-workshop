---
name: agent-ledger
description: Maintain a compaction-safe continuity ledger (CONTINUITY.md) for session state that survives context limits. Use when working on long-running tasks, multi-step workflows, or any situation where session state needs to persist across context boundaries.
---

# Agent Ledger (Compaction-Safe Continuity)

Maintain a single Continuity Ledger for this workspace in `CONTINUITY.md`. The ledger is the canonical session briefing designed to survive context compaction; do not rely on earlier chat text unless it's reflected in the ledger.

## How it works

- At the start of every assistant turn: read `CONTINUITY.md`, update it to reflect the latest goal/constraints/decisions/state, then proceed with the work.
- Update `CONTINUITY.md` again whenever any of these change: goal, constraints/assumptions, key decisions, progress state (Done/Now/Next), or important tool outcomes.
- Keep it short and stable: facts only, no transcripts. Prefer bullets. Mark uncertainty as `UNCONFIRMED` (never guess).
- Use `Owner/Lock` to avoid collisions: set Owner to the active instance and Lock to a timestamp while editing; clear Lock when idle.
- For multi-instance work, pick a short handle (random adjective-noun is fine) and keep a small per-handle section under `Handles`.
- In `Handles`, use `Handle: <id>` lines with 1-3 bullets (Now/Next/Notes); keep only active handles.
- If you notice missing recall or a compaction/summary event: refresh/rebuild the ledger from visible context, mark gaps `UNCONFIRMED`, ask up to 1–3 targeted questions, then continue.

## Task tracking vs the Ledger

- Short-term execution scaffolding (a small 3–7 step plan with pending/in_progress/completed) is for immediate task tracking.
- `CONTINUITY.md` is for long-running continuity across compaction (the "what/why/current state"), not a step-by-step task list.
- Keep them consistent: when the plan or state changes, update the ledger at the intent/progress level (not every micro-step).

## In replies

- Begin with a brief "Ledger Snapshot" (Goal + Now/Next + Open Questions). Print the full ledger only when it materially changes or when the user asks.

## `CONTINUITY.md` format (keep headings)

- Goal (incl. success criteria):
- Constraints/Assumptions:
- Key decisions:
- State:
- Owner/Lock:
- Handles:
- Done:
- Now:
- Next:
- Open questions (UNCONFIRMED if needed):
- Working set (files/ids/commands):
