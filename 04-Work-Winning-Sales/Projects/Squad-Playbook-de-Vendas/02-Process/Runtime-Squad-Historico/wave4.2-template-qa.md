# Onda 4.2: QA Integrado dos Templates

Data: 2026-05-14  
Conta do conector usada na leitura: `samuel@winningsales.com.br`  
Escopo: 14 templates logicos do registry + auxiliares F5 Slides e F12 Slides.

## Decisao

**Pronto para piloto end-to-end controlado.** Todos os arquivos operacionais abriram por Drive ID, sao Google Workspace nativos, estao legiveis pelo conector/plugin e ficaram alinhados com registry, tasks, agents e checklists apos as correcoes locais desta onda.

Validacao final em 2026-05-14: wrappers `.codex` e `.claude` sincronizados com `agents/*.md`; `node scripts\validate-platform-compatibility.js` passou com 7 agents.

Pendencia nao bloqueante para geracao: a conta atual do conector nao conseguiu abrir a pasta raiz `Squad Playbook Comercial` (`1ETyAXq-dQnX7KgU0_Yo4NcBK3Lv7PVAH`) nem `Templates Master` (`1VNNZNFyoXDCGXmuaNni7l9YDWVwf4Zoc`), retornando `404 NOT_FOUND`. Por isso, a pasta correta deve ser reconfirmada com a conta owner/consultor antes de uma auditoria 100% de governanca do Drive. A geracao por Drive ID nao fica bloqueada por essa pendencia.

## Inventario Unico de QA

