# Agent Instructions - Second Brain

This vault is Thiago Cardoso's personal Second Brain. Before doing substantial work here, read the operating context first.

## First Read

Always read these files before analysis, editing, restructuring, writing, or executing improvement work:

1. `00-Start-Here/AI-READ-ME-FIRST.md`
2. `00-Start-Here/System-Map.md`
3. `02-AI-Operating-System/AI-Behavior-and-Communication.md`
4. The relevant domain README or MOC for the task.
5. Any closer scoped `AGENTS.md` inside the relevant folder, when present.

If the task involves strategy, active projects, vault improvement, prioritization, or major focus decisions, also read:

1. `00-Start-Here/Strategy-OS.md`

Treat the Strategy OS as a dated operating snapshot, not as permanent truth. If its snapshot is older than 30 days, ask Thiago what changed before making focus or priority decisions.

Do not force weekly or monthly review rituals. Update the Strategy OS opportunistically when the current work reveals a real change in priority, trade-off, project importance, source of income, offer direction, or strategic decision.

If the task involves LinkedIn, positioning, storytelling, personal voice, or drafts, also read:

1. `02-AI-Operating-System/Voice-Preservation-Rules.md`
2. `06-Personal-Brand/Personal-Brand-OS.md`
3. `06-Personal-Brand/Voz-e-Estilo/Do-Not-Rewrite-My-Voice.md`

If the task involves imports, restructuring, or distillation, also read:

1. `02-AI-Operating-System/Legacy-Import-Protocol.md`
2. `10-Legacy-Imports/README.md`

For scoped instructions, use the standard `AGENTS.md` filename. Do not depend on `AGENT.md` singular unless Thiago explicitly creates one as a compatibility bridge.

## Improvement Work

Only read the improvement plan when the task is explicitly about auditing, restructuring, or improving the vault.

Current improvement plan:

`00-Start-Here/Plano-de-Aprimoramento-Second-Brain.md`

## General Rules

- Do not invent project state, blockers, owners, deadlines, or criteria of done.
- If context is missing and cannot be inferred safely, create a short `Perguntas para Thiago` section or ask directly before editing.
- Preserve raw material and provenance.
- Do not silently rewrite Thiago's voice. Keep originals intact and put improved drafts under `Versao sugerida`.
- Prefer small, useful artifacts over decorative structure.

## When Improving The Vault

- Thiago expects the agent to execute improvements, not only suggest them.
- Read the current improvement plan before editing.
- Read `00-Start-Here/Strategy-OS.md` before choosing improvement priorities or interpreting which wave matters most.
- Work in waves, one domain at a time.
- Before filling unknown operational fields, ask Thiago broad context questions for that wave.
- Avoid leaving empty placeholders that will never be completed.

## Value Standard

A note should help Thiago decide, execute, teach, sell, write, or learn better.

When improving a note, try to turn it into at least one of:

- decision context;
- executable plan;
- prompt;
- checklist;
- template;
- deliverable;
- log of result;
- source-backed reference;
- publishable draft.

## AIOX Integration

AIOX v5.2.7 is installed at the vault root for Codex and Claude Code.

Use it as an orchestration and IDE layer, not as the canonical operating model of the Second Brain.

- Canonical vault instructions remain this `AGENTS.md`, `00-Start-Here/AI-READ-ME-FIRST.md`, `00-Start-Here/System-Map.md`, `02-AI-Operating-System/*`, domain READMEs/MOCs, and closer scoped `AGENTS.md` files.
- For Codex, AIOX local agents and skills live in `.codex/agents/` and `.codex/skills/`.
- For Claude Code, AIOX local agents, commands, skills, rules, and hooks live in `.claude/`.
- If Claude asks how to operate here, tell it to read root `CLAUDE.md`; it imports `.claude/CLAUDE.md`, which imports this file. Then follow the Second Brain rules before any AIOX workflow.
- Do not impose generic software-project defaults like `docs/stories/`, `packages/`, `tests/`, or mandatory `npm run lint/typecheck/test` unless the task is actually software/AIOX framework work.
- For normal vault work, use AIOX agents only when they help decide, execute, teach, sell, write, or learn better.

