---
created_at: 2026-05-21
updated_at: 2026-05-21
status: active
classification: operational-cockpit
scope: stories-waves-governance
source_of_truth: true
drive_modified: false
runtime_modified: false
---

# Status Atual - Squad Playbook de Vendas

## Regra central

**Story e a unidade de execucao. Wave e apenas agrupamento, marco historico ou checkpoint.**

F1, F2 e F11 continuam como IDs de artefato/template do registry. Eles nao sao etapas de trabalho.

Nenhuma execucao material deve comecar direto de chat, benchmark, mapa de contexto ou wave solta. O SM precisa criar ou validar uma story antes de dev/QA executar.

## Agora

| Area | Estado | Documento vivo | Proxima acao permitida |
|---|---|---|---|
| Execucao ativa | Nada em execucao | Este cockpit | Escolher uma nova story antes de qualquer mudanca |
| Ciclo F1/F2/F11 | Concluido em 2026-05-20 | `02-Process/Backlog-Operacional-Atual.md` | Usar como baseline, nao reabrir sem story nova |
| Masters do Drive | Preservados por registry | `07-Runtime-Squad/templates/TEMPLATE_REGISTRY.md` | Nao editar sem aprovacao explicita |

## Artefatos oficiais

| Artefato | Template | ID oficial atual | Formato operacional | QA final | Proxima acao |
|---|---|---|---|---|---|
| F1 | `master-funnel-diagram-winning` | `1MLhe3oKxK5hvwF6wQG-djjsTZsiOGHckpeGAV99tEMc` | Stories | Story 9 regressao `Sim` em 2026-05-20 | Nova geracao/review deve nascer de story |
| F2 | `master-kpis-sheet-winning` | `1uMch8PIUm_M3DkuAKxYRgjWdpbpxDsKzjLMSjlLup3g` | Stories-espelho sobre Waves 3/4/6 | Wave 6 `Sim`, promocao por registry em 2026-05-20 | Proxima mudanca deve ser story F2 nova |
| F11 | `master-roi-calculator-winning` | `1OWeAadbcnuqcjXVtx8-6S16XAbgKnT4S2NkKwQWu8Zw` | Stories-espelho sobre frente ROI | Promocao/runtime `Sim` em 2026-05-20 | Geracao real so com premissas reais e QA de caso |

## Proximas frentes

| Prioridade | Frente | Documento de origem | Status | Como iniciar |
|---:|---|---|---|---|
| 1 | Wave 2 MCP / Codex / Claude Code / Google Workspace + Design System | `02-Process/Wave-2-Auditoria-Design-System-e-Google-Workspace-MCP.md` | Pendente | SM cria story de pesquisa/auditoria antes de executar |
| 2 | Wave 7 referencias do Rafael | `02-Process/Mapa-do-Squad-e-Repo-Externo.md#wave-7---referencias-do-rafael` | Pendente de insumos | Uma story por referencia ou por artefato afetado |
| 3 | Outros artefatos de apresentacao | Registry + story nova | Pendente | Rodar Wave 3/5A/5B/6 apenas como marcos dentro de stories |
| 4 | Primeira geracao real F11 #09 | `02-Process/Artefatos/F11-master-roi-calculator-winning/07-stories-espelho.md` | Pendente | Story nova com premissas reais, fonte e QA de caso |

## Stories-espelho criadas

| Story | Artefato | O que espelha | Status |
|---|---|---|---|
| F2-S01 | F2 | Wave 3 contrato/auditoria | Concluida |
| F2-S02 | F2 | Wave 4 sandbox `KPIs + PROSPECCAO` | Concluida |
| F2-S03 | F2 | Wave 6 QA/promocao | Concluida |
| F11-S01 | F11 | Auditoria read-only F11-W3 | Concluida |
| F11-S02 | F11 | Sandbox + QA F11-W6 | Concluida |
| F11-S03 | F11 | Promocao/runtime F11 v2 | Concluida |

## Checklist para nova execucao

Antes de executar qualquer mudanca material, a story precisa declarar:

| Campo | Obrigatorio |
|---|---|
| Objetivo | Sim |
| Escopo e fora de escopo | Sim |
| Artefato alvo e Drive ID | Sim |
| Modo | `read-only`, `sandbox`, `runtime-docs`, `promocao-master` ou `qa` |
| Wave relacionada | Sim, quando existir marco historico |
| Criterios de aceite | Sim |
| Evidencia esperada | Sim |
| Status final | `Sim`, `Nao`, `Bloqueada` ou `Cancelada` |

## Fontes auxiliares

- Glossario operacional: `02-Process/00-Cockpit/GLOSSARIO-STORIES-WAVES.md`
- Backlog curto: `02-Process/Backlog-Operacional-Atual.md`
- F1 stories: `02-Process/Artefatos/F1-master-funnel-diagram-winning/04-stories-sm.md`
- F2 stories-espelho: `02-Process/Artefatos/F2-master-kpis-sheet-winning/00-stories-espelho.md`
- F11 stories-espelho: `02-Process/Artefatos/F11-master-roi-calculator-winning/07-stories-espelho.md`
- Registry oficial: `07-Runtime-Squad/templates/TEMPLATE_REGISTRY.md`

