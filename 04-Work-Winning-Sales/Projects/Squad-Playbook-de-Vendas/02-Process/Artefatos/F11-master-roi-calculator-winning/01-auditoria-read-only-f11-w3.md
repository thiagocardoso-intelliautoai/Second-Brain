---
created_at: 2026-05-20
updated_at: 2026-05-20
status: aprovada-read-only
wave: "3-F11"
scope: auditoria-read-only-comparacao
artifact: F11 master-roi-calculator-winning
target_drive_id: "1CxI8RtqZifigfam7PhBA8NZVlaorLRSM9cTDUwbL5UY"
reference_drive_id: "16GiuEoJHGkJeiEwxKmKxnDHK5zAdrPJkVP77hB4A5vs"
source_doc: "00-wave-3-contrato-e-frente-roi.md"
runtime_modified: false
drive_modified: false
mode: read-only
verdict: "auditoria-aprovada-sandbox-pendente-de-aprovacao-explicita"
story_mirror: "07-stories-espelho.md#f11-s01---auditoria-read-only-e-rota-f11-v2"
---

# Auditoria Read-only F11-W3

## Nota de governanca - 2026-05-21

Esta auditoria historica agora esta espelhada pela story `F11-S01` em `07-stories-espelho.md`.

## Objetivo

Executar a primeira story/wave propria da frente F11: ler o master atual e a REF-02 em modo read-only, comparar as estruturas e recomendar uma rota antes de qualquer alteracao no `master-roi-calculator-winning`.

## Escopo executado

Executado:

- leitura de metadata do master F11 e da REF-02;
- leitura de comentarios nos dois arquivos;
- leitura de ranges estruturais e formulas principais;
- comparacao master atual vs REF-02;
- recomendacao de rota para F11 v2.

Nao executado:

- nenhuma edicao no Drive;
- nenhuma copia sandbox;
- nenhuma promocao de master;
- nenhuma alteracao em registry, task, checklist ou runtime;
- nenhuma alteracao no F1.

## Evidencias de leitura

### Master F11 atual

| Item | Evidencia |
|---|---|
| Spreadsheet | `master-roi-calculator-winning` |
| ID | `1CxI8RtqZifigfam7PhBA8NZVlaorLRSM9cTDUwbL5UY` |
| URL | `https://docs.google.com/spreadsheets/d/1CxI8RtqZifigfam7PhBA8NZVlaorLRSM9cTDUwbL5UY/edit` |
| Locale | `pt_BR` |
| Timezone | `America/Sao_Paulo` |
| Abas | `Inputs`, `Calculo de impacto`, `Calculo de ROI`, `Resumo executivo` |
| Comentarios | Nenhum comentario ativo |
| Ranges lidos | `Inputs!A1:H40`, `Calculo de impacto!A1:H40`, `Calculo de ROI!A1:H40`, `Resumo executivo!A1:H45` |

### REF-02

| Item | Evidencia |
|---|---|
| Spreadsheet | `Calculadora_ROI_WinningSales` |
| ID | `16GiuEoJHGkJeiEwxKmKxnDHK5zAdrPJkVP77hB4A5vs` |
| URL | `https://docs.google.com/spreadsheets/d/16GiuEoJHGkJeiEwxKmKxnDHK5zAdrPJkVP77hB4A5vs/edit` |
| Locale | `pt_BR` |
| Timezone | `America/Los_Angeles` |
| Abas | `1. Capa`, `2. Inputs`, `3. Motor de Calculo`, `4. Resumo Executivo`, `5. Cenarios`, `6. Dashboard` |
| Comentarios | Nenhum comentario ativo |
| Ranges lidos | `1. Capa!A1:H40`, `2. Inputs!A1:H45`, `3. Motor de Calculo!A1:H60`, `4. Resumo Executivo!A1:H45`, `5. Cenarios!A1:H45`, `6. Dashboard!A1:H50` |

Observacao: a API do Sheets aplicou rate limit em algumas leituras extras, mas os ranges principais acima foram suficientes para a comparacao estrutural e de formulas.

## Master atual observado

O master F11 atual cumpre o contrato minimo do registry:

- tem 4 abas nativas;
- esta em `pt_BR`;
- usa timezone `America/Sao_Paulo`;
- tem formulas tolerantes a placeholders em pontos criticos;
- possui bloco `RESUMO_*` em `Resumo executivo`;
- nao possui comentarios ativos.

Estrutura por aba:

