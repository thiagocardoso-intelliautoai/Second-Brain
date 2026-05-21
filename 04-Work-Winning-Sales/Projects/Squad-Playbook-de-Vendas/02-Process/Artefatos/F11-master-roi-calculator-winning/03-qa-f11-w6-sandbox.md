---
created_at: 2026-05-20
updated_at: 2026-05-20
status: aprovada-sandbox
wave: "6-F11"
scope: qa-completo-sandbox
artifact: F11 master-roi-calculator-winning
source_doc: "02-sandbox-f11-v2-execucao.md"
sandbox_id: "1OWeAadbcnuqcjXVtx8-6S16XAbgKnT4S2NkKwQWu8Zw"
sandbox_url: "https://docs.google.com/spreadsheets/d/1OWeAadbcnuqcjXVtx8-6S16XAbgKnT4S2NkKwQWu8Zw/edit?usp=sharing"
verdict: "Sim"
runtime_modified: false
drive_modified: false
master_modified: false
story_mirror: "07-stories-espelho.md#f11-s02---sandbox-e-qa-f11-w6"
---

# QA F11-W6 - Sandbox F11 v2

## Nota de governanca - 2026-05-21

Este QA historico agora esta espelhado pela story `F11-S02` em `07-stories-espelho.md`.

## Objetivo

Executar o QA completo da sandbox F11 v2 antes de qualquer promocao para master ou atualizacao de runtime.

Este documento valida a sandbox como **template F11 v2 aprovado para evolucao de runtime**, nao como calculadora final preenchida para um cliente real. A geracao final ainda deve rodar mini-onboarding, preencher premissas reais e passar por QA de caso.

## Alvo validado

| Campo | Valor |
|---|---|
| Spreadsheet | `Sandbox F11 v2 - master-roi-calculator-winning - REF-02 base` |
| ID | `1OWeAadbcnuqcjXVtx8-6S16XAbgKnT4S2NkKwQWu8Zw` |
| URL | `https://docs.google.com/spreadsheets/d/1OWeAadbcnuqcjXVtx8-6S16XAbgKnT4S2NkKwQWu8Zw/edit?usp=sharing` |
| Locale | `pt_BR` |
| Timezone | `America/Sao_Paulo` |
| Comentarios ativos | Nenhum |
| Master F11 alterado | Nao |
| REF-02 original alterada | Nao |
| Runtime alterado | Nao |

## Escopo executado

Executado:

- leitura de metadata da sandbox;
- leitura de comentarios ativos;
- leitura de ranges principais das 7 abas;
- validacao de placeholders oficiais do #09;
- validacao de formulas principais enquanto inputs ainda estao como placeholders;
- validacao de payback, ROI, classificacao e resumo sem premissas reais;
- validacao da aba `7. Saidas tecnicas` e do bloco `RESUMO_*`;
- registro do veredito Sim/Nao.

Nao executado:

- nenhuma edicao adicional na sandbox durante este QA;
- nenhuma alteracao no master F11;
- nenhuma alteracao na REF-02 original;
- nenhuma alteracao de registry, task, checklist ou mini-onboarding;
- nenhuma promocao de master.

## Evidencias lidas

### Abas presentes

| Ordem | Aba |
|---:|---|
| 1 | `1. Capa` |
| 2 | `2. Inputs` |
| 3 | `3. Motor de Calculo` |
| 4 | `4. Resumo Executivo` |
| 5 | `5. Cenarios` |
| 6 | `6. Dashboard` |
| 7 | `7. Saidas tecnicas` |

### Ranges usados no QA

| Aba | Range |
|---|---|
| `1. Capa` | `B2:F38` |
| `2. Inputs` | `B7:F37` |
| `3. Motor de Calculo` | `B7:F32` |
| `4. Resumo Executivo` | `B5:F31` |
| `5. Cenarios` | `B6:F20` |
| `6. Dashboard` | `B6:H42` |
| `7. Saidas tecnicas` | `A1:D18` |

## Checklist F11-W6

