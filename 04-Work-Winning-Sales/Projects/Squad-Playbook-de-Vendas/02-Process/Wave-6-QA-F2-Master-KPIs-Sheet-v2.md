---
created_at: 2026-05-18
updated_at: 2026-05-20
status: concluida-promovida-por-registry
wave: 6
scope: qa-f2-master-kpis-sheet-winning-v2-sandbox
target_artifact: "F2 master-kpis-sheet-winning v2"
target_sandbox_id: "1TtoiNQHHr3e5okgSAVYofG5qs53UoCLFEDjQMnKHle8"
target_master_id: "13YLWDeRIXpo7iHaM4N4JCdn3yx17fGiKAJ5bJZvYebo"
promoted_master_id: "1uMch8PIUm_M3DkuAKxYRgjWdpbpxDsKzjLMSjlLup3g"
previous_promoted_copy_id: "1TtoiNQHHr3e5okgSAVYofG5qs53UoCLFEDjQMnKHle8"
verdict: "Sim"
master_modified: "registry_promoted"
runtime_modified_in_this_wave: true
drive_metadata_modified: metadata_normalized_via_sheets_api
story_mirror: "02-Process/Artefatos/F2-master-kpis-sheet-winning/00-stories-espelho.md#f2-s03---qa-e-promocao-por-registry"
---

# Wave 6 - QA F2 `master-kpis-sheet-winning` v2

## Nota de governanca - 2026-05-21

Esta wave historica agora esta espelhada pela story `F2-S03` em `02-Process/Artefatos/F2-master-kpis-sheet-winning/00-stories-espelho.md`.

Para nova execucao de F2, criar story nova. Nao reexecutar esta wave sem motivo novo.

## Objetivo

Validar a sandbox do F2 v2 como gate tecnico final da Wave 4, antes de qualquer promocao para o master `master-kpis-sheet-winning`.

Nota de governanca adicionada em 2026-05-20: F2 esta sendo executado por waves. A fila operacional curta que conecta stories x waves vive em `02-Process/Backlog-Operacional-Atual.md`. A proxima execucao material do F2 deve partir desta Wave 6 aprovada, nao de uma story F1.

Veredito final:

> **Sim**. A sandbox F2 v2 esta aprovada para promocao ao master, desde que a promocao preserve as duas abas `KPIs` + `PROSPECÇÃO` e mantenha o contrato runtime ja atualizado.

Este veredito nao significa que o master ja foi alterado. O master original permanece sem alteracao.

Atualizacao de promocao em 2026-05-20:

- A promocao foi executada pelo caminho autorizado de registry pointer.
- O F2 oficial atual passou a ser `1uMch8PIUm_M3DkuAKxYRgjWdpbpxDsKzjLMSjlLup3g`.
- O master anterior `13YLWDeRIXpo7iHaM4N4JCdn3yx17fGiKAJ5bJZvYebo` foi preservado como referencia historica.

## Protocolo usado

Fato confirmado:

- A Wave 3 do F2 foi executada e registrada em `02-Process/Wave-3-Contrato-F2-Master-KPIs-Sheet.md`.
- A Wave 4 do F2 foi aprovada, executada em sandbox e registrada em `02-Process/Wave-4-F2-Master-KPIs-Sheet-v2.md`.
- O protocolo detalhado citado em `07-Runtime-Squad/docs/WAVE-6-QA-GATE.md` nao existe no runtime atual.
- A secao `Wave 6 - QA gate tecnico Sim/Nao` em `02-Process/Mapa-do-Squad-e-Repo-Externo.md` foi usada como fonte operacional do gate.

Inferencia:

- A ausencia de `07-Runtime-Squad/docs/WAVE-6-QA-GATE.md` e risco de processo/documentacao, mas nao bloqueia o F2 porque o protocolo necessario esta preservado no mapa operacional e este relatorio registra a execucao.

## Fontes e evidencias

Fato confirmado:

| Fonte | Evidencia usada |
|---|---|
| Sandbox F2 v2 | Metadata, abas, ranges `KPIs!A1:H20` e `PROSPECÇÃO!A1:G41` |
| Comentarios da sandbox | Sem comentarios/replies ativos |
| Wave 3 F2 | Contrato de variaveis, formulas, rituais e lacunas |
| Wave 4 F2 | Decisao `KPIs` + `PROSPECÇÃO`, mapa de mudancas e registro pos-aprovacao |
| `templates/TEMPLATE_REGISTRY.md` | F2 atualizado para 2 abas e placeholders novos |
| `tasks/generate-funnel-kpis.md` | Inputs, placeholders e validacao da aba `PROSPECÇÃO` |
| `checklists/camada-b-01-funil-kpis.md` | B7 adicionado para validar `PROSPECÇÃO` |
| `tasks/run-mini-onboarding.md` | Perguntas #01 atualizadas para complexidade e canais |
| `skills/mini-onboarding-pattern.md` | Defaults #1 atualizados |

