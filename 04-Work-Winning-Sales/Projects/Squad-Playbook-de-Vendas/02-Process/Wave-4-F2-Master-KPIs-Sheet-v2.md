---
created_at: 2026-05-18
status: aprovada-sandbox-e-runtime-parcial
wave: 4
scope: f2-master-kpis-sheet-winning-v2
runtime_modified: true
sheet_modified: "sandbox_only"
mode: read-only-contract
target_artifact: "F2 master-kpis-sheet-winning"
target_drive_id: "13YLWDeRIXpo7iHaM4N4JCdn3yx17fGiKAJ5bJZvYebo"
reference_drive_id: "1wL98viKIWGUx-0Pwz3F6gh4plshl4VKw"
sandbox_drive_id: "1TtoiNQHHr3e5okgSAVYofG5qs53UoCLFEDjQMnKHle8"
story_mirror: "02-Process/Artefatos/F2-master-kpis-sheet-winning/00-stories-espelho.md#f2-s02---sandbox-f2-v2-kpis--prospeccao"
---

# Wave 4 - F2 `master-kpis-sheet-winning` v2

## Nota de governanca - 2026-05-21

Esta wave historica agora esta espelhada pela story `F2-S02` em `02-Process/Artefatos/F2-master-kpis-sheet-winning/00-stories-espelho.md`.

Para nova execucao de F2, criar story nova. Nao reexecutar esta wave sem motivo novo.

## Objetivo

Preparar a decisao de evolucao do F2 `master-kpis-sheet-winning`, incorporando somente a logica util de PROSPECCAO da referencia e a variacao Low/Mid/High touch sem overengineering.

## Escopo e regras aplicadas

Fato confirmado:

- Na etapa inicial de contrato, nenhum arquivo do runtime foi alterado; apos aprovacao de Thiago, os arquivos canonicos listados em `Registro pos-aprovacao` foram atualizados.
- O master Google Sheet F2 nao foi alterado; somente a sandbox foi criada/alterada.
- Nenhuma ferramenta foi instalada.
- Este registro foi gravado em `02-Process/`, seguindo o padrao das Waves 2 e 3.
- A Wave 3 foi usada como contrato-base e fonte de verdade.
- A referencia `1wL98viKIWGUx-0Pwz3F6gh4plshl4VKw` foi tratada como `.xlsx`, nao como Google Sheets nativo.

Inferencia:

- A Wave 4 pode recomendar estrutura e backlog de mudanca, mas a implementacao no runtime e no Google Sheet precisa de aprovacao explicita.

## Fontes lidas

Fato confirmado:

| Fonte | Uso |
|---|---|
| `AGENTS.md` | Regras do cockpit e restricao de alteracao do runtime |
| `07-Runtime-Squad/AGENTS.md` | Fonte canonica, portabilidade e fallback MCP |
| `02-Process/Mapa-do-Squad-e-Repo-Externo.md` | Sequenciamento das Waves e escopo da Wave 4 |
| `02-Process/Wave-2-Auditoria-Design-System-e-Google-Workspace-MCP.md` | Rotas tecnicas confirmadas/a testar |
| `02-Process/Wave-3-Contrato-F2-Master-KPIs-Sheet.md` | Contrato-base do F2 |
| F2 real `13YLWDeRIXpo7iHaM4N4JCdn3yx17fGiKAJ5bJZvYebo` | Metadata, aba e range `KPIs!A1:H25` |
| Referencia `.xlsx` `1wL98viKIWGUx-0Pwz3F6gh4plshl4VKw` | Workbook baixado/parseado localmente para abas e conteudo relevante |
| `07-Runtime-Squad/templates/TEMPLATE_REGISTRY.md` | Contrato declarado atual do F2 |
| `07-Runtime-Squad/tasks/generate-funnel-kpis.md` | Task dona de geracao do #01 |
| `07-Runtime-Squad/checklists/camada-b-01-funil-kpis.md` | Checklist especifico do #01 |
| `07-Runtime-Squad/tasks/run-mini-onboarding.md` | Perguntas/defaults atuais de mini-onboarding |
| `07-Runtime-Squad/skills/mini-onboarding-pattern.md` | Defaults por entregavel |
| `07-Runtime-Squad/agents/foundation-agent.md` | Agent dono provavel; regras especificas ficam na task |
| `07-Runtime-Squad/config/mcp-capabilities.md` | MCP primeiro, plugin/conector como fallback tecnico |
| `07-Runtime-Squad/config/mcp-fallback-strategy.md` | Fallback manual para Sheets |

