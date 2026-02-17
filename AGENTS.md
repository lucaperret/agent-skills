# AGENTS.md

This file provides guidance to AI coding agents working on the `agent-skills` repository.

## Project Overview

`agent-skills` is a collection of [Agent Skills](https://agentskills.io) — modular capabilities that extend AI coding agents beyond code editing. Each skill is a self-contained package following the [Agent Skills specification](https://agentskills.io/specification).

Compatible with Claude Code, Cursor, Codex, Gemini CLI, GitHub Copilot, and other agents supporting the open Agent Skills standard.

## Repository Structure

```
agent-skills/
├── AGENTS.md                          # This file — guidance for AI agents
├── README.md                          # Public-facing documentation
├── LICENSE                            # MIT license
└── skills/
    ├── macos-calendar/                # One directory per skill
    │   ├── SKILL.md                   # Skill definition (required)
    │   ├── scripts/
    │   │   └── calendar.sh            # Executable helper script
    │   ├── references/
    │   │   └── recurrence.md          # Reference docs for the agent
    │   └── logs/
    │       └── calendar.log           # Runtime action log (gitignored)
    └── macos-reminders/
        ├── SKILL.md
        ├── scripts/
        │   └── reminders.sh
        ├── references/
        │   └── priorities.md
        └── logs/
            └── reminders.log          # Runtime action log (gitignored)
```

Each skill lives in `skills/<skill-name>/` with a required `SKILL.md` entry point and optional `scripts/`, `references/`, and `assets/` directories.

## Conventions

- **Skill names** use lowercase kebab-case: `macos-calendar`, not `macOSCalendar`
- **Scripts** must be executable (`chmod +x`) and use `set -euo pipefail`
- **User input** is passed via stdin (JSON), never as CLI arguments, to avoid leaking data in process lists
- **All actions** are logged to `logs/` with timestamp, command, and summary
- **No hardcoded dates** — use relative offsets or ISO 8601 (`YYYY-MM-DD`)
- **Read-only resources** must be detected and rejected with a clear error
- **Version** follows semver in `metadata.version` inside `SKILL.md`
- **Description** in frontmatter should include natural-language trigger phrases so agents can match user intent
- Keep `SKILL.md` under 500 lines — split detailed reference material into `references/` files
