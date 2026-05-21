---
created_at: 2026-05-18
status: concluida
wave: 3
scope: contrato-f2-master-kpis-sheet-winning
runtime_modified: false
mode: read-only
target_artifact: "F2 master-kpis-sheet-winning"
target_drive_id: "13YLWDeRIXpo7iHaM4N4JCdn3yx17fGiKAJ5bJZvYebo"
story_mirror: "02-Process/Artefatos/F2-master-kpis-sheet-winning/00-stories-espelho.md#f2-s01---contrato-e-auditoria-read-only"
---

# Wave 3 - Contrato F2 `master-kpis-sheet-winning`

## Nota de governanca - 2026-05-21

Esta wave historica agora esta espelhada pela story `F2-S01` em `02-Process/Artefatos/F2-master-kpis-sheet-winning/00-stories-espelho.md`.

Para nova execucao de F2, criar story nova. Nao reexecutar esta wave sem motivo novo.

## Objetivo

Mapear o artefato alvo para automacao futura, identificando placeholders, campos, variaveis, origem dos dados, limites visuais, dependencias, riscos e fallback antes da Wave 4.

## Escopo e regras aplicadas

Fato confirmado:

- A execucao foi feita em modo read-only.
- Nenhum arquivo do runtime do squad foi alterado.
- Nenhuma ferramenta foi instalada.
- Este registro foi criado em `02-Process/` apos aprovacao explicita de Thiago.
- A Wave 2 foi usada como fonte de verdade para rotas tecnicas confirmadas/a testar.

Inferencia:

- Como o alvo recomendado da Wave 4 e o KPI Sheet, o recorte prioritario da Wave 3 deve ser F2 antes de qualquer mudanca em template, agent, task, skill, checklist ou registry.

## Artefato alvo escolhido

Fato confirmado:

| Campo | Valor |
|---|---|
| Artefato | F2 `master-kpis-sheet-winning` |
| Tipo | Google Sheets |
| Entregavel | `#01 KPIs` / `01_funil_kpis` |
| Drive ID | `13YLWDeRIXpo7iHaM4N4JCdn3yx17fGiKAJ5bJZvYebo` |
| Aba real | `KPIs` |
| `sheetId` | `559901545` |
| Locale | `pt_BR` |
| Timezone | `America/Los_Angeles` |

Justificativa curta:

- O mapa operacional recomenda iniciar a Wave 3 pelo artefato de KPI/planilha.
- A Wave 4 tem como alvo direto o `master-kpis-sheet-winning`.
- A proxima mudanca prevista nao e apenas visual: pode afetar registry, task, agent, skill, checklist, fluxo de mini-onboarding e coerencia com ROI.

## Fontes lidas

Fato confirmado:

| Fonte | Uso |
|---|---|
| `AGENTS.md` | Regras do cockpit e proibicao de alterar runtime sem aprovacao |
| `07-Runtime-Squad/AGENTS.md` | Fonte canonica, portabilidade, MCP/fallback |
| `02-Process/Mapa-do-Squad-e-Repo-Externo.md` | Sequenciamento das Waves e prioridade F2 |
| `02-Process/Wave-2-Auditoria-Design-System-e-Google-Workspace-MCP.md` | Rotas tecnicas confirmadas/a testar |
| `07-Runtime-Squad/templates/TEMPLATE_REGISTRY.md` | Contrato declarado de F2 |
| `07-Runtime-Squad/tasks/generate-funnel-kpis.md` | Task dona e inputs de geracao |
| `07-Runtime-Squad/agents/foundation-agent.md` | Agent dono |
| `07-Runtime-Squad/checklists/camada-a-estruturais.md` | Validacoes universais |
| `07-Runtime-Squad/checklists/camada-b-01-funil-kpis.md` | Validacoes especificas do #01 |
| `07-Runtime-Squad/checklists/camada-c-cross-deliverable.md` | Dependencias cross-entregavel |
| `07-Runtime-Squad/config/mcp-capabilities.md` | Regra MCP primeiro, plugin como fallback tecnico |
| `07-Runtime-Squad/config/mcp-fallback-strategy.md` | Fallback manual |
| `02-Process/Runtime-Squad-Historico/wave4.2-template-qa.md` | QA historico dos templates |
| Google Sheets F2 real | Metadata, range `KPIs!A1:H20`, formulas `KPIs!A5:H20` |
| Referencia `1wL98viKIWGUx-0Pwz3F6gh4plshl4VKw` | Metadata e extracao textual parcial do `.xlsx` |