## F2 atual observado

Fato confirmado:

| Item | Valor |
|---|---|
| Titulo | `master-kpis-sheet-winning` |
| Tipo | Google Sheets nativo |
| Locale | `pt_BR` |
| Timezone | `America/Los_Angeles` |
| Abas | 1 aba: `KPIs` |
| Range operacional | `KPIs!A1:H20` |
| Colunas da linha 5 | KPI, Camada, Definicao, Formula operacional, Meta, Atual, % Atingimento, Dono |
| KPIs Camada A | Linhas 6 a 10, fixos |
| KPIs Camada B | Linhas 11 a 15, placeholders B1..B5 |
| Formula de atingimento | `=IFERROR(F{linha}/E{linha};"")` via API |
| Rituais | Linhas 17 a 20, com placeholders `{{01_RITUAL_DAILY}}`, `{{01_RITUAL_WEEKLY}}`, `{{01_RITUAL_1_1}}` |

Inferencia:

- A aba `KPIs` deve ser preservada como nucleo do F2. A evolucao nao deve trocar a logica A:H, porque ela ja sustenta KPIs Camada A, Camada B e futura coerencia com ROI.
- A divergencia de rituais deve ser resolvida documentando os placeholders no contrato do F2, nao removendo o bloco do template.

## Referencia de PROSPECCAO observada

Fato confirmado:

- O arquivo de referencia tem nome `Etapas do processo de Vendas -- B2B_WinningSales.xlsx`.
- O MIME type e `application/vnd.openxmlformats-officedocument.spreadsheetml.sheet`.
- O workbook foi baixado como `.xlsx` e parseado localmente.
- O workbook tem 9 abas:
  - `INÍCIO`
  - `DIAGNÓSTICO`
  - `ANATOMIA`
  - `PROSPECÇÃO`
  - `LOW TOUCH`
  - `MID TOUCH`
  - `HIGH TOUCH`
  - `PÓS-VENDA`
  - `REFERÊNCIA`
- A aba `PROSPECÇÃO` nao contem formulas.
- A aba `PROSPECÇÃO` contem dois funis:
  - Inbound: `Lead recebido`, `Qualificando`, `Reuniao agendada`, `Desqualificado`.
  - Outbound: `Novo lead`, `Em trabalho`, `Respondido`, `Reuniao agendada`, `Desqualificado`.
- Para cada etapa de prospeccao, a referencia traz:
  - Objetivo;
  - Acoes;
  - Saida Obrigatoria;
  - Campos Obrigatorios;
  - SLA de Tempo;
  - Responsavel.
- O ponto de conexao entre prospeccao e vendas e `Reuniao Agendada`.
- A variacao Low/Mid/High nao esta dentro da aba `PROSPECÇÃO`; ela aparece na aba `DIAGNÓSTICO` e nas abas de pipeline.
- A aba `DIAGNÓSTICO` usa tres variaveis para classificar complexidade:
  - Ticket medio;
  - Ciclo de venda;
  - Numero de decisores.

Fato confirmado sobre divergencia interna da referencia:

| Item | Aba `DIAGNÓSTICO` | Aba de pipeline |
|---|---|---|
| Low touch | Diz `2 etapas` | Aba `LOW TOUCH` tem 3 etapas |
| Mid touch | Diz `3 etapas` | Aba `MID TOUCH` tem 4 etapas |
| High touch | Diz `5 etapas` | Aba `HIGH TOUCH` tem 6 etapas |

