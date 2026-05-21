---
created_at: 2026-05-20
updated_at: 2026-05-20
status: promocao-runtime-concluida
wave: "3-F11"
scope: contrato-e-frente-roi
artifact: F11 master-roi-calculator-winning
target_drive_id: "1OWeAadbcnuqcjXVtx8-6S16XAbgKnT4S2NkKwQWu8Zw"
historical_master_id: "1CxI8RtqZifigfam7PhBA8NZVlaorLRSM9cTDUwbL5UY"
reference_drive_id: "16GiuEoJHGkJeiEwxKmKxnDHK5zAdrPJkVP77hB4A5vs"
source_story: "02-Process/Artefatos/F1-master-funnel-diagram-winning/04-stories-sm.md#story-7"
runtime_modified: true
drive_modified: false
mode: read-only-documento-de-origem
execution_doc: "06-registro-promocao-runtime-f11-v2.md"
stories_mirror: "07-stories-espelho.md"
---

# Wave 3 - F11 Contrato e Frente ROI

## Nota de governanca - 2026-05-21

Esta frente historica agora esta espelhada em `07-stories-espelho.md`:

- `F11-S01`: auditoria read-only e rota F11 v2.
- `F11-S02`: sandbox e QA F11-W6.
- `F11-S03`: promocao e runtime F11 v2.

Para nova execucao de F11, criar story nova. Nao reexecutar esta frente sem motivo novo.

## Objetivo

Criar o documento proprio da frente F11/ROI antes de qualquer alteracao no `master-roi-calculator-winning`.

Esta wave e o documento de origem da execucao F11. A Story 7 do F1 continua existindo apenas como ponte historica/backlog, mas nao autoriza execucao no ROI.

## Decisao de formato

Formato escolhido: **wave propria**.

Motivo:

- F11 e Google Sheets, assim como F2.
- A evolucao deve seguir o mesmo ciclo de controle usado em F2: contrato/read-only -> sandbox -> QA -> promocao.
- A REF-02 e benchmark direto de ROI, nao insumo de F1.
- Qualquer mudanca pode afetar formulas, named ranges, resumo executivo, proposta/deck e coerencia com KPIs do #01.

## Escopo desta wave

Inclui:

- declarar escopo, fontes, permissao de Drive, criterios de pronto e QA esperado;
- registrar F11 como frente separada;
- preparar a auditoria read-only do master atual e da REF-02;
- definir a matriz de decisao para duplicar, substituir ou adaptar o master;
- separar o que e fato confirmado do que ainda precisa de leitura.

Nao inclui:

- editar o master F11;
- copiar, substituir, renomear ou mover arquivo no Drive;
- alterar formulas, abas, named ranges ou runtime;
- mexer no F1;
- tratar a REF-02 como mudanca ja aprovada.

## Artefatos envolvidos

| Papel | Artefato | ID / URL | Estado |
|---|---|---|---|
| F11 oficial atual | F11 `master-roi-calculator-winning` | `1OWeAadbcnuqcjXVtx8-6S16XAbgKnT4S2NkKwQWu8Zw` | Promovido por registry em 2026-05-20 |
| Master historico pre-promocao | F11 `master-roi-calculator-winning` | `1CxI8RtqZifigfam7PhBA8NZVlaorLRSM9cTDUwbL5UY` | ID oficial ate a promocao; preservado como historico |
| Referencia principal | REF-02 `Calculadora_ROI_WinningSales` | `16GiuEoJHGkJeiEwxKmKxnDHK5zAdrPJkVP77hB4A5vs` | Benchmark ROI, separado do F1 |
| Pasta Drive | `Templates Master/09-calculadora-roi` | `1LVbSUh_jXaB9HkJ1ixgTur_A2Wd5itvw` | Pasta declarada no registry |
| Ponte historica | Story 7 do F1 | `04-stories-sm.md` | Nao autoriza execucao; aponta para esta frente |

Links:

