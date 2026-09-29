---
name: agent-changelog
description: Maintain project changelog entries only when the user explicitly tags or names this skill and asks for changelog work.
---

# Agent Changelog Skill

## Triggering

- Do not use this skill automatically for ordinary file or behavior changes.
- Use this skill only when the current user request explicitly tags or names `agent-changelog`.

## When to update

- Update `changelog.md` only when explicitly requested and files or behavior change.
- Skip changelog updates for read-only analysis.

## Entry format

- Insert the newest entry directly under `# changelog`.
- Use an H2 header: `YYYY-MM-DD HH:MM — Topic`.
- Follow with bullet points describing concrete steps and the touched files.

## Scope rules

- If a sub-project has its own changelog, use that instead of the repo root.
- Note noteworthy runtime/UX bugs and include the related file/line when fixed.
- Do not log plan details; planning is tracked separately.