## Resultado da leitura do artefato

Fato confirmado:

| Checagem | Resultado |
|---|---|
| Planilha promovida | `master-kpis-sheet-winning` |
| URL | https://docs.google.com/spreadsheets/d/1uMch8PIUm_M3DkuAKxYRgjWdpbpxDsKzjLMSjlLup3g/edit |
| Locale | `pt_BR` |
| Timezone | `America/Los_Angeles` |
| Abas | `KPIs`, `PROSPECÇÃO` |
| Comentarios | Nenhum comentario ativo |
| Master original | Nao alterado |

### Aba `KPIs`

Fato confirmado:

- A linha 5 mantem as colunas A:H: KPI, Camada, Definicao, Formula operacional, Meta, Atual, % Atingimento, Dono.
- Linhas 6 a 10 mantem os 5 KPIs Camada A.
- Linhas 11 a 15 mantem os 5 slots Camada B.
- `G6:G15` mantem formulas `=IFERROR(F{linha}/E{linha};"")`.
- O bloco `Rituais comerciais` existe em `A17:D20`.
- Os placeholders `{{01_RITUAL_DAILY}}`, `{{01_RITUAL_WEEKLY}}` e `{{01_RITUAL_1_1}}` continuam presentes no template e agora estao contratados no runtime.

Inferencia:

- Para template master/sandbox, placeholders sao esperados. O gate reprovaria somente placeholder sem dono/origem/fallback ou placeholder remanescente em entregavel final gerado.

### Aba `PROSPECÇÃO`

Fato confirmado:

- Existe exatamente uma aba `PROSPECÇÃO`.
- Nao existem abas duplicadas `PROSPECÇÃO - Low`, `PROSPECÇÃO - Mid` ou `PROSPECÇÃO - High`.
- Nao ha seletor dinamico.
- A aba contem:
  - complexidade comercial aplicada;
  - ticket medio mensal;
  - ciclo de venda em dias;
  - decisores envolvidos;
  - canais ativos;
  - regua Low/Mid/High;
  - funil Inbound;
  - funil Outbound;
  - handoff para vendas.
- Inbound contem: Objetivo, Acoes, Saida obrigatoria, Campos obrigatorios, SLA de tempo e Responsavel.
- Outbound contem: Objetivo, Acoes, Saida obrigatoria, Campos obrigatorios, SLA de tempo e Responsavel.
- O handoff usa `Reuniao agendada` como ponto de passagem.

Inferencia:

- A aba `PROSPECÇÃO` esta alinhada com a decisao da Wave 4: incorporar a logica util da referencia sem copiar pipeline completo e sem overengineering.

## Placeholders e contrato

Fato confirmado:

| Grupo | Status |
|---|---|
| `{{NOME_CLIENTE}}` | Origem e dono ja mapeados na Wave 3 |
| KPIs A1..A5 meta/atual/dono | Mantidos e cobertos pela Wave 3 + task #01 |
| KPIs B1..B5 nome/definicao/formula/meta/atual/dono | Mantidos e cobertos pela Wave 3 + task #01 |
| Rituais `daily`, `weekly`, `1_1` | Divergencia da Wave 3 resolvida no registry/task/checklist |
| Complexidade touch | Coberta pela Wave 4 + task #01 + mini-onboarding |
| Ticket/ciclo/decisores | Cobertos pela Wave 4 + task #01 + mini-onboarding |
| Canais ativos | Coberto pela Wave 4 + task #01 + mini-onboarding |
| Responsaveis de prospeccao e handoff | Cobertos pela Wave 4 + task #01 + mini-onboarding |

Inferencia:

- Nao foi encontrado placeholder novo sem caminho de preenchimento. O risco de placeholder remanescente fica controlado pelo find-replace e pela Camada A em entregavel final.

## Achados

| Severidade | Achado | Evidencia | Correcao |
|---|---|---|---|
| Baixa | O arquivo `07-Runtime-Squad/docs/WAVE-6-QA-GATE.md` citado no mapa nao existe. | Tentativa de leitura retornou arquivo ausente. | Criar/promover esse protocolo para o runtime em uma wave documental futura, se o repo operacional precisar ficar 100% autossuficiente. |
| Baixa | O registry ainda aponta para o master F2 original, nao para a sandbox. | `templates/TEMPLATE_REGISTRY.md` preservava o Drive ID `13YLW...`, enquanto a sandbox era `1Ttoi...`. | Resolvido em 2026-05-20: registry atualizado para `1Ttoi...` como F2 oficial. |

Nao foram encontrados bloqueios tecnicos no F2 v2 sandbox.

## Riscos residuais