Inferencia:

- Para a Wave 4 do F2, a parte util da referencia e a estrutura de PROSPECCAO e a regua simples de complexidade. Nao e seguro copiar a logica completa das abas de pipeline para o F2.
- A divergencia de quantidade de etapas reforca que Low/Mid/High deve entrar como decisao de contexto e nao como motor dinamico de formulas dentro da planilha.

## Opcoes comparadas

### Opcao 1 - Aba dinamica com seletor

Estrutura:

- Manter uma aba de prospeccao com seletor `Low/Mid/High`.
- Usar formulas, validacoes ou ranges auxiliares para adaptar conteudo.

Fato confirmado:

- A referencia nao usa formulas na aba `PROSPECÇÃO`.
- O F2 atual usa formulas simples apenas para `% Atingimento`.

Inferencia:

- Esta opcao adiciona complexidade onde a referencia nao tem complexidade.
- Aumenta risco de quebra em Google Sheets, fallback manual e validacao pelo Reviewer.
- Dificulta explicar ao consultor o que foi entregue.

Veredito:

- Nao recomendada.

### Opcao 2 - Tres abas separadas Low/Mid/High

Estrutura:

- Criar `PROSPECÇÃO - Low`, `PROSPECÇÃO - Mid` e `PROSPECÇÃO - High`.
- Orientar o squad/consultor a excluir as duas abas nao aplicaveis.

Fato confirmado:

- A aba `PROSPECÇÃO` da referencia nao varia por Low/Mid/High.
- A variacao Low/Mid/High esta nas abas de pipeline, nao no funil de prospeccao.

Inferencia:

- Tres abas duplicariam quase o mesmo conteudo.
- A regra de excluir duas abas cria risco operacional: o consultor pode entregar abas erradas ao cliente ou esquecer de limpar.
- A manutencao fica mais cara sem ganho claro.

Veredito:

- Nao recomendada para F2 v2.

### Opcao 3 - Solucao simples recomendada

Estrutura:

- Preservar a aba `KPIs`.
- Adicionar uma unica aba `PROSPECÇÃO`.
- Na aba `PROSPECÇÃO`, manter conteudo estatico e client-facing com:
  - bloco curto de complexidade aplicada;
  - regua Low/Mid/High apenas como referencia de classificacao;
  - funil Inbound;
  - funil Outbound;
  - regra de handoff para vendas.
- Preencher poucos placeholders de contexto, sem seletor dinamico.

Inferencia:

- Esta opcao incorpora a logica util da referencia, evita duplicacao e preserva a auditabilidade do F2.
- A complexidade `Low/Mid/High` vira uma decisao do mini-onboarding e do `decisoes/01-funil-kpis.json`, nao uma formula escondida no template.

Veredito:

- Recomendada.

## Decisao recomendada para F2 v2

Recomendacao objetiva:

> Criar F2 v2 com 2 abas: `KPIs` + `PROSPECÇÃO`. Manter a aba `KPIs` como esta, formalizando os placeholders de rituais. Adicionar `PROSPECÇÃO` como aba unica, estatica e editavel, com classificacao Low/Mid/High preenchida por decisao do mini-onboarding e com funis Inbound/Outbound derivados da referencia.

Regra de decisao:

- Nao usar seletor dinamico.
- Nao criar 3 abas Low/Mid/High.
- Nao copiar abas de pipeline, pos-venda, referencia ou anatomia para o F2.
- Nao alterar KPIs Camada A existentes.
- Usar PROSPECCAO para enriquecer Camada B e operacao comercial, nao para substituir o contrato atual A:H.

## Mapa de abas proposto

### Aba `KPIs`

Fato confirmado:

- Ja existe e funciona como contrato A:H.

Mudanca proposta:

- Manter estrutura A:H.
- Manter KPIs Camada A.
- Manter slots Camada B.
- Resolver oficialmente rituais no contrato.
- Opcionalmente usar a decisao de complexidade para sugerir KPIs Camada B mais aterrados em prospeccao, sem criar novas colunas.