The AIOX-managed sections below may contain generic project assumptions. Interpret them through this Second Brain boundary.

---

<!-- AIOX-MANAGED SECTIONS -->
<!-- These sections are managed by AIOX. Edit content between markers carefully. -->
<!-- Your custom content above will be preserved during updates. -->

<!-- AIOX-MANAGED-START: core -->
## Core Rules

1. Siga a Constitution em `.aiox-core/constitution.md`
2. Priorize `CLI First -> Observability Second -> UI Third`
3. Trabalhe por stories em `docs/stories/`
4. Nao invente requisitos fora dos artefatos existentes
<!-- AIOX-MANAGED-END: core -->

<!-- AIOX-MANAGED-START: quality -->
## Quality Gates

- Rode `npm run lint`
- Rode `npm run typecheck`
- Rode `npm test`
- Atualize checklist e file list da story antes de concluir
<!-- AIOX-MANAGED-END: quality -->

<!-- AIOX-MANAGED-START: codebase -->
## Project Map

- Core framework: `.aiox-core/`
- CLI entrypoints: `bin/`
- Shared packages: `packages/`
- Tests: `tests/`
- Docs: `docs/`
<!-- AIOX-MANAGED-END: codebase -->

<!-- AIOX-MANAGED-START: commands -->
## Common Commands

- `npm run sync:ide`
- `npm run sync:ide:check`
- `npm run sync:skills:codex`
- `npm run sync:skills:codex:global` (opcional; neste repo o padrao e local-first)
- `npm run validate:structure`
- `npm run validate:agents`
<!-- AIOX-MANAGED-END: commands -->

<!-- AIOX-MANAGED-START: shortcuts -->
## Agent Shortcuts

Preferencia de ativacao no Codex CLI:
1. Use `/skills` e selecione `aiox-<agent-id>` vindo de `.codex/skills` (ex.: `aiox-architect`)
2. Se preferir, use os atalhos abaixo (`@architect`, `/architect`, etc.)

Interprete os atalhos abaixo carregando o arquivo correspondente em `.aiox-core/development/agents/` (fallback: `.codex/agents/`), renderize o greeting via `generate-greeting.js` e assuma a persona ate `*exit`:

- `@architect`, `/architect`, `/architect.md` -> `.aiox-core/development/agents/architect.md`
- `@dev`, `/dev`, `/dev.md` -> `.aiox-core/development/agents/dev.md`
- `@qa`, `/qa`, `/qa.md` -> `.aiox-core/development/agents/qa.md`
- `@pm`, `/pm`, `/pm.md` -> `.aiox-core/development/agents/pm.md`
- `@po`, `/po`, `/po.md` -> `.aiox-core/development/agents/po.md`
- `@sm`, `/sm`, `/sm.md` -> `.aiox-core/development/agents/sm.md`
- `@analyst`, `/analyst`, `/analyst.md` -> `.aiox-core/development/agents/analyst.md`
- `@devops`, `/devops`, `/devops.md` -> `.aiox-core/development/agents/devops.md`
- `@data-engineer`, `/data-engineer`, `/data-engineer.md` -> `.aiox-core/development/agents/data-engineer.md`
- `@ux-design-expert`, `/ux-design-expert`, `/ux-design-expert.md` -> `.aiox-core/development/agents/ux-design-expert.md`
- `@squad-creator`, `/squad-creator`, `/squad-creator.md` -> `.aiox-core/development/agents/squad-creator.md`
- `@aiox-master`, `/aiox-master`, `/aiox-master.md` -> `.aiox-core/development/agents/aiox-master.md`
<!-- AIOX-MANAGED-END: shortcuts -->
