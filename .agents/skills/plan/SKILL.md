---
name: plan
disable-model-invocation: true
description: Generate and manage standalone or feature-grouped project plans in meta/plans (create/read/update/delete) and track perf todos in NextSprint.md. Use only when the user explicitly asks for a plan or plan file changes.
---

# Planning Skill

## Plan location

- Plans live in `meta/plans` in the project we're working on as markdown files (not tracked in git on purpose).
- When asked to create a plan, write it to `<project_root>/meta/plans`.
- Plan filename must start with current date in this format: <yyyy-mm-dd>-<name-plan>.md

## Feature-grouped plan hierarchy

- When the user requests feature-grouped plans, an umbrella plan with phase plans, or multiple
  plans for one feature, always create a dedicated folder at
  `<project_root>/meta/plans/<feature-slug>/`.
- Place the umbrella and every related phase plan in that feature folder. Keep the date prefix
  on every plan filename.
- Link umbrella-to-phase and phase-to-umbrella references with relative Markdown links.
- Update references from `NextSprint.md` or other plans to include the feature-folder path.
- When grouping existing loose plans, move the whole feature set, remove loose duplicates, and
  verify every reference resolves from its new location.
- Keep a single standalone plan directly in `meta/plans` unless the user requests grouping or
  the feature grows into multiple related plans.

## Plan workflow

- When speccing new features or refactors and asked to plan, add a new plan file.

## Performance notes

- Add performance optimization ideas to `meta/plans/NextSprint.md`.

## Changelog separation

- Do not log plan details in `changelog.md`.