### Aba `PROSPECÇÃO`

Campos/areas propostos:

| Bloco | Campos | Fonte |
|---|---|---|
| Cabecalho | Cliente, complexidade touch, justificativa curta | Mini-onboarding + perfil |
| Diagnostico simples | Ticket medio, ciclo de venda em dias, decisores envolvidos | Mini-onboarding #01 |
| Regua Low/Mid/High | Ticket, ciclo, decisores | Referencia `.xlsx` aba `DIAGNÓSTICO` |
| Funil Inbound | Etapas + Objetivo, Acoes, Saida Obrigatoria, Campos Obrigatorios, SLA, Responsavel | Referencia `.xlsx` aba `PROSPECÇÃO` |
| Funil Outbound | Etapas + Objetivo, Acoes, Saida Obrigatoria, Campos Obrigatorios, SLA, Responsavel | Referencia `.xlsx` aba `PROSPECÇÃO` |
| Handoff | `Reuniao Agendada` como passagem SDR/BDR -> AE | Referencia `.xlsx` aba `PROSPECÇÃO` |

Inferencia:

- A aba `PROSPECÇÃO` deve ser client-facing, nao um manual interno. Evitar labels como `template`, `agent`, `placeholder`, `regra operacional` ou instrucoes de edicao.

## Variaveis novas propostas

| Variavel | Dono | Origem | Formato | Fallback | Risco |
|---|---|---|---|---|---|
| `ticket_medio_mensal` | Onboarding Agent / Foundation Agent | Mini-onboarding #01 ou CRM/input do consultor | Numero monetario | Perguntar ao consultor | Classificacao touch errada |
| `ciclo_venda_dias` | Onboarding Agent / Foundation Agent | Mini-onboarding #01 ou CRM/input do consultor | Inteiro em dias | Perguntar ao consultor | Classificacao touch errada |
| `decisores_envolvidos` | Onboarding Agent / Foundation Agent | Mini-onboarding #01 ou diagnostico comercial | Inteiro | Perguntar ao consultor | High touch subestimado |
| `complexidade_touch` | Foundation Agent | Derivada de ticket, ciclo e decisores, com validacao humana | Enum `low`, `mid`, `high` | Nao preencher final sem confirmacao; usar `a definir` apenas antes da entrega | Entregavel com recomendacao errada |
| `complexidade_justificativa` | Foundation Agent | Sintese dos tres criterios | Texto curto, ate 140 caracteres | Gerar a partir dos dados confirmados | Textao na celula |
| `canais_prospeccao_ativos` | Onboarding Agent / Foundation Agent | Mini-onboarding #01 | Lista: `inbound`, `outbound` ou ambos | Default: ambos, se consultor nao restringir | Entregar funil irrelevante |
| `responsavel_prospeccao` | Foundation Agent / consultor | Perfil comercial ou mini-onboarding | Texto curto | `SDR / BDR` com aprovacao humana | Papel inexistente no cliente |
| `responsavel_handoff` | Foundation Agent / consultor | Perfil comercial ou mini-onboarding | Texto curto | `AE` com aprovacao humana | Handoff sem dono real |
| `rituais.daily` | Foundation Agent | `decisoes/01-funil-kpis.json.rituais` | Texto ate 100 caracteres | Default de daily comercial | Divergencia registry/template |
| `rituais.weekly` | Foundation Agent | `decisoes/01-funil-kpis.json.rituais` | Texto ate 100 caracteres | Default de weekly comercial | Divergencia registry/template |
| `rituais.one_on_one` | Foundation Agent | `decisoes/01-funil-kpis.json.rituais` | Texto ate 100 caracteres | Default de 1:1 comercial | Divergencia registry/template |

Placeholders de template sugeridos:

| Placeholder | Campo |
|---|---|
| `{{01_COMPLEXIDADE_TOUCH}}` | `complexidade_touch` |
| `{{01_COMPLEXIDADE_JUSTIFICATIVA}}` | `complexidade_justificativa` |
| `{{01_TICKET_MEDIO}}` | `ticket_medio_mensal` |
| `{{01_CICLO_VENDA_DIAS}}` | `ciclo_venda_dias` |
| `{{01_DECISORES_ENVOLVIDOS}}` | `decisores_envolvidos` |
| `{{01_CANAIS_PROSPECCAO_ATIVOS}}` | `canais_prospeccao_ativos` |
| `{{01_RESPONSAVEL_PROSPECCAO}}` | `responsavel_prospeccao` |
| `{{01_RESPONSAVEL_HANDOFF}}` | `responsavel_handoff` |
| `{{01_RITUAL_DAILY}}` | `rituais.daily` |
| `{{01_RITUAL_WEEKLY}}` | `rituais.weekly` |
| `{{01_RITUAL_1_1}}` | `rituais.one_on_one` |

## Origem dos dados, dono, formato, fallback e risco

| Dado | Origem primaria | Dono no squad | Formato | Fallback operacional | Risco se faltar |
|---|---|---|---|---|---|
| Estrutura Inbound/Outbound | Referencia `.xlsx`, aba `PROSPECÇÃO` | Foundation Agent aplica no template | Tabela estatica | Manter defaults da referencia | Processo generico demais se cliente nao usa o canal |
| Ticket medio | Mini-onboarding #01 | Onboarding Agent coleta; Foundation Agent usa | Numero em BRL | Pergunta direta ao consultor | Classificacao Low/Mid/High fraca |
| Ciclo de venda | Mini-onboarding #01 | Onboarding Agent coleta; Foundation Agent usa | Dias inteiros | Pergunta direta ao consultor | Classificacao Low/Mid/High fraca |
| Decisores | Mini-onboarding #01 | Onboarding Agent coleta; Foundation Agent usa | Numero inteiro | Pergunta direta ao consultor | High touch subestimado |
| Complexidade touch | Derivacao + validacao humana | Foundation Agent | Enum | Consultor escolhe manualmente | Aba PROSPECÇÃO desalinhada com operacao real |
| Responsaveis | Perfil comercial / mini-onboarding | Foundation Agent | Texto curto | Defaults `SDR / BDR` e `AE` | Handoff sem dono real |
| Rituais | `decisoes/01-funil-kpis.json.rituais` | Foundation Agent | Texto curto | Defaults comerciais aprovados | Placeholder residual ou ritual vazio |
| KPIs Camada B | Produto + prospeccao + metas | Foundation Agent | Nome/definicao/formula/meta/atual/dono | Pedir aprovacao do consultor; limpar B4/B5 se nao usados | KPI generico ou formula quebrada |

## Arquivos/artefatos que precisariam mudar

### Template/sheet

Mudanca necessaria:

- Criar versao sandbox do F2 antes de mexer no master.
- Preservar aba `KPIs`.
- Adicionar aba unica `PROSPECÇÃO`.
- Inserir blocos descritos acima.
- Aplicar identidade Winning Sales coerente com F2 atual.
- Garantir 0 placeholders remanescentes em entrega final.
- Validar que formulas da aba `KPIs` continuam funcionando.

Nao fazer:

- Nao converter a referencia inteira para template F2.
- Nao criar seletor dinamico.
- Nao criar tres abas duplicadas Low/Mid/High.

### `templates/TEMPLATE_REGISTRY.md`

Mudanca necessaria:

- Alterar F2 de `Sheets · 1 aba` para `Sheets · 2 abas`.
- Documentar aba `KPIs` preservada.
- Documentar nova aba `PROSPECÇÃO`.
- Incluir os placeholders de rituais no contrato real do F2.
- Incluir os novos placeholders de complexidade/prospeccao.
- Explicitar que PROSPECÇÃO usa conteudo estatico da referencia `.xlsx` e que Low/Mid/High e decisao do mini-onboarding, nao seletor dinamico.

### `tasks/generate-funnel-kpis.md`

Mudanca necessaria:

