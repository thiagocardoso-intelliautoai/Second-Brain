---
source: "Wave 1 migration execution"
created_at: 2026-05-17
status: completed
related:
  - "04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/02-Process/Wave-1-Exportacao-Repo-para-Second-Brain.md"
  - "04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/02-Process/Runtime-Squad-Historico/MANIFESTO-DE-MIGRACAO.md"
---

# 2026-05-17 - Wave 1 - Migracao do Runtime do Squad

## Resultado

Wave 1 executada.

O Active Project agora contem o runtime principal do Squad em:

```text
04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/07-Runtime-Squad/
```

O repo antigo fica como legado/historico:

```text
D:\1AWinningSales-Projetos\squadfactory\squads\playbook-comercial-squad
```

## Decisoes tomadas

- Criar `07-Runtime-Squad/` dentro do Active Project.
- Migrar `.codex/` e `.claude/` inteiros, porque neste repo eles sao apenas wrappers/config examples.
- Manter `agents/*.md` como fonte canonica.
- Tratar wrappers como derivados e sincronizaveis via `node scripts\sync-agent-wrappers.js`.
- Nao copiar `.tmp/`, `tmp-wave3/` e `tmp-wave4/` para o runtime principal.
- Registrar outputs, previews e workspaces temporarios em manifesto, nao como copia no vault.
- Marcar o repo legado operacionalmente como historico/nao editar dentro do Project OS, sem alterar fisicamente o repo legado nesta execucao.

## Validacoes

Rodadas no novo runtime:

```powershell
node scripts\validate-template-registry.js
node scripts\validate-template-registry.js --require-p0
node scripts\validate-template-registry.js --strict-drive-ids
node scripts\validate-platform-compatibility.js
```

Resultado:

- registry: PASS, 14/14 templates e 292 placeholders;
- registry P0: PASS;
- strict Drive IDs: PASS;
- platform compatibility: PASS, 7 agents.

## Pendencias

- Decidir proxima frente: Wave 4 KPI Sheet parece o proximo bloco mais concreto, salvo prioridade nova de Rafael.
- Confirmar referencias do Rafael para Wave 7.
- Antes de redesenho visual, auditar `D:\1AWinningSales-Projetos\squadfactory\Design System`.
- Resolver se `scripts/validate-template-client-facing.js` deve ser atualizado, porque ele aponta para `tmp-wave4/build_wave4_decks.mjs`, que ficou fora do runtime.

