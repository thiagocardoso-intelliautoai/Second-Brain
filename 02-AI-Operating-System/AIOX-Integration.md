---
created_at: 2026-05-18
status: active
type: framework-integration
framework: AIOX
version: 5.2.7
source: "https://github.com/SynkraAI/aiox-core"
---

# AIOX Integration

## Decision

Install AIOX at the root of the Second Brain so both Codex and Claude Code can use AIOX agents, skills, commands, and framework resources across the whole vault.

## Boundary

AIOX is an orchestration and IDE layer. It does not replace the Second Brain operating rules.

Canonical behavior for vault work still comes from:

- `AGENTS.md`
- `00-Start-Here/AI-READ-ME-FIRST.md`
- `00-Start-Here/System-Map.md`
- `02-AI-Operating-System/AI-Behavior-and-Communication.md`
- relevant domain READMEs/MOCs
- closer scoped `AGENTS.md` files

Generic AIOX software-project assumptions, such as mandatory stories in `docs/stories/` or `npm run lint/typecheck/test`, apply only when the task is actually software or AIOX framework work.

## Installation Commands

```powershell
npx --cache "$env:TEMP\aiox-isolated-npm-cache" aiox-core@5.2.7 install --ci --yes --ide codex --merge
npx --cache "$env:TEMP\aiox-isolated-npm-cache" aiox-core@5.2.7 install --ci --yes --ide claude-code --merge
```

## Created Artifacts

- `.aiox-core/`: AIOX core framework.
- `.codex/agents/`: AIOX agent definitions for Codex.
- `.codex/skills/`: local AIOX skills for Codex.
- `CLAUDE.md`: root Claude Code project memory that imports `.claude/CLAUDE.md`.
- `.claude/CLAUDE.md`: Claude Code project instructions, now importing `../AGENTS.md`.
- `.claude/agents/`, `.claude/commands/`, `.claude/rules/`, `.claude/hooks/`, `.claude/skills/`: AIOX Claude Code materialization.
- `.env` and `.env.example`: blank AIOX environment templates, with no real secrets.
- `.gitignore`: ignores `.env`, logs, local settings, and dependency/build artifacts.

## How To Use

### Codex

Use `/skills` and choose an AIOX skill such as `aiox-master`, `aiox-architect`, `aiox-qa`, or `aiox-dev`.

You can also use shortcuts documented in root `AGENTS.md`, such as `@aiox-master`, `@architect`, `@dev`, `@qa`, `@pm`, `@po`, `@sm`, and `@analyst`.

### Claude Code

Open the vault in Claude Code. Claude should read root `CLAUDE.md`, which imports `.claude/CLAUDE.md`; that file imports `../AGENTS.md`.

Use AIOX agents through `@agent-name` or `/AIOX:agents:agent-name`.

Implementation note: current Claude Code docs say project instructions can live in `./CLAUDE.md` or `./.claude/CLAUDE.md`, and that repositories using `AGENTS.md` should create a `CLAUDE.md` that imports it. Source: https://code.claude.com/docs/en/memory

If Claude asks what to follow, answer:

1. Read root `CLAUDE.md`.
2. Respect imported root `AGENTS.md`.
3. Treat AIOX as orchestration, not as the source of truth for the vault.
4. Apply domain-specific README/MOC/AGENTS rules before changing content.

## Validation

Run from the vault root:

```powershell
npx --cache "$env:TEMP\aiox-isolated-npm-cache" aiox-core@5.2.7 validate
```

Result on 2026-05-18: passed with 100% integrity.

`doctor` note: `npx aiox-core@5.2.7 doctor` reports the root as missing `node_modules` because this vault intentionally has no root `package.json` and is not a Node app. Do not fix that by running `npm install` unless the vault later becomes an actual software project.