- F11 oficial atual: `https://docs.google.com/spreadsheets/d/1OWeAadbcnuqcjXVtx8-6S16XAbgKnT4S2NkKwQWu8Zw/edit`
- Master F11 historico: `https://docs.google.com/spreadsheets/d/1CxI8RtqZifigfam7PhBA8NZVlaorLRSM9cTDUwbL5UY/edit`
- REF-02: `https://docs.google.com/spreadsheets/d/16GiuEoJHGkJeiEwxKmKxnDHK5zAdrPJkVP77hB4A5vs/edit`

## Fontes locais usadas para criar este documento

| Fonte | Uso |
|---|---|
| `02-Process/Backlog-Operacional-Atual.md` | Regra de que F11 precisa de documento proprio antes de execucao |
| `02-Process/Artefatos/F1-master-funnel-diagram-winning/04-stories-sm.md` | Story 7 como origem do backlog, nao como execucao suficiente |
| `02-Process/Artefatos/F1-master-funnel-diagram-winning/00-referencias-e-benchmark.md` | Registro da REF-02 e decisao de separar ROI do F1 |
| `07-Runtime-Squad/templates/TEMPLATE_REGISTRY.md` | Contrato declarado do F11, Drive ID, abas, placeholders e formulas esperadas |
| `07-Runtime-Squad/tasks/generate-roi-calculator.md` | Task dona do #09 e ciclo de 4 mini-pausas |
| `07-Runtime-Squad/checklists/camada-b-09-calculadora-roi.md` | Checklist especifico de ROI |
| `02-Process/Wave-3-Contrato-F2-Master-KPIs-Sheet.md` | Dependencia F2 -> F11 por KPIs Camada B |
| `02-Process/Wave-4-F2-Master-KPIs-Sheet-v2.md` | F2 v2 como base atual de KPIs/prospeccao |
| `02-Process/Wave-6-QA-F2-Master-KPIs-Sheet-v2.md` | F2 promovido por registry e smoke test pos-promocao |
| `02-Process/Equacao-de-Valor-ROI-Automacao-Assistida.md` | Insumo contextual sobre ROI da automacao assistida, nao contrato do F11 ainda |

## Fatos confirmados

- F11 existe no registry como `master-roi-calculator-winning`.
- Antes da promocao, o ID oficial do F11 era `1CxI8RtqZifigfam7PhBA8NZVlaorLRSM9cTDUwbL5UY`.
- Depois da promocao de 2026-05-20, o ID oficial do F11 e `1OWeAadbcnuqcjXVtx8-6S16XAbgKnT4S2NkKwQWu8Zw`.
- Antes da promocao, o registry declarava F11 como Sheets nativo com 4 abas:
  - `Inputs`;
  - `Calculo de impacto`;
  - `Calculo de ROI`;
  - `Resumo executivo`.
- O registry espera locale `pt_BR`, timezone `America/Sao_Paulo`, cabecalhos Winning Sales e formulas tolerantes a placeholders.
- A task `generate-roi-calculator.md` trata F11 como entregavel #09, de responsabilidade do `specialty-agent`.
- A task exige 4 mini-pausas: uma por aba.
- O checklist `camada-b-09-calculadora-roi.md` valida inputs, formulas customizadas, ROI, payback, named ranges `RESUMO_*`, locale `pt_BR` e visual usavel.
- A REF-02 foi registrada como benchmark principal de ROI e nao deve entrar no F1.
- Thiago indicou que praticamente tudo da REF-02 esta melhor que o master atual.
- Calculos da REF-02 nao devem ser alterados sem necessidade.

## Hipoteses a validar na auditoria read-only