| ID | Nome esperado | Tipo esperado | Pasta esperada | Link | Status de leitura plugin/MCP | Status estrategico | Pendencias |
|---|---|---|---|---|---|---|---|
| F1 | `master-funnel-diagram-winning` | Google Slides | `Templates Master/01-funil-kpis` | [abrir](https://docs.google.com/presentation/d/1MLhe3oKxK5hvwF6wQG-djjsTZsiOGHckpeGAV99tEMc/edit) | OK: abriu, nativo, 5 slides, texto extraivel, thumbnail de amostra gerado | Aprovado: sustenta funil e handoff #01 | Pasta nao confirmada pelo conector atual |
| F2 | `master-kpis-sheet-winning` | Google Sheets | `Templates Master/01-funil-kpis` | [abrir](https://docs.google.com/spreadsheets/d/13YLWDeRIXpo7iHaM4N4JCdn3yx17fGiKAJ5bJZvYebo/edit) | OK: abriu, nativo, locale `pt_BR`, formulas parseaveis, zero erro visivel | Aprovado: KPIs Camada A+B e contrato A:H | Timezone `America/Los_Angeles` nao bloqueia; pasta nao confirmada |
| F3 | `master-icp-narrative-winning` | Google Docs | `Templates Master/02-icp-persona` | [abrir](https://docs.google.com/document/d/1za_FPKz8HAZ-Dfs2png2Zuvp-GbqX22DHIIZCKmp6rc/edit) | OK: abriu, nativo, texto/tabelas legiveis, placeholders integros | Aprovado: ICP/personas acionaveis | Pasta nao confirmada pelo conector atual |
| F4 | `master-icp-scoring-winning` | Google Sheets | `Templates Master/02-icp-persona` | [abrir](https://docs.google.com/spreadsheets/d/1Zqufaii9qTzxXT6gOcjQWfaR2ztaTXhQ4UPR4-AmAK4/edit) | OK: abriu, nativo, locale `pt_BR`, formulas tolerantes | Aprovado: scoring acionavel com corte/fit | Aba real `master-icp-scoring-winning-corrigido`; timezone nao bloqueia; pasta nao confirmada |
| F5 Doc | `master-prospecting-guide-winning` | Google Docs | `Templates Master/03-prospeccao` | [abrir](https://docs.google.com/document/d/1K-zjcFpembRND6IuE2-UF1qrytpONPLmSCJWpQkea5I/edit) | OK: abriu, nativo, texto legivel, placeholders integros | Aprovado: prepara prospeccao e transicao DBA | Pasta nao confirmada pelo conector atual |
| F5 Slides | `master-prospecting-training-winning` | Google Slides | `Templates Master/03-prospeccao` | [abrir](https://docs.google.com/presentation/d/1tJhBAKQVAyJ8VpNMEFgdBpWO8Mk0N6n0e0GOR_wG0wg/edit) | OK: abriu, nativo, 16 slides, texto extraivel, thumbnail de amostra gerado | Aprovado: treinamento didatico #03 | Placeholders `03_APLICACAO_*` foram mapeados nesta onda; pasta nao confirmada |
| F6 | `master-outreach-matrix-winning` | Google Sheets | `Templates Master/04-outreach` | [abrir](https://docs.google.com/spreadsheets/d/1ezEhGslMVrIf9c772mZLRr8Y_VgocJLvLXeQ1Z2vkeM/edit) | OK: abriu, nativo, locale `pt_BR`, 84 linhas, zero formulas/erros | Aprovado: matriz por tipo/canal/persona | Timezone nao bloqueia; pasta nao confirmada |
| F7 | `master-dba-template-winning` | Google Slides | `Templates Master/05-dba` | [abrir](https://docs.google.com/presentation/d/1y5DQOjCljY18FVwMkbglWf-cBlckltXfogJ21L9eeuo/edit) | OK: abriu, nativo, 72 slides, texto extraivel, thumbnail de amostra gerado | Aprovado: DBA 90/10, diagnostico e demo consultiva | Pasta nao confirmada pelo conector atual |
| F8 | `master-dbs-template-winning` | Google Slides | `Templates Master/06-dbs` | [abrir](https://docs.google.com/presentation/d/1DshHoQYm1gUdmMWHqW9HbIHnS9dRkv3fSlBxn_QyKbk/edit) | OK: abriu, nativo, 48 slides, texto extraivel, thumbnail de amostra gerado | Aprovado: continuidade do DBA, nao novo diagnostico | Pasta nao confirmada pelo conector atual |
| F9 | `master-proposal-deck-winning` | Google Slides | `Templates Master/07-deck-proposta` | [abrir](https://docs.google.com/presentation/d/1feXvh8Ox139_J1xcDqxJWScqXRrOrokZYsND9hPkgd8/edit) | OK: abriu, nativo, 12 slides, texto extraivel, thumbnail de amostra gerado | Aprovado: consome DBA, ROI e provas sociais | Pasta nao confirmada pelo conector atual |
| F10 | `master-battle-cards-winning` | Google Slides | `Templates Master/08-battle-cards` | [abrir](https://docs.google.com/presentation/d/13Ae4tSchwM6W90vKVRRf0LRx4drcb9O8L6st7o146ns/edit) | OK: abriu, nativo, 3 slides, texto extraivel, thumbnail de amostra gerado | Aprovado: ajuda vendedor em call real | Pasta nao confirmada pelo conector atual |
| F11 | `master-roi-calculator-winning` | Google Sheets | `Templates Master/09-calculadora-roi` | [abrir](https://docs.google.com/spreadsheets/d/1CxI8RtqZifigfam7PhBA8NZVlaorLRSM9cTDUwbL5UY/edit) | OK: abriu, nativo, locale `pt_BR`, timezone `America/Sao_Paulo`, 4 abas, zero erro visivel | Aprovado: ROI auditavel para proposta | Pasta nao confirmada pelo conector atual |
| F12 Doc | `master-social-proof-winning` | Google Docs | `Templates Master/10-provas-sociais` | [abrir](https://docs.google.com/document/d/1tqIIZajAENRPWxi1BgTxAHNoq69M1jde4gF9Gssjh2E/edit) | OK: abriu, nativo, texto/tabelas legiveis | Aprovado: biblioteca tagueada, nao lista solta | Taxonomia foi mapeada nesta onda; pasta nao confirmada |
| F12 Slides | `master-social-proof-slides-winning` | Google Slides | `Templates Master/10-provas-sociais` | [abrir](https://docs.google.com/presentation/d/1UbRKzI-Dt2_1xBW6vfrA6g58ZPY4Kwg1InCLDk-8SW4/edit) | OK: abriu, nativo, 5 slides, texto extraivel, thumbnail de amostra gerado | Aprovado com regra: duplicar layout para case 4+ | Regra de duplicacao documentada nesta onda; pasta nao confirmada |
| F13 | `master-objections-matrix-winning` | Google Sheets | `Templates Master/11-objecoes` | [abrir](https://docs.google.com/spreadsheets/d/1U3gXSMyBOGQ4m9N5PY3PW9UxAvIdSmxJBOy06dEj4zI/edit) | OK: abriu, nativo, locale `pt_BR`, filtros/colunas legiveis | Aprovado: matriz de objecoes para call real | Timezone nao bloqueia; pasta nao confirmada |
| F14 | `master-index-guide-winning` | Google Docs | `Templates Master/00-indice-mestre` | [abrir](https://docs.google.com/document/d/1Y9AC2Au26nT57nGNb3pdrN-PyW-MqBcCRXyIO1U5RYA/edit) | OK: abriu, nativo, texto legivel, placeholders integros | Aprovado: guia simples de navegacao | Pasta nao confirmada pelo conector atual |

## QA de Contrato

Bloqueadores encontrados e corrigidos localmente:

- Nomes do registry estavam sem sufixo `-winning` em varios templates, enquanto o Drive real usa os titulos finais. Corrigido em `templates/TEMPLATE_REGISTRY.md`, tasks e agents.
- F2 registry esperava colunas `Frequencia de update` e `Observacoes`, mas a Sheet real tem contrato A:H. Corrigido para A:H.
- F5 Slides continha placeholders reais `{{03_APLICACAO_*}}` que estavam parcialmente implicitos como `etc.`. Corrigido no registry, task e checklist.
- F12 Doc continha placeholders de taxonomia sem dono explicito. Corrigido no registry, task, agent e checklist.
- F12 Slides tem 3 layouts iniciais de case, enquanto o Doc suporta 5 cases. Corrigido com regra obrigatoria de duplicar layout de case para case 4+ antes do find-replace.

Sem bloqueadores remanescentes de contrato local apos as correcoes.

## QA Tecnico por Tipo

Docs:

- F3, F5 Doc, F12 Doc e F14 tiveram texto real lido pelo conector.
- Secoes obrigatorias presentes, placeholders integros, sem sinal de mojibake no texto lido.
- F12 inclui taxonomia, indice, cases e lacunas; nao e lista solta.

Sheets:

- F2, F4, F6, F11 e F13 estao em locale `pt_BR`.
- F2, F4 e F11 usam formulas parseaveis e tolerantes a placeholders.
- Nenhum `#ERROR!`, `#VALUE!` ou `#DIV/0!` foi observado nas leituras principais.
- F6 nao usa formulas e manteve 84 linhas oficiais.

Slides:

- F1, F5 Slides, F7, F8, F9, F10 e F12 Slides tiveram outline/texto extraivel e thumbnails de amostra gerados.
- Nenhum deck se comportou como imagem chapada: os outlines retornaram elementos e texto por slide.
- F7, F8 e F9 mantem a contagem esperada: 72, 48 e 12 slides.

## Classificacao das Pendencias

Bloqueador:

- Nenhum remanescente apos a sincronizacao final dos wrappers e rerun das validacoes.

Importante:

- Validar parent folders com a conta owner/consultor, porque a conta atual nao abre a raiz nem `Templates Master`.
- Ajustar timezone dos Sheets F2/F4/F6/F13 para `America/Sao_Paulo` se algum fluxo futuro passar a usar datas/horarios em formulas. Hoje nao bloqueia geracao.

Polimento:

- Revisao visual humana opcional dos thumbnails finais antes de demonstracao externa. A amostragem tecnica nao encontrou sinal de arquivo chapado ou sem texto.

## Templates Corrigidos no Contrato Local

- F1-F6, F10-F14: nomes normalizados para os titulos reais do Drive.
- F2: contrato de colunas e placeholders ajustado ao master real.
- F5: placeholders de treinamento explicitados.
- F6: placeholders reais em colchetes documentados.
- F12: taxonomia, placeholders reais e regra de duplicacao dos slides auxiliares documentados.

## Validação Local

Comandos obrigatorios da Onda 4.2:

```powershell
node scripts\validate-platform-compatibility.js
node scripts\validate-template-registry.js --require-p0
```

Resultado: registrar no plano apos execucao final.

Resultado em 2026-05-14:

- `node scripts\validate-template-registry.js --require-p0`: PASS.
- `node scripts\validate-template-registry.js --strict-drive-ids`: PASS.
- `node scripts\validate-platform-compatibility.js`: PASS.
