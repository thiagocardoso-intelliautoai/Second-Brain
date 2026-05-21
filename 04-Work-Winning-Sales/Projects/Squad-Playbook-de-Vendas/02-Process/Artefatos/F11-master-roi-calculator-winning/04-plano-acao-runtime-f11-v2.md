---
created_at: 2026-05-20
updated_at: 2026-05-20
status: plano-runtime-pronto
wave: "pos-qa-F11-W6"
scope: plano-acao-runtime-f11-v2
artifact: F11 master-roi-calculator-winning
source_doc: "03-qa-f11-w6-sandbox.md"
sandbox_id: "1OWeAadbcnuqcjXVtx8-6S16XAbgKnT4S2NkKwQWu8Zw"
sandbox_url: "https://docs.google.com/spreadsheets/d/1OWeAadbcnuqcjXVtx8-6S16XAbgKnT4S2NkKwQWu8Zw/edit?usp=sharing"
runtime_modified: false
drive_modified: false
master_modified: false
story_mirror: "07-stories-espelho.md#f11-s02---sandbox-e-qa-f11-w6"
---

# Plano de Acao Runtime F11 v2

## Nota de governanca - 2026-05-21

Este plano historico agora esta espelhado pela story `F11-S02` em `07-stories-espelho.md`.

## Objetivo

Preparar a atualizacao do runtime para que o entregavel #09 gere a nova Calculadora ROI F11 v2 aprovada em sandbox, com 7 abas, 3 alavancas de valor, cenarios, dashboard e saidas tecnicas `RESUMO_*`.

Este plano **nao altera o runtime ainda**. Ele define ordem, arquivos alvo, criterio de aceite e riscos para uma execucao posterior.

## Fonte aprovada

| Campo | Valor |
|---|---|
| QA aprovado | `03-qa-f11-w6-sandbox.md` |
| Sandbox aprovada | `Sandbox F11 v2 - master-roi-calculator-winning - REF-02 base` |
| ID | `1OWeAadbcnuqcjXVtx8-6S16XAbgKnT4S2NkKwQWu8Zw` |
| URL | `https://docs.google.com/spreadsheets/d/1OWeAadbcnuqcjXVtx8-6S16XAbgKnT4S2NkKwQWu8Zw/edit?usp=sharing` |
| Veredito QA | Sim, aprovada como template/sandbox |

## Principio de atualizacao

Nao atualizar o ID oficial do F11 no registry para a sandbox sem uma decisao separada de promocao.

Primeiro o runtime deve aprender o contrato F11 v2; depois a promocao do master pode ser decidida com outro gate.

## Arquivos alvo

| Arquivo | Tipo de mudanca | Motivo |
|---|---|---|
| `07-Runtime-Squad/templates/TEMPLATE_REGISTRY.md` | Atualizar contrato F11 de 4 para 7 abas ou registrar F11 v2 como contrato aprovado pendente de promocao. | Hoje o registry ainda descreve 4 abas e modelo estreito de tickets/horas. |
| `07-Runtime-Squad/tasks/generate-roi-calculator.md` | Reescrever task #09 para F11 v2. | Hoje a task fala em 4 abas e 4 mini-pausas. |
| `07-Runtime-Squad/checklists/camada-b-09-calculadora-roi.md` | Atualizar checklist B09 para 7 abas e QA de sandbox/template + caso real. | Hoje o checklist valida 4 abas e nao cobre capa, cenarios, dashboard e saidas tecnicas. |
| `07-Runtime-Squad/tasks/run-mini-onboarding.md` | Expandir perguntas/defaults do #09. | O mini-onboarding atual pede volume, baseline operacional e pricing; F11 v2 precisa receita, custo, risco, investimento, prazo e fonte. |
| `07-Runtime-Squad/skills/mini-onboarding-pattern.md` | Atualizar variacao do #9. | A skill ainda declara 4 abas fixas e formulas inferidas. |
| `07-Runtime-Squad/checklists/camada-c-cross-deliverable.md` | Opcional. Adicionar cross-check entre #09, deck/proposta e aviso comercial. | Garante que `RESUMO_*` seja consumido sem promessa indevida. |

