---
created_at: 2026-05-19
status: preenchido
artifact: F1 master-funnel-diagram-winning
runtime_modified: false
drive_modified: false
source_truth_visual: D:\1AWinningSales-Projetos\squadfactory\Design System
feeds:
  - 01-auditoria-1-wave5a.md
  - 02-consolidacao-pre-wave5b.md
  - 03-plano-de-acao-tecnico.md
---

# 00 - Referencias e Benchmark F1

## Papel deste documento

Este documento guarda as referencias que Thiago ja enviou para o F1 `master-funnel-diagram-winning` e separa o que cada uma pode inspirar sem confundir `Do it yourself` com `Done for you`.

Ele nao executa Wave 5B, nao altera Google Slides e nao muda runtime. Serve como insumo para a Auditoria 1 atualizada, a consolidacao pre-Wave 5B e o plano tecnico.

## Alvos e IDs importantes

| Item | ID / URL | Observacao |
|---|---|---|
| F1 master no registry | `1MLhe3oKxK5hvwF6wQG-djjsTZsiOGHckpeGAV99tEMc` | Fonte alvo do template master atual, conforme `TEMPLATE_REGISTRY.md`. |
| Original F1 enviado por Thiago nas refs 1 e 3 | `1tnc5AcoEBjQkVGbouJ5Eav5Ihjz9d7OvLgbTQ4Zgo20` | Usar como artefato relacionado/comparacao. Nao assumir que e o master a editar sem confirmacao. |
| F11 ROI master no registry | `1CxI8RtqZifigfam7PhBA8NZVlaorLRSM9cTDUwbL5UY` | Ref2 aponta diretamente para o artefato ROI, nao para o F1. |
| Design System Winning | `D:\1AWinningSales-Projetos\squadfactory\Design System` | Fonte de verdade visual. Referencias reais sao benchmark, nao substituem o Design System. |

## Regra central de adaptacao

O F1 do Playbook e um entregavel `Done for you`: a Winning entrega uma arquitetura de funil pronta, personalizada e utilizavel pelo cliente.

Quando a referencia for `Do it yourself`, ela pode inspirar clareza, narrativa, criterios, exemplos e visual, mas deve ser convertida para saida pronta. Nao copiar linguagem de aula, orientacoes ao cliente para preencher sozinho, golden tips, exercicios ou campos em branco sem tratamento.

Regra especifica de variaveis: ao transformar campos em `{{variaveis}}`, prever o tamanho real do output do squad e reservar espaco visual suficiente. Variavel nao pode ser inserida onde so cabe uma palavra curta se o agente provavelmente vai gerar frase longa.

## Matriz de referencias recebidas

| Ref | Formato | Tipo | URL da referencia | Original relacionado | Status | Decisao |
|---|---|---|---|---|---|---|
| REF-01 | Google Slides | Do it yourself | `https://docs.google.com/presentation/d/1Ye5fGZhrFNjenQoZS2NoxGEMhjk-RlhOvnzIr0Qmrqg/edit?slide=id.g8827b4d983_0_5192#slide=id.g8827b4d983_0_5192` | `https://docs.google.com/presentation/d/1tnc5AcoEBjQkVGbouJ5Eav5Ihjz9d7OvLgbTQ4Zgo20/edit?slide=id.p1#slide=id.p1` | Lida e analisada | Adaptar design e conteudo; nao copiar linguagem de treinamento. |
| REF-02 | Google Sheets | Done for you | `https://docs.google.com/spreadsheets/d/16GiuEoJHGkJeiEwxKmKxnDHK5zAdrPJkVP77hB4A5vs/edit?gid=1344566515#gid=1344566515` | `https://docs.google.com/spreadsheets/d/1CxI8RtqZifigfam7PhBA8NZVlaorLRSM9cTDUwbL5UY/edit?gid=763349089#gid=763349089` | Lida e analisada apos ajuste de acesso | Backlog proprio para ROI/F11; para F1 usar apenas como benchmark transversal de maturidade executiva. |
| REF-03 | Google Docs | Do it yourself | `https://docs.google.com/document/d/1qZheecBy_Dqr3XazuZbImCmjlvMDPr55GuLBvruGuD0/edit?tab=t.0` | `https://docs.google.com/presentation/d/1tnc5AcoEBjQkVGbouJ5Eav5Ihjz9d7OvLgbTQ4Zgo20/edit?slide=id.p1#slide=id.p1` | Lida e analisada apos ajuste de acesso | Adaptar conteudo, variaveis e criterios; nao transformar F1 em workbook/roteiro de primeira reuniao. |
| REF-04 | Google Slides | Do it yourself | `https://docs.google.com/presentation/d/1tH83ydvDzNHzYU9RxfLJIohZ0JVY1NUg0Gvssi-YwsQ/edit?slide=id.g20dc3e06440_0_352#slide=id.g20dc3e06440_0_352` | `https://docs.google.com/presentation/d/1mEhFhVqVcMfoFy6_pl7adzMVtuKJiEMoVvS8e_MlP0Q/edit?slide=id.p1#slide=id.p1` | Lida e analisada | Adaptar narrativa dor -> solucao -> valor -> decisao; nao copiar roteiro de aula/treinamento. |