- Expandir `decisoes/01-funil-kpis.json` com:
  - `ticket_medio_mensal`;
  - `ciclo_venda_dias`;
  - `decisores_envolvidos`;
  - `complexidade_touch`;
  - `complexidade_justificativa`;
  - `canais_prospeccao_ativos`;
  - `responsavel_prospeccao`;
  - `responsavel_handoff`.
- Mapear placeholders da nova aba `PROSPECÇÃO`.
- Formalizar que rituais tambem existem no F2, nao so no F1.
- Adicionar validacao de que `KPIs!G6:G15` continua calculando.
- Adicionar regra para KPIs Camada B: PROSPECÇÃO pode sugerir KPIs de SLA, conversao e handoff, mas sem substituir a customizacao por produto.

### `checklists/camada-b-01-funil-kpis.md`

Mudanca necessaria:

- Atualizar B2 para reconhecer F2 v2 com `KPIs` + `PROSPECÇÃO`.
- Manter B3/B3.1 para formulas e contrato A:H.
- Atualizar B5 para verificar rituais tambem no Sheets.
- Adicionar item novo sugerido:
  - `B7 - Aba PROSPECÇÃO presente e coerente`: valida Inbound, Outbound, campos obrigatorios, SLA, responsaveis, handoff e complexidade touch.
- Adicionar falha explicita se houver seletor dinamico quebrado, tres abas duplicadas nao limpas ou instrucao interna visivel.

### Mini-onboarding / decisoes do entregavel

Mudanca necessaria:

- Atualizar `tasks/run-mini-onboarding.md` para #01 com ate 3 perguntas:
  1. `Pela regua de ticket/ciclo/decisores, recomendo {low|mid|high}. Confirma ou ajusta?`
  2. `Para este cliente, prospeccao ativa Inbound, Outbound ou ambos?`
  3. `Mantemos responsaveis padrao SDR/BDR -> AE e rituais default, ou ajusta algum dono/ritual?`
- Atualizar `skills/mini-onboarding-pattern.md` na linha de #1 para incluir complexidade touch e prospeccao Inbound/Outbound.
- Definir no `decisoes/01-funil-kpis.json` a estrutura acima antes de gerar F2.

### Agent/skill

Mudanca recomendada:

- Nao alterar `agents/foundation-agent.md` neste momento. Ele ja delega as regras especificas do #01 para a task.
- Nao alterar `skills/find-replace-placeholders.md`.
- Nao alterar `skills/identidade-visual-dupla.md`.
- Alterar somente `skills/mini-onboarding-pattern.md` se a decisao for tornar Low/Mid/High parte oficial do mini-onboarding #01.

Inferencia:

- O menor conjunto de mudancas canonicas e: template F2, registry F2, `generate-funnel-kpis.md`, `camada-b-01-funil-kpis.md`, `run-mini-onboarding.md` e `mini-onboarding-pattern.md`.

## Resolucao da divergencia de rituais

Fato confirmado:

- O template real F2 tem placeholders de rituais em `KPIs!D18:D20`.
- O registry F2 atual nao documenta esses placeholders.
- A task `generate-funnel-kpis.md` ja declara `rituais` em `decisoes/01-funil-kpis.json`.
- O checklist B5 aceita rituais em Slides ou Sheets.

Decisao recomendada:

- Manter os rituais no F2.
- Atualizar `templates/TEMPLATE_REGISTRY.md` para declarar:
  - `{{01_RITUAL_DAILY}}`
  - `{{01_RITUAL_WEEKLY}}`
  - `{{01_RITUAL_1_1}}`
- Atualizar `tasks/generate-funnel-kpis.md` para preencher esses placeholders explicitamente no F2.
- Atualizar checklist para reprovar placeholder de ritual remanescente em entrega final.

Inferencia:

- Remover os rituais do template seria uma correcao mais arriscada, porque o checklist ja espera rituais e a task ja possui o input `rituais`.

## Bloqueios antes de implementar

