# AGENTS.md — ai-context

## Purpose

Documentation-only repo. Stores reusable AI agent instruction files for Velumi projects. No code, no dependencies, no build.

Files here get referenced from consuming project configs — see `README.md` for setup per tool.

## Structure

- One `.md` per domain, named `SCREAMING_CASE` (e.g., `GENERAL.md`, `DESIGN.md`)
- `GENERAL.md` = company context, included in every Velumi project
- Future files follow same pattern
- Context documents lives in `context/`

## Conventions

- Playbook references use format `` `velumi/playbook` → `filename.md` `` — keep this consistent across all files.
- Pricing, plans, positioning: always verify against playbook source of truth before editing. These files propagate to every Velumi project.
- Keep files under ~200 lines. Agents have context limits — bloat degrades performance.
- Never duplicate full playbook content. Summarize what changes agent behavior, reference the rest.
