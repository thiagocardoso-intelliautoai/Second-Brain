---
source: "original prompt recovery + external repo read-only inspection"
created_at: 2026-05-16
updated_at: 2026-05-20
status: external-artifacts-index
---

# Links e Artefatos Externos

## Regra

Este arquivo e um indice de links, caminhos e status. Ele nao deve virar copia dos artefatos.

O Second Brain recebe:

- links;
- status;
- criterio de uso;
- pendencias;
- decisoes;
- logs de mudanca.

O Second Brain nao recebe por padrao:

- repo inteiro;
- outputs pesados;
- workspaces temporarios;
- copias de planilhas, docs e slides que continuam vivos no Google Workspace.

Excecao decidida na Wave 1: `.codex/` e `.claude/` foram migrados para `07-Runtime-Squad/` porque eram apenas wrappers/config examples pequenos e derivados dos agentes canonicos.

## Legenda de status

| Status | Significado |
|---|---|
| Confirmado | caminho/link existe ou foi registrado no repo/QA |
| A auditar | existe caminho/local, mas a auditoria nao foi feita nesta atualizacao |
| A pesquisar | depende de pesquisa externa atualizada, nao executada aqui |
| A separar | depende de Thiago organizar ou enviar insumos |
| A decidir | precisa de decisao humana ou comparacao antes de alterar o squad |
| A implementar no runtime | decisao/protocolo documentado, mas ainda nao aplicado no runtime novo |
| Migrado | ja entrou no runtime novo |

## Runtime e repo legado

| Item | Link / path | Status | Uso |
|---|---|---|---|
| Cockpit operacional | `04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/02-Process/00-Cockpit/STATUS-ATUAL.md` | Confirmado | Primeira leitura antes de qualquer nova execucao |
| Repo legado | `D:\1AWinningSales-Projetos\squadfactory\squads\playbook-comercial-squad` | Historico / nao editar por padrao | Fonte historica para consulta, auditoria ou recuperacao |
| Runtime principal | `04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/07-Runtime-Squad/` | Migrado | Fonte tecnica viva do squad dentro do Active Project |
| Instrucoes | `07-Runtime-Squad/AGENTS.md` | Migrado | Regras de portabilidade, MCP e execucao |
| Manifesto | `07-Runtime-Squad/squad.yaml` | Migrado | Componentes e versao `0.7.0` |
| Registry de templates | `07-Runtime-Squad/templates/TEMPLATE_REGISTRY.md` | Migrado | IDs, contratos e especificacoes F1-F14 |
| QA historico | `02-Process/Runtime-Squad-Historico/wave4.2-template-qa.md` | Preservado fora do runtime | Evidencia de QA 2026-05-14 |
| Capacidades MCP | `07-Runtime-Squad/config/mcp-capabilities.md` | Migrado | Operacoes esperadas por Drive, Slides, Sheets e Docs |
| Fallback MCP | `07-Runtime-Squad/config/mcp-fallback-strategy.md` | Migrado | Manual fallback quando MCP/plugin falhar |
| Exemplo MCP | `07-Runtime-Squad/.mcp.example.json` | Migrado, incompleto por design | Placeholder seguro sem comando real nem credencial |

## Wave 1 - Migracao completa

| Item | Link / path | Status | Uso |
|---|---|---|---|
| Plano da Wave 1 | [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/02-Process/Wave-1-Exportacao-Repo-para-Second-Brain|Wave 1 - Migracao Completa do Squad para o Active Project]] | Confirmado | Criterios de migracao e QA da copia |
| Runtime novo | `04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/07-Runtime-Squad/` | Migrado | Destino da migracao do squad |
| Inventario de migracao | [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/02-Process/Runtime-Squad-Historico/MANIFESTO-DE-MIGRACAO|Manifesto de Migracao]] | Preservado fora do runtime | Lista de incluidos, excluidos, validacoes e decisao de wrappers |
| Artefatos legados | [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/02-Process/Runtime-Squad-Historico/ARTEFATOS-LEGADOS|Artefatos Legados]] | Preservado fora do runtime | Outputs/previews/workspaces mantidos no legado |
| Mapa de referencias externas | [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/02-Process/Runtime-Squad-Historico/REFERENCIAS-EXTERNAS|Referencias Externas]] | Preservado fora do runtime | Paths/URLs fora do runtime classificados |
| Path suspeito de Design System | `D:\1AWinningSales-Projetos\squadfactory\Design.md winning sales` | Existe, a verificar | Mencionado no repo; parece versao legada/parcial |

## Design System Winning Sales