## Contrato F11 v2 a refletir

### Estrutura de abas

1. `1. Capa`
2. `2. Inputs`
3. `3. Motor de Calculo`
4. `4. Resumo Executivo`
5. `5. Cenarios`
6. `6. Dashboard`
7. `7. Saidas tecnicas`

### Inputs oficiais do #09

Identificacao:

- `{{NOME_CLIENTE}}`
- `{{09_SEGMENTO_INDUSTRIA}}`
- `{{NOME_PRODUTO}}`
- periodicidade/prazo de analise
- `{{09_INVESTIMENTO_TOTAL}}`

Receita:

- `{{09_RECEITA_ATUAL_PERIODO}}`
- `{{09_LEADS_ATUAIS_PERIODO}}`
- `{{09_CONVERSAO_ATUAL}}`
- `{{09_TICKET_MEDIO_ATUAL}}`
- `{{09_MARGEM_BRUTA_ATUAL}}`
- respectivos valores futuros/esperados

Custo:

- `{{09_CUSTO_OPERACIONAL_ATUAL}}`
- `{{09_HORAS_TIME_ATUAL}}`
- `{{09_CUSTO_HORA_TIME_ATUAL}}`
- `{{09_VOLUME_ATIVIDADES_ATUAL}}`
- `{{09_CUSTO_UNITARIO_ATUAL}}`
- respectivos valores futuros/esperados

Risco:

- `{{09_PROB_RISCO_ATUAL}}`
- `{{09_IMPACTO_RISCO_ATUAL}}`
- `{{09_CUSTO_EVITADO_ADICIONAL_ATUAL}}`
- respectivos valores futuros/esperados

### Saidas tecnicas obrigatorias

Manter compatibilidade:

- `RESUMO_USUARIOS`
- `RESUMO_PAYBACK`
- `RESUMO_ROI_ANO_1`
- `RESUMO_REDUCAO_TICKETS`
- `RESUMO_ECONOMIA_ANUAL`
- `RESUMO_FRASE_FINAL`

Adicionar/validar como saidas preferenciais do F11 v2:

- `RESUMO_CLIENTE`
- `RESUMO_PRODUTO`
- `RESUMO_GANHO_BRUTO`
- `RESUMO_GANHO_LIQUIDO`
- `RESUMO_INVESTIMENTO`
- `RESUMO_ALAVANCA_PRINCIPAL`
- `RESUMO_CLASSIFICACAO_IMPACTO`
- `RESUMO_AVISO_COMERCIAL`

## Mudancas por arquivo

### `TEMPLATE_REGISTRY.md`

Atualizar a secao F11 para:

- declarar 7 abas aprovadas na sandbox F11 v2;
- manter locale `pt_BR` e timezone `America/Sao_Paulo`;
- declarar que placeholders sem premissa real devem produzir vazio, zero seguro ou `A definir`;
- declarar cenarios Conservador/Base/Otimista como analise de sensibilidade, nao promessa;
- declarar `7. Saidas tecnicas` como contrato de consumo por deck/proposta;
- registrar nota historica: F11 v2 aprovado em sandbox no QA F11-W6, master ainda pendente de promocao.

Decisao pendente:

- manter o Drive ID atual do master ate promocao, ou trocar o ID oficial para a sandbox aprovada quando Thiago autorizar promocao.

### `generate-roi-calculator.md`

Reescrever a task #09 para:

- trocar "4 abas" por "7 abas";
- trocar modelo estreito de tickets/horas por 3 alavancas: receita, custo e risco;
- exigir mini-pausas por bloco:
  - Inputs;
  - Motor de calculo;
  - ROI/payback/classificacao;
  - Resumo executivo;
  - Cenarios;
  - Dashboard;
  - Saidas tecnicas;
- exigir teste com dados reais antes de liberar frases comerciais;
- exigir aviso comercial visivel;
- exigir que formulas tolerem placeholders no template e validem plausibilidade no caso real.