## REF-01 - DBA Slides

Fatos confirmados:

- Titulo lido: `DBA - Joao Oxygen`.
- Formato: apresentacao em Google Slides.
- Tipo informado por Thiago: `Do it yourself`.
- Conteudo identificado: treinamento de vendas consultivas, arco de DBA, diagnostico, educacao, fechamento e uso de frameworks como GPCT-CI.
- Pode inspirar design e conteudo do F1, mas a saida do F1 continua sendo apresentacao `Done for you`.

O que deve inspirar:

| Dimensao | Aprendizado aplicavel ao F1 |
|---|---|
| Design | Ritmo visual mais forte que o F1 atual; uso de secao, contraste, hierarquia e respiro para guiar leitura. |
| Conteudo | Estruturar o funil como raciocinio consultivo, nao apenas inventario de cards. |
| Narrativa | Fazer o leitor entender por que as etapas existem, qual transicao importa e qual decisao cada etapa sustenta. |
| Variaveis | Campos de preenchimento devem virar `{{variaveis}}` com limite e espaco projetado, nao lacunas em branco. |

O que nao copiar:

- Texto de aula, dicas ao vendedor, golden tips e instrucoes de preenchimento.
- Exemplo longo que dependa de contexto de treinamento.
- Linguagem em segunda pessoa ensinando o cliente a fazer.
- Campos em branco do material original; no F1 eles viram saida pronta ou placeholder controlado.

Impacto no F1:

- Slide 1 deve parecer mapa executivo pronto, nao capa de treinamento.
- Slide 2 deve comunicar fluxo e handoff com mais clareza.
- Slides 3 e 4 podem manter detalhe operacional, mas com cara de consulta pronta e nao worksheet.
- Slide 5 deve conectar gestao, metas e rituais como decisoes ja propostas pela Winning.

## REF-02 - Calculadora ROI & Valor

Fatos confirmados:

- Referencia: `Calculadora_ROI_WinningSales`.
- Tipo informado por Thiago: `Done for you`.
- Conteudo identificado: capa, objetivo, modo de uso, convencao de cores, inputs do cliente, 3 alavancas de valor, motor de calculo, resumo executivo, cenarios conservador/base/otimista e dashboard executivo.
- Original relacionado: `master-roi-calculator-winning`, artefato F11/Sheets.

Decisao:

- REF-02 nao deve entrar como execucao da Wave 5B do F1.
- Deve virar backlog proprio do ROI/F11, porque Thiago indicou que praticamente tudo da referencia esta melhor que o master atual.
- Para o F1, aproveitar apenas como benchmark transversal de maturidade: clareza executiva, premissas explicitas, cenarios e visual de decisao.

O que pode inspirar no F1:

| Aprendizado | Aplicacao segura no F1 |
|---|---|
| Leitura executiva | Slide 1 e slide 5 devem responder "o que muda na gestao comercial". |
| Premissas explicitas | Handoff, metas e rituais devem ter criterios visiveis e nao parecer texto solto. |
| Cenarios | Nao criar ROI no F1, mas separar o que e estado atual, desenho proposto e decisao pendente. |
| Personalizacao Done for you | O deck deve parecer adaptado pela Winning para o cliente, nao uma matriz generica. |

Backlog separado:

- Criar frente propria para F11 `master-roi-calculator-winning`.
- Provavel rota: duplicar/substituir master ROI a partir da referencia, se Thiago colocar a referencia no Drive/local correto e aprovar.
- Melhorias visuais podem ser feitas depois; calculos da referencia foram considerados corretos por Thiago.

## REF-03 - DBA Google Docs

Fatos confirmados:

- Titulo lido: `Template_DBA_Winning_Sales`.
- Tipo informado por Thiago: `Do it yourself`.
- Mesmo universo de conteudo da REF-01.
- Objetivo informado: inspirar conteudo, transformar campos em branco em `{{variavel-A}}`, manter saida final como apresentacao, e melhorar design pela REF-01.
- Status tecnico: acesso liberado e leitura confirmada pelo conector em 2026-05-19.
- Conteudo identificado: contexto da venda, tipo Low/Mid/High Touch, origem dos leads, missao da primeira reuniao, alavancas de compra B2B, arco DBA de 6 etapas, SPIN, educacao em duas camadas, percepcao de valor, ICUVA, proximos passos e checklist final.

O que deve inspirar:

| Frente | Aprendizado aplicavel ao F1 |
|---|---|
| Conteudo | Tornar o F1 mais valioso como arquitetura de decisao: origem do lead, tipo de venda, missao da reuniao/funil, criterio de saida e proximo passo. |
| Variaveis | Campos em branco da referencia devem virar placeholders controlados ou saidas prontas sintetizadas pelo squad. |
| Narrativa | O arco da reuniao ajuda a pensar o funil como sequencia de progresso, nao como lista de etapas. |
| Handoff | O F1 deve explicitar o que precisa estar verdadeiro para a etapa avancar. |
| Valor | A estrutura de percepcao de valor reforca que criterios de etapa devem conectar dor, impacto, valor e decisao. |