## Rota tecnica para Sheets

Fato confirmado:

| Rota | Status | Evidencia |
|---|---|---|
| Codex Google Drive plugin/conector | Confirmado no Codex | Wave 2 testou Sheets com batch update, formula, formatacao, validacao e formatacao condicional |
| Google Sheets real F2 via conector | Confirmado para leitura | Metadata e ranges de F2 foram lidos nesta Wave 3 |
| `workspace-mcp` | A testar | Wave 2 recomenda como candidato portavel Codex + Claude Code |
| Fallback manual | Disponivel | `config/mcp-fallback-strategy.md` cobre criar Sheets/CSV/formulas manualmente |

Inferencia:

- Para Wave 4 no Codex, a rota operacional mais segura e usar o conector Google Drive/Sheets ja confirmado.
- Para regra portavel do squad, qualquer decisao final deve continuar escrita por capacidade MCP/fallback, nao por dependencia fixa do plugin Codex.

## Contrato real observado no F2

Fato confirmado:

| Local | Conteudo |
|---|---|
| `KPIs!A1` | `Playbook Comercial - KPIs | {{NOME_CLIENTE}}` |
| `KPIs!A2` | `Winning Sales` |
| `KPIs!A3` | Instrucao curta de uso da planilha |
| `KPIs!A5:H5` | `KPI`, `Camada`, `Definição`, `Fórmula operacional`, `Meta`, `Atual`, `% Atingimento`, `Dono` |
| `KPIs!A6:H10` | 5 KPIs Camada A fixos |
| `KPIs!A11:H15` | 5 slots Camada B |
| `KPIs!G6:G15` | Formula `=IFERROR(F{linha}/E{linha};"")` |
| `KPIs!A17` | `Rituais comerciais` |
| `KPIs!A18:D20` | 3 rituais com placeholders em `D18:D20` |

Fato confirmado:

| Linha | KPI / bloco | Camada | Placeholders ou formula |
|---:|---|---|---|
| 6 | Reunioes agendadas | A - fixo | `{{01_KPI_A1_META}}`, `{{01_KPI_A1_ATUAL}}`, `=IFERROR(F6/E6;"")`, `{{01_KPI_A1_DONO}}` |
| 7 | Reunioes realizadas | A - fixo | `{{01_KPI_A2_META}}`, `{{01_KPI_A2_ATUAL}}`, `=IFERROR(F7/E7;"")`, `{{01_KPI_A2_DONO}}` |
| 8 | Tentativas de contato | A - fixo | `{{01_KPI_A3_META}}`, `{{01_KPI_A3_ATUAL}}`, `=IFERROR(F8/E8;"")`, `{{01_KPI_A3_DONO}}` |
| 9 | Conversao MQL-SQL | A - fixo | `{{01_KPI_A4_META}}`, `{{01_KPI_A4_ATUAL}}`, `=IFERROR(F9/E9;"")`, `{{01_KPI_A4_DONO}}` |
| 10 | Ciclo medio | A - fixo | `{{01_KPI_A5_META}}`, `{{01_KPI_A5_ATUAL}}`, `=IFERROR(F10/E10;"")`, `{{01_KPI_A5_DONO}}` |
| 11 | KPI B1 | B - customizado | `{{01_KPI_B1_NOME}}`, `{{01_KPI_B1_DEFINICAO}}`, `{{01_KPI_B1_FORMULA}}`, `{{01_KPI_B1_META}}`, `{{01_KPI_B1_ATUAL}}`, `=IFERROR(F11/E11;"")`, `{{01_KPI_B1_DONO}}` |
| 12 | KPI B2 | B - customizado | `{{01_KPI_B2_NOME}}`, `{{01_KPI_B2_DEFINICAO}}`, `{{01_KPI_B2_FORMULA}}`, `{{01_KPI_B2_META}}`, `{{01_KPI_B2_ATUAL}}`, `=IFERROR(F12/E12;"")`, `{{01_KPI_B2_DONO}}` |
| 13 | KPI B3 | B - customizado | `{{01_KPI_B3_NOME}}`, `{{01_KPI_B3_DEFINICAO}}`, `{{01_KPI_B3_FORMULA}}`, `{{01_KPI_B3_META}}`, `{{01_KPI_B3_ATUAL}}`, `=IFERROR(F13/E13;"")`, `{{01_KPI_B3_DONO}}` |
| 14 | KPI B4 | B - customizado opcional | `{{01_KPI_B4_NOME}}`, `{{01_KPI_B4_DEFINICAO}}`, `{{01_KPI_B4_FORMULA}}`, `{{01_KPI_B4_META}}`, `{{01_KPI_B4_ATUAL}}`, `=IFERROR(F14/E14;"")`, `{{01_KPI_B4_DONO}}` |
| 15 | KPI B5 | B - customizado opcional | `{{01_KPI_B5_NOME}}`, `{{01_KPI_B5_DEFINICAO}}`, `{{01_KPI_B5_FORMULA}}`, `{{01_KPI_B5_META}}`, `{{01_KPI_B5_ATUAL}}`, `=IFERROR(F15/E15;"")`, `{{01_KPI_B5_DONO}}` |
| 18 | Daily 15 min | Ritual | `{{01_RITUAL_DAILY}}` |
| 19 | Weekly 45-60 min | Ritual | `{{01_RITUAL_WEEKLY}}` |
| 20 | 1:1 semanal | Ritual | `{{01_RITUAL_1_1}}` |

## Inventario de campos, variaveis e riscos

