---
created_at: 2026-05-20
updated_at: 2026-05-20
status: concluido
wave: "promocao-runtime-F11-v2"
scope: promocao-master-e-runtime
artifact: F11 master-roi-calculator-winning
veredito: Sim
official_f11_id: "1OWeAadbcnuqcjXVtx8-6S16XAbgKnT4S2NkKwQWu8Zw"
historical_f11_id: "1CxI8RtqZifigfam7PhBA8NZVlaorLRSM9cTDUwbL5UY"
runtime_modified: true
drive_modified: metadata_title_normalized_via_sheets_api
master_modified: metadata_only_title
source_plan: "05-plano-execucao-promocao-runtime-f11-v2.md"
story_mirror: "07-stories-espelho.md#f11-s03---promocao-e-runtime-f11-v2"
---

# Registro de Promocao + Runtime F11 v2

## Nota de governanca - 2026-05-21

Este registro historico agora esta espelhado pela story `F11-S03` em `07-stories-espelho.md`.

## Veredito

**Sim.**

A sandbox F11 v2 aprovada foi promovida por registry pointer e o runtime local foi atualizado para gerar/validar o contrato F11 v2.

## IDs

| Papel | ID | Status |
|---|---|---|
| F11 oficial atual | `1OWeAadbcnuqcjXVtx8-6S16XAbgKnT4S2NkKwQWu8Zw` | Promovido por registry e metadata normalizada em 2026-05-20 |
| Master F11 historico | `1CxI8RtqZifigfam7PhBA8NZVlaorLRSM9cTDUwbL5UY` | Preservado como historico; titulo normalizado em 2026-05-20 |
| Source F11 QA Onda 3 | `1FuesU793roZjix8g6cG5T6lmsl7CggPOI3bdLnI2pco` | Nao oficial; titulo normalizado em 2026-05-20 |

URL oficial:

- `https://docs.google.com/spreadsheets/d/1OWeAadbcnuqcjXVtx8-6S16XAbgKnT4S2NkKwQWu8Zw/edit`

## Arquivos alterados

- `07-Runtime-Squad/templates/TEMPLATE_REGISTRY.md`
- `07-Runtime-Squad/tasks/generate-roi-calculator.md`
- `07-Runtime-Squad/checklists/camada-b-09-calculadora-roi.md`
- `07-Runtime-Squad/tasks/run-mini-onboarding.md`
- `07-Runtime-Squad/skills/mini-onboarding-pattern.md`
- `07-Runtime-Squad/checklists/camada-c-cross-deliverable.md`
- `07-Runtime-Squad/agents/specialty-agent.md`
- `07-Runtime-Squad/.codex/agents/specialty-agent.toml`
- `07-Runtime-Squad/.claude/agents/specialty-agent.md`
- `07-Runtime-Squad/skills/validacao-3-camadas.md`
- `07-Runtime-Squad/config/mcp-fallback-strategy.md`
- `07-Runtime-Squad/README.md`
- `02-Process/Backlog-Operacional-Atual.md`
- `02-Process/Artefatos/F11-master-roi-calculator-winning/00-wave-3-contrato-e-frente-roi.md`
- `02-Process/Artefatos/F11-master-roi-calculator-winning/05-plano-execucao-promocao-runtime-f11-v2.md`
- `02-Process/Artefatos/F1-master-funnel-diagram-winning/04-stories-sm.md`
- `03-Outputs/Links-e-Artefatos-Externos.md`
- `02-Process/Artefatos/F11-master-roi-calculator-winning/06-registro-promocao-runtime-f11-v2.md`

## Validacoes locais

Executadas a partir de `07-Runtime-Squad/`:

| Comando | Resultado |
|---|---|
| `node scripts/validate-template-registry.js` | Pass |
| `node scripts/validate-template-registry.js --require-p0` | Pass |
| `node scripts/validate-template-registry.js --strict-drive-ids` | Pass |
| `node scripts/validate-platform-compatibility.js` | Pass |
| `node scripts/sync-agent-wrappers.js` | 7 wrappers sincronizados |

Busca textual:

- `rg -n "4 abas|Sheets \(4 abas\)|Calculadora ROI: 4|Calculadora tem 4|CSV das 4 abas|cria as 4 abas|\(4 abas:" 07-Runtime-Squad`
- Resultado: apenas documentos historicos (`02-Process/Runtime-Squad-Historico/template-factory-plan.md`, `02-Process/Runtime-Squad-Historico/wave4.2-template-qa.md`) ainda mencionam 4 abas, como registro do F11 anterior.

## Smoke test pos-promocao no Sheets

Planilha lida:

- titulo: `master-roi-calculator-winning`
- locale: `pt_BR`
- timezone: `America/Sao_Paulo`

Abas confirmadas por metadata:

1. `1. Capa`
2. `2. Inputs`
3. `3. Motor de Cálculo`
4. `4. Resumo Executivo`
5. `5. Cenários`
6. `6. Dashboard`
7. `7. Saidas tecnicas`

Ranges lidos:

- `'1. Capa'!B2:F38`
- `'2. Inputs'!B7:F37`
- `'3. Motor de Cálculo'!B7:F32`
- `'4. Resumo Executivo'!B5:F31`
- `'5. Cenários'!B6:F20`
- `'6. Dashboard'!B6:H42`
- `'7. Saidas tecnicas'!A1:D18`

Resultado:

- 7 abas presentes.
- Ranges criticos legiveis.
- Comentarios ativos: nenhum.
- Busca por erro visivel nos ranges/sheets varridos: sem `#ERROR!`, `#VALUE!` ou `#DIV/0!`.
- `RESUMO_*` legado e F11 v2 presentes em `7. Saidas tecnicas!A4:D18`.
- `RESUMO_FRASE_FINAL` permanece neutro: `Preencher premissas de valor para gerar o resumo executivo.`
- `RESUMO_AVISO_COMERCIAL` presente, evitando promessa contratual indevida.

## Riscos residuais

| Risco | Severidade | Tratamento |
|---|---|---|
| Sources antigos ainda podem aparecer em buscas por nome historico. | Baixa | F11 historico e source QA Onda 3 foram renomeados; tratar qualquer source como nao oficial quando o ID nao bater com o registry. |
| A ferramenta de metadata nao listou named ranges. | Baixa | A aba `7. Saidas tecnicas` foi lida e contem o contrato `RESUMO_*`; revalidar named ranges quando houver ferramenta adequada. |
| Ainda nao houve geracao real com cliente. | Media | Antes de entrega real, rodar mini-onboarding #09, preencher premissas reais e executar QA de caso. |

## Proximo passo

Rodar a primeira geracao real do #09 somente com premissas reais, fonte registrada e QA de caso. Ate la, deck/proposta devem consumir `RESUMO_AVISO_COMERCIAL` quando `RESUMO_FRASE_FINAL` estiver em estado neutro.