| Hipotese | Como validar |
|---|---|
| REF-02 pode virar base do F11 v2 | Comparar abas, formulas, named ranges, visual, cenarios e dashboard com o master atual |
| O caminho mais seguro pode ser duplicar/substituir, nao remendar | Mapear esforco e risco de patch incremental vs copia sandbox da referencia |
| Cenarios conservador/base/otimista devem entrar no contrato oficial | Verificar se a REF-02 ja traz estrutura auditavel e se cabe no fluxo do #09 |
| O resumo executivo precisa alimentar proposta/deck sem quebra | Confirmar existencia e formato de `RESUMO_*` ou equivalentes |
| F11 precisa consumir KPIs do F2 v2 | Checar se KPIs Camada B e prospeccao do #01 entram como premissas ou alavancas |
| `Equacao-de-Valor-ROI-Automacao-Assistida.md` e contextual | Decidir se entra como exemplo interno, criterio de sucesso ou fica fora do master F11 |

## Contrato minimo esperado do F11

Antes de aprovar qualquer sandbox ou promocao, a frente F11 precisa confirmar:

| Area | Contrato minimo |
|---|---|
| Abas | 4 abas nativas ou nova estrutura aprovada explicitamente |
| Inputs | Cliente, volume, baseline operacional, custo, investimento e premissas customizadas |
| Impacto | Formulas especificas ao produto/setor, sem reducao generica automatica |
| ROI | Economia mensal/anual, investimento anual, ROI ano 1 e payback |
| Resumo | Campos ou named ranges consumiveis por proposta/deck |
| Cenarios | Se adotados, precisam ser auditaveis e nao inflar ROI artificialmente |
| Placeholders | Sem placeholder sem dono/origem/fallback |
| Formulas | Sem `#ERROR!`, `#VALUE!` ou `#DIV/0!` enquanto houver placeholders |
| Locale | `pt_BR`, formulas parseaveis e valores monetarios legiveis |
| Visual | Cabecalhos Winning, contraste correto, largura/wrap suficientes |
| Cross-deliverable | Coerencia com F2/#01 e com a proposta/deck que consome o resumo |

## Permissao de Drive

Permissao desta atualizacao:

- Criar documento local da frente F11.
- Atualizar backlog local e ponte da Story 7.

Nao autorizado nesta atualizacao:

- ler ou editar o master F11 via conector;
- ler ou editar a REF-02 via conector;
- criar copia sandbox;
- alterar registry, task, checklist ou arquivos de runtime;
- alterar qualquer arquivo no Google Drive.

Permissao necessaria para a proxima execucao:

- leitura read-only do master F11 e da REF-02;
- se a auditoria recomendar, aprovacao explicita separada para criar sandbox;
- aprovacao posterior, tambem separada, para promover qualquer artefato a master.

## Backlog executavel da frente F11

### F11-W3-01 - Auditoria read-only do master atual

Objetivo: ler metadata, abas, ranges, formulas, named ranges e comentarios do F11 oficial.

Criterios de aceite:

- Nenhuma alteracao no Drive.
- Abas reais listadas.
- Formulas criticas inventariadas.
- Placeholders e named ranges mapeados.
- Erros visiveis ou riscos de formula registrados.

### F11-W3-02 - Auditoria read-only da REF-02

Objetivo: entender o que a referencia criou e por que ela e melhor que o master atual.

Criterios de aceite:

- Nenhuma alteracao na REF-02.
- Estrutura de abas/blocos documentada.
- Capa, objetivo, modo de uso, convencao de cores, inputs, alavancas, motor, resumo, cenarios e dashboard classificados.
- Calculos preservados como fonte, salvo erro confirmado.

### F11-W3-03 - Comparacao master atual vs REF-02

Objetivo: decidir o caminho tecnico antes de qualquer sandbox.

Criterios de aceite:

- Matriz `manter / adaptar / substituir / descartar`.
- Riscos por formula, visual, named ranges e cross-deliverable.
- Impacto em registry, task, checklist, mini-onboarding e proposta/deck.
- Recomendacao objetiva: patch incremental, duplicacao da REF-02, sandbox hibrida ou outra rota.

### F11-W3-04 - Decisao de escopo F11 v2