| Criterio | Resultado | Evidencia |
|---|---|---|
| B1 - Inputs contratados | Pass | Aba `2. Inputs` usa placeholders oficiais do #09 para cliente, segmento, produto, investimento, receita, custo e risco. |
| B1 - Inputs plausiveis para cliente real | Condicionado | Como sandbox/template, os valores reais ainda nao existem. O runtime deve preencher via mini-onboarding antes de entrega. |
| B2 - Impacto por alavancas | Pass | Modelo cobre aumento de receita, reducao de custo e reducao de risco, superando o recorte antigo de tickets/horas. |
| B2 - Formulas customizaveis | Pass | Motor exibe formulas por alavanca e usa entradas tolerantes a placeholders nos pontos criticos. |
| B3 - ROI e payback | Pass | Com placeholders, ROI/payback ficam vazios ou neutros; nao aparecem `#ERROR!`, `#VALUE!` ou `#DIV/0!` nos ranges lidos. |
| B3 - Classificacao de impacto | Pass | Sem premissas, classificacao fica `A definir`, evitando recomendacao comercial falsa. |
| B4 - Resumo executivo | Pass | Aba `4. Resumo Executivo` retorna mensagens de preenchimento enquanto faltam premissas, sem prometer resultado indevido. |
| B4 - Saidas tecnicas `RESUMO_*` | Pass | Aba `7. Saidas tecnicas` contem chaves `RESUMO_*` para proposta/deck e campos adicionais de cliente, produto, ganho, investimento, alavanca, classificacao e aviso. |
| B5 - Mini-pausas | Condicionado | Nao se aplica a sandbox estatica. Deve ser requisito obrigatorio no runtime de geracao do #09. |
| B6 - Identidade visual | Pass | Estrutura da REF-02 foi preservada com capa, convencao de cores, motor, cenarios, dashboard e aviso comercial. |
| B7 - Locale/timezone | Pass | Metadata validada em `pt_BR` e `America/Sao_Paulo`. |
| B8 - Visual usavel | Pass | As 7 abas estao organizadas por uso executivo/tecnico e nao nasceram como import cru. |

## Saidas tecnicas confirmadas

O bloco `7. Saidas tecnicas!A4:D18` contem:

- `RESUMO_USUARIOS`
- `RESUMO_PAYBACK`
- `RESUMO_ROI_ANO_1`
- `RESUMO_REDUCAO_TICKETS`
- `RESUMO_ECONOMIA_ANUAL`
- `RESUMO_FRASE_FINAL`
- `RESUMO_CLIENTE`
- `RESUMO_PRODUTO`
- `RESUMO_GANHO_BRUTO`
- `RESUMO_GANHO_LIQUIDO`
- `RESUMO_INVESTIMENTO`
- `RESUMO_ALAVANCA_PRINCIPAL`
- `RESUMO_CLASSIFICACAO_IMPACTO`
- `RESUMO_AVISO_COMERCIAL`

Valores observados sem premissas reais:

- `RESUMO_FRASE_FINAL`: `Preencher premissas de valor para gerar o resumo executivo.`
- `RESUMO_ALAVANCA_PRINCIPAL`: `A definir`
- `RESUMO_CLASSIFICACAO_IMPACTO`: `A definir`

## Achados residuais

| Severidade | Achado | Impacto | Tratamento |
|---|---|---|---|
| Baixa | O dashboard ainda tem formulas de exposicao ao risco com referencia direta a inputs, protegidas por `IFERROR`. | Nao quebra o template com placeholders, mas fica menos padronizado que o motor com `N(...)`. | Padronizar para `N(...)` quando atualizar runtime ou antes de promover master. |
| Baixa | `RESUMO_USUARIOS` e `RESUMO_REDUCAO_TICKETS` continuam como compatibilidade legado. | O F11 v2 e mais amplo que tickets/usuarios. | Manter por compatibilidade com deck/proposta e acrescentar campos novos como fonte preferencial. |
| Media | QA foi feito como sandbox/template, nao como caso real preenchido. | Nao prova plausibilidade numerica de um cliente especifico. | Runtime deve exigir mini-onboarding e QA de premissas antes da entrega final. |
| Media | A resposta de criacao dos named ranges foi confirmada no batch anterior, mas a ferramenta de metadata usada no QA nao listou named ranges. | Baixo risco porque o bloco tecnico foi lido e os nomes foram criados na execucao. | Revalidar named ranges numa etapa de promocao/runtime, se a ferramenta listar essa propriedade. |

## Veredito

**Sim.**

A sandbox F11 v2 esta aprovada como base para plano de atualizacao do runtime.

Liberado:

- criar plano de acao para atualizar runtime;
- preparar patch local em registry/task/checklist/mini-onboarding quando Thiago autorizar;
- usar a sandbox como referencia aprovada da estrutura F11 v2.

Nao liberado por este QA:

- promover a sandbox como master oficial;
- editar o master F11 atual;
- alterar runtime sem execucao separada;
- entregar calculadora final a cliente sem premissas reais e mini-onboarding.

## Proximo passo

Aguardar autorizacao explicita para executar o plano de acao runtime F11 v2 ou abrir uma execucao separada de promocao do master.
