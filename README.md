# ai-context

Shared AI agent instruction files for Velumi projects. Each `.md` file covers one domain and gets pulled into consuming repos via tool-specific config.

## Files

| File | Domain | Include in |
|------|--------|------------|
| `GENERAL.md` | Company context, positioning, pricing, ICPs, billing | Every Velumi project |
| `DESIGN.md` | Frontend/UI conventions | Frontend projects *(planned)* |

More files follow the same pattern: one `.md` per concern, named in `SCREAMING_CASE`.

## Usage — OpenCode

Add raw GitHub URLs to `opencode.jsonc` in the consuming repo root:

```jsonc
// opencode.jsonc
{
  "$schema": "https://opencode.ai/config.json",
  "instructions": [
    "https://raw.githubusercontent.com/velumi/ai-context/main/GENERAL.md"
  ]
}
```

Multiple files and glob patterns work:

```jsonc
{
  "$schema": "https://opencode.ai/config.json",
  "instructions": [
    "https://raw.githubusercontent.com/velumi/ai-context/main/GENERAL.md",
    "https://raw.githubusercontent.com/velumi/ai-context/main/DESIGN.md"
  ]
}
```

All instruction files are combined with the project's `AGENTS.md`.

## Usage — Claude Code

Claude Code does not support remote URL imports in `CLAUDE.md` yet ([tracking issue](https://github.com/anthropics/claude-code/issues/29072)).

One could possibly reference URLs in CLAUDE.md file, but that's not reliable and "expensive" since it requires tools which takes up additional context space.

## Writing guidelines

These files are consumed by AI agents with limited context windows. Every line costs tokens.

- **Write for agents, not humans.** Every line should change agent behavior or prevent a mistake. Cut prose that doesn't.
- **One file per topic.** Don't mix concerns.
- **Prefer bullets and tables** over paragraphs.
- **Reference, don't duplicate.** Link to `velumi/playbook` repo for deep detail. Summarize only what agents need.
- **Verify before editing.** Pricing, plans, and positioning must match the playbook source of truth before updating here.
- **Keep files compact.** If a file exceeds ~200 lines, split it or trim.