| Risco | Severidade | Tratamento |
|---|---:|---|
| Nao ha schema JSON separado para `decisoes/01-funil-kpis.json` | Media | A task agora declara os campos obrigatorios; schema formal pode virar melhoria futura. |
| Uma busca textual adicional na Sheets API sofreu rate limit 429 | Baixa | Mitigado por leitura completa dos ranges relevantes e buscas/inspecoes ja realizadas. |
| Visual final ainda depende de QA apos preenchimento real | Media | Camada A do Reviewer deve validar 0 placeholders e ausencia de texto interno no entregavel final gerado. |

## Capacidades MCP/conector/fallback

Fato confirmado:

- O Codex Google Drive plugin/conector leu e editou a sandbox.
- A Wave 2 ja havia confirmado Sheets com batch update, formula, formatacao, validacao e formatacao condicional.
- O fallback manual em `config/mcp-fallback-strategy.md` cobre Sheets via CSV/formulas quando MCP/conector nao estiver disponivel.

Inferencia:

- Para Codex, a rota esta confirmada.
- Para portabilidade Claude Code/Codex via `workspace-mcp`, continua `a testar`, mas nao bloqueia este gate porque o runtime mantem fallback por capacidade.

## Validacoes locais

Fato confirmado:

- `node scripts/validate-template-registry.js` passou.
- `node scripts/validate-template-registry.js --require-p0` passou na Wave 4 pos-aprovacao.
- `node scripts/validate-template-registry.js --strict-drive-ids` passou na Wave 4 pos-aprovacao.
- `node scripts/validate-platform-compatibility.js` passou.
- Nao ha `package.json` na raiz do cockpit nem em `07-Runtime-Squad/`; portanto `npm run lint`, `npm run typecheck` e `npm test` nao sao aplicaveis neste workspace.

## Veredito final

**Sim.**

A sandbox F2 v2 esta aprovada para promocao ao master. A promocao deve preservar:

- duas abas: `KPIs` + `PROSPECÇÃO`;
- formulas de `KPIs!G6:G15`;
- rituais em `KPIs!A17:D20`;
- aba `PROSPECÇÃO` unica, estatica e editavel;
- nenhum seletor dinamico;
- nenhuma triplicacao Low/Mid/High;
- runtime ja atualizado em registry, task, checklist e mini-onboarding.

## Registro pos-promocao - 2026-05-20

Fato confirmado:

- Metodo executado: atualizar o registry para apontar ao artefato promovido.
- ID oficial F2 apos normalizacao de pasta: `1uMch8PIUm_M3DkuAKxYRgjWdpbpxDsKzjLMSjlLup3g`.
- URL oficial: https://docs.google.com/spreadsheets/d/1uMch8PIUm_M3DkuAKxYRgjWdpbpxDsKzjLMSjlLup3g/edit
- Registry atualizado: `07-Runtime-Squad/templates/TEMPLATE_REGISTRY.md`.
- Backlog atualizado: `02-Process/Backlog-Operacional-Atual.md`.
- Indice de links atualizado: `03-Outputs/Links-e-Artefatos-Externos.md`.

Tentativas de metadata no Drive:

- Renomear a sandbox para `master-kpis-sheet-winning`: tentativa inicial pelo conector de Drive metadata bloqueada por permissao insuficiente; resolvido em 2026-05-20 via Sheets API `updateSpreadsheetProperties.title`.
- Copiar a sandbox para a pasta `Templates Master/01-funil-kpis`: bloqueado pelo conector legado, que nao localizou o ID mesmo com leitura disponivel pelo conector principal.
- Atualizacao posterior em 2026-05-20: o master anterior `13YLWDeRIXpo7iHaM4N4JCdn3yx17fGiKAJ5bJZvYebo` foi renomeado com sucesso para `master-kpis-sheet-winning (historico pre-Wave 6)`. A copia promovida inicial `1TtoiNQHHr3e5okgSAVYofG5qs53UoCLFEDjQMnKHle8` foi substituida como ID canonico pela copia organizada em pasta `1uMch8PIUm_M3DkuAKxYRgjWdpbpxDsKzjLMSjlLup3g`, que segue oficial por registry.
- Decisao operacional: nao bloquear a promocao por metadata; usar o ID aprovado como master oficial via registry.

Smoke test pos-promocao:

| Checagem | Resultado |
|---|---|
| Metadata | OK: Google Sheets nativo, locale `pt_BR`, timezone `America/Los_Angeles` |
| Abas | OK: `KPIs` + `PROSPECÇÃO` |
| `KPIs!A1:H20` | OK: cabecalho, KPIs A/B, formulas `=IFERROR(F{linha}/E{linha};"")` em `G6:G15` e rituais preservados |
| `PROSPECÇÃO!A1:G41` | OK: complexidade, regua Low/Mid/High, Inbound, Outbound e handoff presentes |

Proximo passo objetivo:

1. Para execucao de produto, seguir para QA de geracao real ou para a proxima frente do backlog.
2. Se houver necessidade de governanca de pastas, reconfirmar parent folder com conta owner antes de mover qualquer arquivo.