### `camada-b-09-calculadora-roi.md`

Atualizar checklist para:

- separar QA de template/sandbox e QA de caso real;
- validar as 7 abas;
- validar inputs das 3 alavancas;
- validar formulas sem erro com placeholders;
- validar ROI/payback com dados reais;
- validar cenarios sem inflar ROI artificialmente;
- validar dashboard executivo;
- validar `RESUMO_*`;
- validar mini-pausas obrigatorias no runtime;
- validar locale/timezone e visual.

### `run-mini-onboarding.md`

Atualizar linha do #09 para propor defaults e perguntar no maximo 3 blocos:

- quais alavancas entram no caso: receita, custo, risco ou combinacao;
- quais premissas reais existem e quais devem ser estimadas com fonte;
- investimento total, periodicidade e criterio de payback esperado.

Evitar perguntar de novo o que ja estiver em `perfil.json`, #01 ou vault.

### `mini-onboarding-pattern.md`

Atualizar variacao do #9 para:

- "7 abas";
- "3 alavancas de valor";
- "perguntas direcionadas com defaults por setor/produto";
- "avisar que cenario e estimativa comercial, nao garantia".

### `camada-c-cross-deliverable.md` opcional

Adicionar gate para:

- deck/proposta puxar `RESUMO_*` da calculadora sem inventar ROI;
- proposta manter premissas e aviso comercial;
- F2/#01 alimentar premissas quando existir;
- se `RESUMO_FRASE_FINAL` estiver em estado de preenchimento, deck/proposta nao deve usar frase comercial.

## Ordem de execucao sugerida

1. Confirmar com Thiago se a atualizacao agora sera apenas runtime-docs ou tambem promocao do master F11.
2. Se for apenas runtime-docs, aplicar patch local nos arquivos de runtime sem alterar Drive ID oficial.
3. Se houver promocao, decidir antes se o ID oficial passara a ser a sandbox aprovada ou se o master atual sera substituido por outro procedimento.
4. Atualizar `TEMPLATE_REGISTRY.md`.
5. Atualizar `generate-roi-calculator.md`.
6. Atualizar `camada-b-09-calculadora-roi.md`.
7. Atualizar mini-onboarding em `run-mini-onboarding.md` e `mini-onboarding-pattern.md`.
8. Rodar validacoes locais disponiveis no repo.
9. Rodar geracao/QA de um caso real ou fixture antes de declarar runtime pronto.

## Validacoes recomendadas apos patch

- Buscar referencias antigas a F11 como "4 abas".
- Buscar referencias antigas a tickets/horas como modelo unico.
- Verificar se `RESUMO_*` novo e legado aparecem no contrato.
- Validar que mini-pausas do #09 cobrem 7 blocos.
- Validar que a task diferencia template com placeholders de caso real preenchido.
- Rodar qualquer script local de validacao do registry se existir.
- Fazer smoke test manual/assistido de geracao #09 com dados ficticios plausiveis.

## Definition of Done da atualizacao runtime

O runtime so fica pronto quando:

- registry, task, checklist e mini-onboarding estiverem coerentes entre si;
- F11 v2 estiver descrito como 7 abas;
- inputs de receita, custo e risco estiverem contratados;
- formulas com placeholders forem tratadas como estado seguro;
- QA de caso real exigir plausibilidade numerica;
- deck/proposta tiver caminho seguro via `RESUMO_*`;
- master F11 ou sandbox oficial estiverem claramente identificados;
- nao houver contradicao ativa dizendo que F11 ainda tem apenas 4 abas.

## Risco principal

Atualizar o runtime antes de decidir promocao do master pode criar divergencia entre contrato e Drive ID oficial.

Mitigacao:

- registrar explicitamente no registry que F11 v2 foi aprovado em sandbox e que a promocao do ID oficial e gate separado; ou
- promover a sandbox como master em execucao separada antes de trocar o contrato definitivo.

## Proximo passo

Usar o plano combinado `05-plano-execucao-promocao-runtime-f11-v2.md` como documento de origem da proxima execucao.