| Item | Link / path | Status | Uso |
|---|---|---|---|
| Design System local | `D:\1AWinningSales-Projetos\squadfactory\Design System` | Confirmado | Auditoria obrigatoria antes de buscar skills externas |
| `README.md` | mesmo diretorio | A auditar | Brand book e fundamentos |
| `SKILL.md` | mesmo diretorio | A auditar | Skill local de design Winning Sales |
| `REFERENCE.md` | mesmo diretorio | A auditar | Cheatsheet de tokens |
| `PATTERNS.md` | mesmo diretorio | A auditar | Patterns reutilizaveis |
| `DESIGN.md` | mesmo diretorio | A auditar | Diretrizes visuais |
| `VALIDATION.md` | mesmo diretorio | A auditar | Checklist de validacao |
| `colors_and_type.css` | mesmo diretorio | A auditar | Tokens CSS |
| `tokens.yaml` / `tokens.tailwind.js` | mesmo diretorio | A auditar | Tokens estruturados |
| `assets/` | mesmo diretorio | A auditar | Logos e logomarks |
| `ui_kits/` / `v2/` | mesmo diretorio | A auditar | Componentes e exemplos |

Observacao: a leitura rapida confirmou existencia desses arquivos, mas nao substitui a auditoria exigida pela Wave 2 e pela Wave 5.

## Google Drive operacional

Registrado em `templates/TEMPLATE_REGISTRY.md`:

| Item | URL | Status | Observacao |
|---|---|---|---|
| Pasta raiz `Squad Playbook Comercial` | https://drive.google.com/drive/folders/1ETyAXq-dQnX7KgU0_Yo4NcBK3Lv7PVAH | Confirmado no registry; parent folder nao confirmado no QA | Reconfirmar com conta owner/consultor antes de governanca de Drive |
| `Templates Master` | https://drive.google.com/drive/folders/1VNNZNFyoXDCGXmuaNni7l9YDWVwf4Zoc | Confirmado no registry; parent folder nao confirmado no QA | Pasta principal dos masters |
| `Clientes` | https://drive.google.com/drive/folders/1QHOixQ_uO1zhlXZtsohxpEHHrER9Rp6d | Confirmado no registry | Destino de outputs por cliente |

Observacao do QA 2026-05-14: a conta usada no conector leu arquivos por Drive ID, mas nao confirmou a pasta raiz nem `Templates Master` por parent folder. Isso nao bloqueia geracao por Drive ID, mas precisa reconfirmacao para auditoria de governanca.

## Sheets principais

| Item | URL | Status | Uso |
|---|---|---|---|
| `master-kpis-sheet-winning` atual | https://docs.google.com/spreadsheets/d/1uMch8PIUm_M3DkuAKxYRgjWdpbpxDsKzjLMSjlLup3g/edit | Promovido por registry + pasta/metadata normalizadas em 2026-05-20 | Master F2 oficial atual; Google Sheet nativo com abas `KPIs` + `PROSPECÇÃO`; localizado em `Templates Master/01-funil-kpis` |
| `master-kpis-sheet-winning` pré-Wave 6 | https://docs.google.com/spreadsheets/d/13YLWDeRIXpo7iHaM4N4JCdn3yx17fGiKAJ5bJZvYebo/edit?gid=559901545#gid=559901545 | Histórico preservado; renomeado no Drive | Master anterior com 1 aba `KPIs`, mantido como referência histórica sob o titulo `master-kpis-sheet-winning (historico pre-Wave 6)` |
| Referencia de KPI | https://docs.google.com/spreadsheets/d/1wL98viKIWGUx-0Pwz3F6gh4plshl4VKw/edit?gid=2128190769#gid=2128190769 | Confirmado no prompt; conteudo a analisar | Usar apenas aba de PROSPECCAO |
| `master-roi-calculator-winning` atual | https://docs.google.com/spreadsheets/d/1OWeAadbcnuqcjXVtx8-6S16XAbgKnT4S2NkKwQWu8Zw/edit | Promovido por registry + metadata normalizada em 2026-05-20 | F11 v2 oficial; Google Sheet nativo com 7 abas, cenarios, dashboard e `RESUMO_*` |
| `master-roi-calculator-winning` pre-promocao | https://docs.google.com/spreadsheets/d/1CxI8RtqZifigfam7PhBA8NZVlaorLRSM9cTDUwbL5UY/edit | Historico preservado; renomeado via Sheets API | Master F11 anterior, nao oficial, mantido como referencia historica sob o titulo `master-roi-calculator-winning (historico pre-promocao F11 v2)` |
| `master-roi-calculator-winning` source QA Onda 3 | https://docs.google.com/spreadsheets/d/1FuesU793roZjix8g6cG5T6lmsl7CggPOI3bdLnI2pco/edit | Source nao oficial; renomeado via Sheets API | Source antigo do QA Onda 3, nao usar como master |
| `master-objections-matrix-winning` | https://docs.google.com/spreadsheets/d/1U3gXSMyBOGQ4m9N5PY3PW9UxAvIdSmxJBOy06dEj4zI/edit | Confirmado no registry/QA F13 | Matriz de objecoes |

