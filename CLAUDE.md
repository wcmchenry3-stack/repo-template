# CLAUDE.md
<!-- Global standards: ~/.claude/CLAUDE.md and ~/.claude/standards/ -->

## Stack
<!-- TODO: Describe your stack here, e.g.:
FastAPI · SQLite · Render
or
Expo React Native · FastAPI · PostgreSQL · Render
-->

## Quick Start
<!-- TODO: Add local dev setup commands -->
```bash

```

## Key Rules
<!-- TODO: Add project-specific rules. The global hard rules in ~/.claude/CLAUDE.md always apply. -->

## Available Agents

These project subagents live in `.claude/agents/` and are invoked via the `Agent` tool (not Skill). Always prefer them over a general-purpose agent for their domain.

| Agent | `subagent_type` | When to use |
|---|---|---|
| lint-review | `lint-review` | Auto-fix lint issues after a lint-gate hook failure |
| policy-compliance | `policy-compliance` | Check and fix policy violations after a policy-gate hook failure |

## Architecture
See [docs/claude/architecture.md](docs/claude/architecture.md)

## Standards
- Git workflow: [~/.claude/standards/git.md](~/.claude/standards/git.md)
- Testing: [~/.claude/standards/testing.md](~/.claude/standards/testing.md)
- Security: [~/.claude/standards/security.md](~/.claude/standards/security.md)
- Accessibility: [~/.claude/standards/accessibility.md](~/.claude/standards/accessibility.md) *(frontend only)*
- Code style: [~/.claude/standards/code-style.md](~/.claude/standards/code-style.md)