| Item | Dono | Origem | Formato esperado | Limite visual seguro | Obrigatorio/opcional | Fallback | Risco |
|---|---|---|---|---|---|---|---|
| `{{NOME_CLIENTE}}` | Foundation Agent / onboarding | `perfil.json.cliente.nome` | Texto | Ate 45 caracteres no cabecalho | Obrigatorio | Voltar ao onboarding se faltar | Nome longo pode estourar `A1` |
| KPIs Camada A fixos | Template + Foundation Agent | Contrato fixo do squad | Texto fixo | Nao alterar nomes sem decisao | Obrigatorio | Manter texto fixo | Troca de nome quebra checklist e coerencia futura com ROI |
| `{{01_KPI_A1..A5_META}}` | Foundation Agent | `decisoes/01-funil-kpis.json.metas_numericas` | Numero sem unidade | Celulas E6:E10; numero curto | Obrigatorio | Pedir meta ao consultor | Unidade textual quebra formula de atingimento |
| `{{01_KPI_A1..A5_ATUAL}}` | Foundation Agent / consultor | Baseline atual, CRM ou input manual | Numero sem unidade | Celulas F6:F10; numero curto | Obrigatorio para entrega final confiavel | Campo manual ou `0` apenas se confirmado | Se vazio/zero sem contexto pode gerar leitura falsa |
| `{{01_KPI_A1..A5_DONO}}` | Foundation Agent / consultor | Mini-onboarding ou papel comercial padrao | Texto curto | Ate 35 caracteres | Obrigatorio | `A definir` apenas com aprovacao humana | KPI sem dono nao e acionavel |
| `{{01_KPI_B1..B3_NOME}}` | Foundation Agent | `kpis_camada_b`, produto vendido, vault | Texto especifico do produto | Ate 35 caracteres | Obrigatorio, salvo decisao humana | Gerar por inferencia e pedir confirmacao | KPI generico reprova checklist B6 |
| `{{01_KPI_B4..B5_NOME}}` | Foundation Agent | `kpis_camada_b`, produto vendido, vault | Texto especifico do produto | Ate 35 caracteres | Opcional | Limpar/remover linhas extras | Placeholder remanescente reprova Camada A |
| `{{01_KPI_B1..B5_DEFINICAO}}` | Foundation Agent | Contexto do produto e decisao comercial | 1 frase | Ate 120 caracteres | Obrigatorio se linha existir | Limpar/remover linha nao usada | Texto longo reduz legibilidade |
| `{{01_KPI_B1..B5_FORMULA}}` | Foundation Agent | Regra operacional do KPI | Texto humano, nao formula tecnica | Ate 90 caracteres | Obrigatorio se linha existir | Limpar/remover linha nao usada | Formula textual ambigua reduz uso do vendedor |
| `{{01_KPI_B1..B5_META}}` | Foundation Agent | Meta numerica aprovada | Numero sem unidade | Celulas E11:E15 | Obrigatorio se linha existir | Pedir input ao consultor | Quebra formula ou vira placeholder residual |
| `{{01_KPI_B1..B5_ATUAL}}` | Foundation Agent / consultor | Baseline atual, CRM ou input manual | Numero sem unidade | Celulas F11:F15 | Obrigatorio se linha existir | Campo manual, ou vazio apenas se formula tolerar | Pode gerar 0% enganoso |
| `{{01_KPI_B1..B5_DONO}}` | Foundation Agent / consultor | Mini-onboarding, papel comercial, owner interno | Texto curto | Ate 35 caracteres | Obrigatorio se linha existir | `A definir` apenas com aprovacao humana | Sem dono, KPI customizado perde operacao |
| Formulas `G6:G15` | Template / Sheets | Calculada a partir de Meta e Atual | Formula percentual | Celula G; formatacao percentual | Obrigatorio | Manter `IFERROR`, revisar blanks na Wave 4 | Hoje pode mascarar dado ausente |
| `{{01_RITUAL_DAILY}}` | Foundation Agent | `decisoes/01-funil-kpis.json.rituais` ou default | Texto curto | Ate 100 caracteres | Obrigatorio no template real | Default: desbloqueios e foco do dia; ou remover bloco | Nao documentado no registry F2 |
| `{{01_RITUAL_WEEKLY}}` | Foundation Agent | `decisoes/01-funil-kpis.json.rituais` ou default | Texto curto | Ate 100 caracteres | Obrigatorio no template real | Default: revisar funil e compromissos | Nao documentado no registry F2 |
| `{{01_RITUAL_1_1}}` | Foundation Agent | `decisoes/01-funil-kpis.json.rituais` ou default | Texto curto | Ate 100 caracteres | Obrigatorio no template real | Default: coaching por vendedor | Nao documentado no registry F2 |
| `ticket_medio` | Onboarding Agent / Foundation Agent | Mini-onboarding #01 ou perfil comercial | Numero monetario | N/A no F2 atual | Necessario para Wave 4 Low/Mid/High | Perguntar ao consultor | Ainda nao existe no contrato atual |
| `ciclo_venda_dias` | Onboarding Agent / Foundation Agent | Mini-onboarding #01 ou CRM | Numero inteiro | N/A no F2 atual | Necessario para Wave 4 Low/Mid/High | Perguntar ao consultor | Ainda nao existe no contrato atual |
| `decisores_envolvidos` | Onboarding Agent / Foundation Agent | Mini-onboarding #01 ou diagnostico | Numero inteiro | N/A no F2 atual | Necessario para Wave 4 Low/Mid/High | Perguntar ao consultor | Ainda nao existe no contrato atual |
| `complexidade_touch` | Onboarding Agent / Foundation Agent | Derivada de ticket, ciclo e decisores | Enum `low`, `mid`, `high` | N/A no F2 atual | Necessario para Wave 4 | Calculo assistido + validacao humana | Decisao ainda nao formalizada |