Resultado Wave 4/Wave 6: a decisão Low/Mid/High touch foi aplicada sem seletor dinâmico e sem três abas duplicadas. O F2 oficial passou a usar `KPIs` + `PROSPECÇÃO`; o registry aponta para o artefato aprovado na Wave 6.

Normalizacao de pasta F2 em 2026-05-20: `Templates Master/01-funil-kpis` agora lista o F1 oficial, o F2 oficial `1uMch8PIUm_M3DkuAKxYRgjWdpbpxDsKzjLMSjlLup3g` e a subpasta `_historico-nao-oficial(apagar futuramente)`.

## Slides principais

| Item | URL | Status | Uso |
|---|---|---|---|
| F1 `master-funnel-diagram-winning` | https://docs.google.com/presentation/d/1MLhe3oKxK5hvwF6wQG-djjsTZsiOGHckpeGAV99tEMc/edit | Confirmado no registry/QA | Funil e handoff #01 |
| F1 Story 9 QA `Cliente QA F1` | https://docs.google.com/presentation/d/1_l7o56_tjdEn4FUOzvmweEN6V1KXTTaF6sNIcEI87kQ/edit | Smoke real aprovado; nao oficial | Evidencia da regressao do #01 |
| F5 Slides `master-prospecting-training-winning` | https://docs.google.com/presentation/d/1tJhBAKQVAyJ8VpNMEFgdBpWO8Mk0N6n0e0GOR_wG0wg/edit | Confirmado no registry/QA | Treinamento de prospeccao |
| F10 `master-battle-cards-winning` | https://docs.google.com/presentation/d/13Ae4tSchwM6W90vKVRRf0LRx4drcb9O8L6st7o146ns/edit | Confirmado no registry/QA | Battle cards |
| F12 Slides `master-social-proof-slides-winning` | https://docs.google.com/presentation/d/1UbRKzI-Dt2_1xBW6vfrA6g58ZPY4Kwg1InCLDk-8SW4/edit | Confirmado no registry/QA | Provas sociais em slides |
| DBA criado por Rafael | caminho/link a informar | A separar | Referencia para Wave 5/7 |
| DBS criado por Rafael | caminho/link a informar | A separar | Referencia para Wave 5/7 |
| Deck proposta / outros slides do squad | IDs no registry | A auditar | Entram na Wave 5 uma apresentacao por vez |

Sources antigos de Slides ainda podem aparecer com nome limpo em busca no Drive, mas nao sao oficiais e nao estao no registry atual: F7 `1G4S_-ltWRCAU5-drduycsFZir7ccJ_Bj_w4byu1XIPA`, F8 `11hYM2tUY7HGRDV2PQpCZIQMSEf3Zz6x4aQn1RO2I638`, F9 `1GfMus2WxkEmE8W0FQai49YaTll-wnDjp3afCB_TrOvo`, F10 `1xoXhkVnHzKXatHM9PLhF7sLk2oTrDE5AvfM_PDr9jes` e F12 Slides `1OraLz7t9OWuK7uaI6fZ907FCe6RUvT40_1nD2DJfRLU`. Tentativa de rename metadata em 2026-05-20 ficou bloqueada por `Auth required`.

## Docs principais

| Item | URL | Status | Uso |
|---|---|---|---|
| F5 Doc `master-prospecting-guide-winning` | https://docs.google.com/document/d/1K-zjcFpembRND6IuE2-UF1qrytpONPLmSCJWpQkea5I/edit | Confirmado no registry/QA | Guia de prospeccao |
| F12 Doc `master-social-proof-winning` | https://docs.google.com/document/d/1tqIIZajAENRPWxi1BgTxAHNoq69M1jde4gF9Gssjh2E/edit | Confirmado no registry/QA | Biblioteca de provas sociais |
| F14 `master-index-guide-winning` | https://docs.google.com/document/d/1Y9AC2Au26nT57nGNb3pdrN-PyW-MqBcCRXyIO1U5RYA/edit | Confirmado no registry/QA | Guia de uso / indice mestre |
| DBA/DBS explicativos do Rafael | caminho/link a informar | A separar | Precisam ser classificados como explicativos ou entregaveis de cliente |