Objetivo: transformar a comparacao em plano aprovado.

Criterios de aceite:

- Escopo do F11 v2 aprovado por Thiago.
- Itens fora de escopo explicitos.
- Permissao de Drive definida: sandbox, master ou apenas docs.
- Criterio de promocao definido antes de executar.

### F11-W6-01 - QA Sim/Nao pos-sandbox

Objetivo: validar a sandbox F11 antes de qualquer promocao.

Criterios de aceite:

- Veredito final obrigatorio: Sim ou Nao.
- Inputs plausiveis.
- Formulas sem erro.
- ROI e payback plausiveis.
- Named ranges/resumo acessiveis.
- Visual usavel sem polimento manual.
- Coerencia com F2/#01 e proposta/deck.

## Definition of Ready para executar a auditoria F11-W3

| Item | Estado |
|---|---|
| Documento proprio F11 criado | Sim |
| Story 7 do F1 separada da execucao ROI | Sim |
| Master F11 identificado | Sim |
| REF-02 identificada | Sim |
| Fontes locais de runtime mapeadas | Sim |
| Permissao para editar Drive | Nao |
| Permissao para criar sandbox | Nao |
| Permissao para alterar runtime | Nao |

## Definition of Done desta frente documental

Esta atualizacao fica pronta quando:

- este arquivo existir na pasta propria de F11;
- `Backlog-Operacional-Atual.md` apontar para este arquivo como documento de origem;
- a Story 7 do F1 deixar claro que o documento proprio foi criado;
- nenhuma alteracao tiver sido feita no master F11, na REF-02 ou no runtime.

## Registro de execucao F11-W3

Executado em 2026-05-20:

- `01-auditoria-read-only-f11-w3.md`

Resultado:

- master F11 e REF-02 lidos em modo read-only;
- nenhum arquivo do Drive foi alterado;
- nenhum arquivo de runtime foi alterado;
- recomendacao registrada: criar sandbox hibrida baseada na REF-02 antes de qualquer promocao.
- auditoria aprovada por Thiago em 2026-05-20.

## Registro de sandbox e QA F11-W6

Executado em 2026-05-20:

- `02-sandbox-f11-v2-execucao.md`
- `03-qa-f11-w6-sandbox.md`
- `04-plano-acao-runtime-f11-v2.md`
- `05-plano-execucao-promocao-runtime-f11-v2.md`

Resultado:

- sandbox F11 v2 criada/adaptada na copia manual `1OWeAadbcnuqcjXVtx8-6S16XAbgKnT4S2NkKwQWu8Zw`;
- QA F11-W6 aprovado com veredito **Sim** para a sandbox/template;
- plano de acao para atualizar runtime criado;
- plano executavel combinado de promocao F11 v2 + atualizacao runtime criado;
- master F11, REF-02 original e runtime continuam sem alteracao nesta frente.

## Registro de promocao e runtime F11 v2

Executado em 2026-05-20:

- `05-plano-execucao-promocao-runtime-f11-v2.md`
- `06-registro-promocao-runtime-f11-v2.md`

Resultado:

- veredito **Sim**;
- F11 oficial promovido por registry para `1OWeAadbcnuqcjXVtx8-6S16XAbgKnT4S2NkKwQWu8Zw`;
- master F11 anterior `1CxI8RtqZifigfam7PhBA8NZVlaorLRSM9cTDUwbL5UY` preservado como historico;
- runtime #09, checklist B09, mini-onboarding, agent specialty, validacao de 3 camadas, fallback MCP, README e wrappers sincronizados para F11 v2;
- smoke test pos-promocao passou no Google Sheets promovido;
- REF-02 original e master historico nao foram editados.

## Proximo passo objetivo

Gerar a primeira calculadora #09 real somente depois de mini-onboarding com premissas reais e QA de caso; ate la, manter `RESUMO_AVISO_COMERCIAL` como protecao contra promessa indevida.