## Dependencias

Fato confirmado:

| Dependencia | Impacto |
|---|---|
| `perfil.json` | Fonte de `NOME_CLIENTE`, produto vendido e identidade visual |
| `decisoes/01-funil-kpis.json` | Deve conter funis, KPIs Camada B, metas numericas e rituais |
| `generate-funnel-kpis.md` | Task que duplica F2 e executa find-replace |
| `foundation-agent.md` | Agent dono de #01 Funil + KPIs |
| `find-replace-placeholders.md` | Skill que aplica placeholders e exige zero remanescentes |
| `identidade-visual-dupla.md` | Skill visual para cabecalho, tabela e paleta |
| `camada-b-01-funil-kpis.md` | Checklist de KPIs Camada A+B, formulas e rituais |
| `camada-c-cross-deliverable.md` | Calculadora ROI #09 compara KPIs Camada B com #01 |
| F11 `master-roi-calculator-winning` | Consome KPIs Camada B em etapa posterior |

Inferencia:

- Qualquer mudanca de estrutura em F2 na Wave 4 deve atualizar, no minimo: registry, task `generate-funnel-kpis.md`, checklist Camada B, prompts/mini-onboarding e possivelmente regras de coerencia com F11.

## Referencia de PROSPECCAO e Low/Mid/High

Fato confirmado:

- O arquivo de referencia `1wL98viKIWGUx-0Pwz3F6gh4plshl4VKw` tem nome `Etapas do processo de Vendas -- B2B_WinningSales.xlsx`.
- O mime type e `application/vnd.openxmlformats-officedocument.spreadsheetml.sheet`.
- A API de Google Sheets retornou que a operacao nao e suportada porque o documento e Office, nao Google Sheets nativo.
- A extracao textual parcial confirmou secoes de:
  - diagnostico de complexidade;
  - regua Low/Mid/High;
  - anatomia de etapa;
  - funis de prospeccao Inbound e Outbound;
  - pipeline Low Touch;
  - pipeline Mid Touch;
  - pipeline High Touch;
  - pos-venda/CS;
  - referencia e checklist.
- A secao `FUNIS DE PROSPECÇÃO` contem Inbound e Outbound com componentes: Objetivo, Acoes, Saida Obrigatoria, Campos Obrigatorios, SLA de Tempo e Responsavel.

Inferencia:

- A referencia e util para Wave 4, mas ainda nao esta pronta como fonte automatizavel celula-a-celula.
- Antes de incorporar `PROSPECCAO`, a Wave 4 precisa converter o `.xlsx` para Google Sheets nativo ou baixar/parsear workbook localmente com preservacao de abas.

## Divergencias encontradas

| Severidade | Fato confirmado | Impacto |
|---|---|---|
| Alta | `scripts/analyze-template-contracts.py` e citado pela Wave 3, mas nao existe em `07-Runtime-Squad/scripts/` | Processo automatico recomendado nao pode ser executado como descrito |
| Alta | Registry F2 diz que frequencia/observacoes nao entram no contrato atual, mas o template real tem bloco `Rituais comerciais` com placeholders | Risco de placeholders remanescentes em entrega final |
| Alta | Nao ha schema explicito para `decisoes/01-funil-kpis.json` cobrindo metas, atual, donos e rituais | Automacao pode preencher parcialmente ou inventar campos |
| Media | F2 timezone esta `America/Los_Angeles` | Nao bloqueia hoje, mas pode afetar formulas/datas futuras |
| Media | Referencia de Wave 4 e `.xlsx`, nao Sheets nativo | Leitura granular por Sheets API fica bloqueada ate converter/baixar |
| Media | Formula atual usa `IFERROR(F/E;"")`, mas Meta/Atual podem ser placeholders ou vazios | Pode mascarar dado ausente e gerar leitura enganosa |
| Media | B4/B5 sao opcionais na planilha, mas task fala preencher 5 sempre que houver insumo e limpar/remover se houver menos | Precisa regra deterministica de quando limpar linha |