Source antigo de Doc F12 ainda pode aparecer com nome limpo em busca no Drive, mas nao e oficial e nao esta no registry atual: `1Hn9Nk1A79fVvKX3IzjmNU-XVkBa6mV4QycUwVCs222M`. Tentativa de rename metadata em 2026-05-20 ficou bloqueada por `Auth required`.

## MCP / Claude Code

| Item | Status | Proxima acao |
|---|---|---|
| MCP server Google Workspace escolhido | A pesquisar | Pesquisar fontes 2025+ antes de recomendar |
| Google Slides MCP com edicao granular | A pesquisar | Validar suporte a shapes, text boxes, layouts, formatacao e `batch_update_presentation` |
| Compatibilidade `claude mcp add` | A pesquisar | Registrar comando exato e teste minimo |
| OAuth 2.x / multi-user | A pesquisar | Comparar candidatos |
| Plano de instalacao | A pesquisar | Documentar comando, prerequisitos e teste |
| `.mcp.example.json` do runtime | Confirmado | Atualizar somente depois da escolha tecnica, sem credenciais |

## Outputs locais do repo legado

O repo legado contem outputs temporarios em:

```text
D:\1AWinningSales-Projetos\squadfactory\squads\playbook-comercial-squad\tmp-wave3\output
D:\1AWinningSales-Projetos\squadfactory\squads\playbook-comercial-squad\tmp-wave4\output
```

Exemplos visiveis:

- `master-social-proof-winning.docx`
- `master-social-proof-slides-winning.pptx`
- `master-roi-calculator-winning.xlsx`
- `master-battle-cards-winning.pptx`
- `master-dbs-template-winning.pptx`
- `master-dba-template-winning.pptx`
- `master-proposal-deck-winning.pptx`

Regra: usar como referencia/auditoria quando necessario, mas nao trazer para o vault.

## Entregaveis logicos do registry

O registry do runtime mapeia F1-F14, incluindo docs, sheets, slides e auxiliares:

- F1/F2: funil e KPIs.
- F3/F4: ICP e scoring.
- F5/F6: prospeccao e outreach.
- F7/F8/F9: DBA, DBS e proposta.
- F10/F11/F12/F13/F14: battle cards, ROI, provas sociais, objecoes e guia de uso.

## Artefatos pendentes por wave

| Wave | Artefato / decisao | Status | Proxima acao |
|---|---|---|---|
| Wave 1 | Migracao completa do squad para o Active Project | Migrado | Inventario, `07-Runtime-Squad/`, validacoes e corte operacional do repo legado concluidos |
| Wave 1 | Auditoria de paths fora do repo | Migrado | Design System, Google links, schema URLs, tmp outputs e paths suspeitos classificados |
| Wave 2 | Auditoria do Design System | A auditar | Levantar skills, brand guidelines, templates, tokens, componentes e gaps |
| Wave 2 | Pesquisa MCP Google Workspace | A pesquisar | Comparar MCPs com fontes 2025+ |
| Wave 2 | Plano de instalacao Claude Code | A pesquisar | Registrar `claude mcp add`, prerequisitos e teste |
| Wave 3 | Metodo, criterios e contratos dos templates | A implementar no repo operacional | Definir rota/criterios por tipo e rodar auditoria de contrato antes de alterar templates |
| Wave 4 | Decisao Low/Mid/High touch do KPI sheet | Concluida | Opcao simples aprovada: `KPIs` + `PROSPECÇÃO`, sem seletor dinamico e sem 3 abas |
| Wave 4 | Fluxo ponta a ponta ate sheet entregue | Implementado no runtime | Registry, task, checklist e mini-onboarding atualizados; Wave 6 promoveu o ID oficial |
| Wave 5 | Redesign de apresentacoes | A decidir | Uma apresentacao por vez, com Design System lido integralmente |
| Wave 6 | QA gate Sim/Nao de Slides, Sheets e Docs | F2 aprovado e promovido por registry | F2 oficial atual: `1uMch8PIUm_M3DkuAKxYRgjWdpbpxDsKzjLMSjlLup3g` |
| F11 v2 | Promocao do ROI + runtime #09 | Concluida | F11 oficial atual: `1OWeAadbcnuqcjXVtx8-6S16XAbgKnT4S2NkKwQWu8Zw`; master anterior preservado |
| Wave 7 | Referencias do Rafael | A separar | Thiago separar links/arquivos e classificar origem |

## Perguntas para Thiago

- Onde estao as referencias do Rafael que devem entrar na Wave 7?
- A calculadora de ROI de referencia e a mesma F11 do squad ou existe outra referencia enviada pelo Rafael?
- A conta que vai executar o squad tera acesso de edicao aos links de KPI, DBA, DBS e ROI?