O que nao copiar:

- Roteiro de primeira reuniao como conteudo final do F1.
- Perguntas SPIN completas, listas longas e checklist final.
- Linguagem `construa`, `marque`, `como voce vai...` e instrucoes de preenchimento.
- Campos em branco com sublinhado; no F1 isso deve virar `{{variavel}}` ou conteudo pronto.
- Tempos de reuniao como se fossem etapas do funil, salvo quando fizerem sentido como SLA/ritual.

Conversao recomendada para o F1:

| Padrao da REF-03 | Conversao Done for you no F1 |
|---|---|
| Tipo Low/Mid/High Touch | Premissa de desenho do funil ou nota de contexto, ja preenchida a partir do squad. |
| Origem dos leads | Variavel de contexto do funil/prospeccao, nao campo aberto. |
| Missao da primeira reuniao | Variavel de proposito do funil/etapa, escrita como resultado pronto. |
| Alavancas receita/custo/risco | Criterio narrativo para slide 5 e para criterios de saida. |
| SPIN | Base para enriquecer descricoes/criterios de diagnostico, sem inserir questionario. |
| Educacao em duas camadas | Ajuda a diferenciar etapas de meio e fundo de funil. |
| ICUVA | Pode inspirar criterio de saida/qualificacao de oportunidade. |
| Proximos passos | Reforca que todo handoff precisa ter agenda/acao concreta. |

## REF-04 - DBS Slides

Fatos confirmados:

- Titulo lido: `Joao Oxygen - Treinamento de DBS`.
- Tipo informado por Thiago: `Do it yourself`.
- Conteudo identificado: narrativa DBS, proposta, dor -> solucao -> valor -> decisao, quantificacao, investimento, planos e proximos passos.
- Original relacionado aponta para artefato DBS, nao F1.

O que deve inspirar:

| Dimensao | Aprendizado aplicavel ao F1 |
|---|---|
| Narrativa | Organizar funil como caminho de valor e decisao, nao so sequencia operacional. |
| Conteudo | Destacar dor operacional, handoff, valor esperado e criterio de saida por etapa. |
| Design | Mais hierarquia, contraste e ritmo de secao do que o F1 atual. |
| Proximos passos | Slide 5 pode fechar com decisoes/rituais como compromissos operacionais. |

O que nao copiar:

- Roteiro de apresentacao ou treinamento.
- Texto de proposta, planos, investimento ou argumentos comerciais que pertencem ao DBS.
- Golden tips e instrucoes ao vendedor.
- Estrutura completa de DBS dentro do F1.

## Matriz de conversao Do it yourself -> Done for you

| Padrao da referencia | Natureza original | Conversao correta no F1 | Copiar? |
|---|---|---|---|
| Campo em branco para cliente preencher | Exercicio / worksheet | Placeholder `{{...}}` com limite e output pronto do squad | Adaptar |
| Origem de lead, tipo de venda ou missao da reuniao | Contexto a preencher | Variavel de apresentacao ou nota executiva ja sintetizada | Adaptar |
| Pergunta de diagnostico | Ensino do metodo | Criterio de saida ou premissa ja sintetizada | Adaptar |
| Dica ao vendedor | Instrucao interna | Remover do entregavel final; se util, virar checklist/runtime futuro | Nao copiar no deck |
| Exemplo narrativo longo | Aula / demonstracao | Microcopy curta ou nota executiva, se couber | Adaptar com corte |
| Estrutura dor -> solucao -> valor -> decisao | Framework de ensino | Sequencia narrativa executiva do F1 | Adaptar |
| Dashboard/cenarios ROI | Entregavel Done for you de Sheets | Backlog F11; no F1 usar apenas criterio executivo | Nao misturar |

## Gaps que as referencias ajudam a resolver

| Gap da Wave 5A | Referencia que ajuda | Como ajuda |
|---|---|---|
| F1 parece inventario de cards | REF-01, REF-03, REF-04 | Reforcam narrativa, arco de progresso e transicoes entre etapas. |
| Identidade Winning parcial | REF-01, REF-04, Design System | Inspiram hierarquia/ritmo, mas Design System decide visual final. |
| Falta criterio de placeholder | REF-03, observacao de Thiago | Campos em branco devem virar variaveis ou saidas prontas com espaco planejado. |
| Slide 5 pouco executivo | REF-02, REF-03, REF-04 | Reforcam leitura de valor, premissas, handoff e proximos passos. |
| Risco de copiar material Do it yourself | REF-01, REF-03, REF-04 | Exigem matriz de conversao antes de aplicar. |

## Pendencias

| Pendencia | Severidade | Proximo passo |
|---|---:|---|
| Relacao entre URL original `1tnc5...` e master registry `1ML...` | Media | Dev deve usar registry como master alvo; URL de Thiago fica como comparacao ate confirmacao. |
| Backlog ROI/F11 | Media | Criar artefato proprio para F11; nao misturar com Wave 5B do F1. |