| Aba | Observacao |
|---|---|
| `Inputs` | Campos para cliente, produto, volume, baseline de tickets/horas, custo hora, reducoes esperadas, investimento e fonte de benchmark. |
| `Calculo de impacto` | Calcula reducao de tickets, reducao de horas, horas liberadas e economia mensal. |
| `Calculo de ROI` | Calcula economia mensal/anual, investimento anual, ROI ano 1 e payback. |
| `Resumo executivo` | Expoe `RESUMO_USUARIOS`, `RESUMO_PAYBACK`, `RESUMO_ROI_ANO_1`, `RESUMO_REDUCAO_TICKETS`, `RESUMO_ECONOMIA_ANUAL` e `RESUMO_FRASE_FINAL`. |

Limites encontrados:

- O modelo atual e estreito: foca em tickets de TI, provisionamento, horas e custo.
- Nao ha capa, modo de uso, convencao de cores, cenarios ou dashboard executivo.
- O resumo existe tecnicamente, mas e menos forte como material de reuniao.
- A planilha tem instrucoes visiveis de uso do template. Isso e aceitavel no master, mas deve ser revisto se a aba for entregue client-facing.

## REF-02 observada

A REF-02 e uma calculadora de valor mais completa e mais pronta para conversa comercial.

Estrutura por aba:

| Aba | Observacao |
|---|---|
| `1. Capa` | Abre com posicionamento executivo, objetivo, modo de uso, convencao de cores e aviso de estimativa comercial. |
| `2. Inputs` | Organiza identificacao, investimento e 3 alavancas: aumento de receita, reducao de custo e reducao de risco. |
| `3. Motor de Calculo` | Calcula ganho por alavanca, ganho bruto, ganho liquido, ROI, payback, classificacao de impacto e validacao de integridade. |
| `4. Resumo Executivo` | Mostra cards de ganho bruto, ganho liquido, investimento, ROI e payback; gera leitura do caso e texto executivo. |
| `5. Cenarios` | Traz Conservador, Base e Otimista com fatores editaveis e resultados automaticos. |
| `6. Dashboard` | Consolida ROI, payback, ganho liquido, comparativos por alavanca e cenarios. |

Pontos fortes:

- Tem narrativa de uso: transforma conversa de venda em conversa de valor.
- Cobre 3 alavancas, nao apenas reducao de custo.
- Mostra formula logica junto do motor, facilitando auditoria.
- Traz cenarios de sensibilidade, util para ancorar risco e decisao.
- Tem dashboard executivo pronto para reuniao.
- Inclui aviso de estimativa comercial, reduzindo risco de promessa indevida.

Pontos que precisam ajuste antes de virar master F11:

- Timezone esta `America/Los_Angeles`; contrato F11 espera `America/Sao_Paulo`.
- Ha dados de exemplo (`Acme Industria S.A.`, valores e solucao exemplo) que precisam virar placeholders ou defaults controlados.
- Nao foi identificado bloco tecnico `RESUMO_*` equivalente ao master atual nos ranges lidos.
- A estrutura tem 6 abas, enquanto o registry atual declara 4 abas.
- A REF-02 deve ser adaptada ao fluxo do squad: mini-onboarding, task #09, checklist B09 e consumo pelo deck/proposta.

## Comparacao objetiva

| Area | Master atual | REF-02 | Decisao recomendada |
|---|---|---|---|
| Estrutura | 4 abas tecnicas | 6 abas com capa, cenarios e dashboard | Adaptar REF-02 como base de F11 v2 |
| Modelo de valor | Reducao de tickets/horas/custo | Receita, custo e risco | Substituir modelo estreito por 3 alavancas |
| Inputs | Placeholders bem contratados | Exemplo comercial rico | Converter exemplos em placeholders e defaults |
| Formulas | Simples e tolerantes | Mais completas e auditaveis | Preservar formulas da REF-02 salvo erro confirmado |
| Resumo executivo | Bloco tecnico `RESUMO_*` | Cards e textos comerciais | Combinar: manter `RESUMO_*` e adicionar resumo da REF-02 |
| Cenarios | Ausente | Conservador/Base/Otimista | Incorporar em F11 v2 |
| Dashboard | Ausente | Presente | Incorporar em F11 v2 |
| Locale/timezone | `pt_BR`, `America/Sao_Paulo` | `pt_BR`, `America/Los_Angeles` | Corrigir timezone na sandbox |
| Cross-deliverable | Ja pensa em deck/proposta | Mais forte para reuniao | Manter contrato de saida para deck/proposta |