## Lacunas que impedem automacao segura

Fato confirmado:

1. O script de auditoria automatica citado no processo nao existe no runtime.
2. Placeholders de rituais existem no template real, mas nao estao explicitamente mapeados no contrato F2 do registry.
3. A referencia de PROSPECCAO nao pode ser lida via Google Sheets API enquanto permanecer como `.xlsx`.
4. A decisao Low/Mid/High ainda nao foi tomada.
5. A origem exata de `Atual` para cada KPI nao esta definida: CRM, input manual, baseline ou valor inicial.
6. Nao ha limite visual formalizado no registry/task/checklist para nomes, definicoes, formulas operacionais e donos.

Inferencia:

1. Sem schema de decisoes, o Foundation Agent pode preencher valores numericos, texto e donos de forma inconsistente entre clientes.
2. Se Wave 4 adicionar abas de prospeccao sem regra de limpeza, o consultor pode entregar ao cliente abas nao aplicaveis.
3. Se a logica Low/Mid/High virar seletor dinamico antes do contrato estar claro, ha risco de overengineering e formulas mais frageis.

## Recomendacao objetiva para Wave 4

Recomendacao:

1. Nao alterar o master F2 antes de aprovar um contrato F2 v2.
2. Converter ou baixar/parsear o `.xlsx` de referencia para obter estrutura de abas, celulas e formulas de forma confiavel.
3. Formalizar `decisoes/01-funil-kpis.json` com pelo menos:
   - `metas_numericas`;
   - `valores_atuais`;
   - `donos_kpis`;
   - `kpis_camada_b`;
   - `rituais`;
   - `ticket_medio`;
   - `ciclo_venda_dias`;
   - `decisores_envolvidos`;
   - `complexidade_touch`.
4. Atualizar contrato local para incluir ou remover oficialmente os placeholders de rituais.
5. Definir limites visuais por campo antes de editar o template.
6. Preferir, como primeira hipotese, 3 abas separadas Low/Mid/High em vez de seletor dinamico, com regra operacional para manter apenas a aba aplicavel.
7. So depois atualizar F2, task, checklist e prompts do squad.

Inferencia:

- A opcao de 3 abas separadas parece mais segura que uma aba dinamica porque reduz formulas condicionais, facilita revisao humana e combina com o pedido original de evitar overengineering.

## Backlog sugerido para aprovacao futura

Nao executado nesta Wave 3:

| Item | Arquivo/artefato afetado | Motivo |
|---|---|---|
| Criar ou ajustar auditor de contratos | `07-Runtime-Squad/scripts/analyze-template-contracts.py` | Processo da Wave 3 cita script inexistente |
| Documentar rituais no contrato F2 | `templates/TEMPLATE_REGISTRY.md` | Alinhar template real e registry |
| Expandir task #01 para rituais e complexidade | `tasks/generate-funnel-kpis.md` | Garantir origem e dono das novas variaveis |
| Atualizar checklist B #01 | `checklists/camada-b-01-funil-kpis.md` | Validar rituais, Low/Mid/High e limpeza de abas/linhas |
| Definir schema de decisoes #01 | Runtime/config ou docs operacionais | Evitar preenchimento parcial |
| Converter/parsear referencia `.xlsx` | Artefato Google Workspace ou leitura local | Permitir comparacao celula-a-celula |