| Bloqueio | Motivo | Resolucao esperada |
|---|---|---|
| Aprovacao da decisao F2 v2 | Runtime e master Sheet nao podem ser alterados sem aprovacao | Thiago aprovar a estrutura `KPIs` + `PROSPECÇÃO` |
| Aprovacao para criar/editar sandbox do Sheet | O pedido atual permite analise/contrato; mudanca no Sheet deve ser proposta antes | Criar copia sandbox do F2 e validar antes do master |
| Schema de `decisoes/01-funil-kpis.json` | Hoje nao ha schema explicito para os novos campos | Aprovar campos de complexidade/prospeccao |
| Divergencia interna da referencia sobre numero de etapas | Diagnostico e abas Low/Mid/High divergem | Usar apenas a regua de classificacao e nao copiar pipeline |
| Fonte de `Atual` dos KPIs | Wave 3 ja marcou como lacuna | Definir CRM, input manual, baseline ou vazio controlado |
| Timezone `America/Los_Angeles` | Nao bloqueia hoje, mas pode afetar datas futuras | Nao adicionar formulas de data agora; revisar se houver datas |
| Portabilidade MCP | Codex connector confirmado; `workspace-mcp` ainda a testar | Manter fallback manual documentado |

## Proximo passo objetivo

1. Thiago aprovar ou ajustar a decisao: F2 v2 com `KPIs` + `PROSPECÇÃO`.
2. Com aprovacao, criar uma copia sandbox do F2 no Drive.
3. Aplicar a aba `PROSPECÇÃO` na copia sandbox.
4. Atualizar runtime em branch/patch pequeno:
   - `templates/TEMPLATE_REGISTRY.md`;
   - `tasks/generate-funnel-kpis.md`;
   - `checklists/camada-b-01-funil-kpis.md`;
   - `tasks/run-mini-onboarding.md`;
   - `skills/mini-onboarding-pattern.md`.
5. Rodar QA Wave 6 para F2 v2 antes de mexer no master final.

## Registro pos-aprovacao

Data: 2026-05-18.

Fato confirmado:

- Thiago aprovou a decisao F2 v2 com `KPIs` + `PROSPECÇÃO`.
- Foi criada uma copia sandbox do F2:
  - `Sandbox Wave 4 - F2 master-kpis-sheet-winning v2`
  - https://docs.google.com/spreadsheets/d/1TtoiNQHHr3e5okgSAVYofG5qs53UoCLFEDjQMnKHle8/edit
- A sandbox tem 2 abas:
  - `KPIs`
  - `PROSPECÇÃO`
- A aba `KPIs` foi copiada do master e manteve as formulas `=IFERROR(F{linha}/E{linha};"")` em `G6:G15`.
- A aba `PROSPECÇÃO` foi criada como aba unica, estatica e editavel, sem seletor dinamico e sem tres abas Low/Mid/High.
- O master `13YLWDeRIXpo7iHaM4N4JCdn3yx17fGiKAJ5bJZvYebo` nao foi alterado.
- Os seguintes arquivos do runtime foram atualizados:
  - `07-Runtime-Squad/templates/TEMPLATE_REGISTRY.md`
  - `07-Runtime-Squad/tasks/generate-funnel-kpis.md`
  - `07-Runtime-Squad/checklists/camada-b-01-funil-kpis.md`
  - `07-Runtime-Squad/tasks/run-mini-onboarding.md`
  - `07-Runtime-Squad/skills/mini-onboarding-pattern.md`
- Validacoes locais executadas:
  - `node scripts/validate-template-registry.js` passou.
  - `node scripts/validate-template-registry.js --require-p0` passou.
  - `node scripts/validate-template-registry.js --strict-drive-ids` passou.
  - `node scripts/validate-platform-compatibility.js` passou.
- Nao ha `package.json` na raiz do cockpit nem em `07-Runtime-Squad/`; por isso `npm run lint`, `npm run typecheck` e `npm test` nao foram aplicaveis nesta execucao.

Inferencia:

- O proximo gate adequado e Wave 6 na sandbox, antes de promover a estrutura para o master F2.