## Achados

| Severidade | Achado | Impacto | Tratamento recomendado |
|---|---|---|---|
| Alta | Master atual e funcional, mas estreito demais para a ambicao da REF-02. | ROI fica preso a caso de tickets/provisionamento e perde valor comercial. | Criar F11 v2 em sandbox baseada na REF-02. |
| Alta | REF-02 nao parece expor o mesmo bloco tecnico `RESUMO_*` do master atual. | Deck/proposta podem perder caminho estavel de consumo. | Adicionar bloco/named ranges `RESUMO_*` na sandbox. |
| Alta | REF-02 usa 6 abas, registry atual declara 4. | Promocao sem atualizar runtime criaria divergencia. | Se aprovada, atualizar registry/task/checklist para F11 v2. |
| Media | REF-02 esta em timezone `America/Los_Angeles`. | Divergencia com contrato F11 e padrao operacional Brasil. | Ajustar timezone para `America/Sao_Paulo` na sandbox. |
| Media | REF-02 contem dados de exemplo em vez de placeholders. | Risco de entregar exemplo ao cliente se promovida sem adaptacao. | Converter exemplos para placeholders e defaults controlados. |
| Media | Cenarios podem inflar ROI se usados sem fonte de premissa. | Risco comercial de promessa exagerada. | Exigir fonte/hipotese e aviso comercial em todos os cenarios. |

## Recomendacao de rota

Nao recomendo patch incremental direto no master atual.

Recomendo criar uma **sandbox hibrida baseada na REF-02**, preservando seus calculos e estrutura comercial, mas adaptando para o contrato do squad:

1. Duplicar a REF-02 como sandbox F11 v2.
2. Corrigir timezone para `America/Sao_Paulo`.
3. Converter dados de exemplo em placeholders oficiais do #09.
4. Manter as 6 abas, se Thiago aprovar a expansao do contrato F11.
5. Adicionar bloco tecnico `RESUMO_*` para proposta/deck.
6. Manter aviso de estimativa comercial.
7. Validar formulas e cenarios contra o checklist B09.
8. Atualizar registry/task/checklist apenas depois da sandbox aprovada.

## Mudancas provaveis se a sandbox for aprovada

| Arquivo/artefato | Mudanca provavel |
|---|---|
| F11 Google Sheet | Nova sandbox com 6 abas e outputs tecnicos `RESUMO_*`. |
| `TEMPLATE_REGISTRY.md` | Atualizar F11 de 4 para 6 abas ou documentar excecao aprovada. |
| `generate-roi-calculator.md` | Expandir inputs para receita, custo, risco, cenarios e dashboard. |
| `camada-b-09-calculadora-roi.md` | Incluir capa, cenarios, dashboard, aviso de estimativa e contrato `RESUMO_*`. |
| Mini-onboarding #09 | Coletar alavancas aplicaveis, investimento, prazo, premissas e fonte. |
| Proposta/deck | Consumir `RESUMO_*` mantendo estabilidade cross-deliverable. |

## Definition of Done da F11-W3

| Criterio | Estado |
|---|---|
| Master F11 lido em modo read-only | Sim |
| REF-02 lida em modo read-only | Sim |
| Comentarios verificados | Sim, nenhum comentario ativo |
| Comparacao master vs REF-02 registrada | Sim |
| Recomendacao objetiva registrada | Sim |
| Drive alterado | Nao |
| Runtime alterado | Nao |

## Registro de aprovacao

Data: 2026-05-20.

Thiago aprovou a auditoria read-only F11-W3.

Escopo da aprovacao:

- aprovar o diagnostico e a recomendacao de rota;
- manter a recomendacao de sandbox hibrida baseada na REF-02 como proximo passo;
- nao autorizar, ainda, edicao no master F11, criacao de sandbox, promocao de master ou alteracao de runtime.

## Proximo passo

Pedir aprovacao explicita para criar uma sandbox F11 v2 a partir da REF-02.

Texto operacional sugerido:

```text
Aprovar criacao de sandbox F11 v2 baseada na REF-02, sem mexer no master atual.

Escopo da sandbox:
- duplicar/adaptar a REF-02;
- corrigir timezone para America/Sao_Paulo;
- converter exemplos em placeholders;
- manter 6 abas se aprovado;
- adicionar bloco RESUMO_* para proposta/deck;
- validar formulas, cenarios, ROI, payback e dashboard antes de qualquer promocao.
```
