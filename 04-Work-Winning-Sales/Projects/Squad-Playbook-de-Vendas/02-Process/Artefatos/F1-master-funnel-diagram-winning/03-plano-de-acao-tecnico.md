---
created_at: 2026-05-19
status: handoff-dev-pronto
artifact: F1 master-funnel-diagram-winning
runtime_modified: false
drive_modified: false
depends_on:
  - 00-referencias-e-benchmark.md
  - 01-auditoria-1-wave5a.md
  - 02-consolidacao-pre-wave5b.md
story_source:
  - 04-stories-sm.md
---

# 03 - Plano de Acao Tecnico F1

## Resumo executivo tecnico

Objetivo: preparar a execucao da Wave 5B do F1 `master-funnel-diagram-winning` em Google Slides nativo, com base Winning, preservando placeholders e transformando referencias reais em melhorias `Done for you`.

Este plano e o handoff para o dev. Ele nao executa alteracao. O dev deve pedir aprovacao antes de editar Google Slides master ou runtime.

Decisao principal: **manter Google Slides nativo** como rota final. HTML/CSS pode ser usado apenas como prototipo visual auxiliar, se acelerar decisao visual, mas o resultado final deve ser no Slides.

Gate REF-03 resolvido: a referencia foi liberada, lida e analisada em 2026-05-19. Ela entra como benchmark de conteudo, variaveis e criterios, mas nao como estrutura bruta do F1.

## Fontes obrigatorias para o dev

| Ordem | Fonte | Uso |
|---:|---|---|
| 1 | `00-referencias-e-benchmark.md` | Saber o que pode inspirar e o que nao pode ser copiado. |
| 2 | `01-auditoria-1-wave5a.md` | Diagnostico por slide, variaveis, gaps e rota tecnica. |
| 3 | `02-consolidacao-pre-wave5b.md` | Escopo que entra, nao entra e pendencias. |
| 4 | `02-Process/Wave-5A-F1-Master-Funnel-Diagram-Winning.md` | Evidencia original completa da Wave 5A. |
| 5 | `07-Runtime-Squad/templates/TEMPLATE_REGISTRY.md` | ID do master e contrato do F1. |
| 6 | `07-Runtime-Squad/tasks/generate-funnel-kpis.md` | Fluxo de geracao do F1/F2. |
| 7 | `D:\1AWinningSales-Projetos\squadfactory\Design System` | Fonte de verdade visual. |

## Alvo tecnico

| Item | Decisao |
|---|---|
| Master alvo | `master-funnel-diagram-winning` do registry, ID `1MLhe3oKxK5hvwF6wQG-djjsTZsiOGHckpeGAV99tEMc`. |
| URL `1tnc5...` enviada por Thiago | Usar como comparacao/original relacionado ate confirmacao; nao editar como master por padrao. |
| Plataforma final | Google Slides nativo. |
| Numero de slides | Manter 5 slides neste ciclo. |
| Escopo Wave 5B | Corrigir defeitos, aplicar base Winning, melhorar fluxo/narrativa e robustecer placeholders. |
| Fora do escopo | ROI/F11, runtime amplo, redesign pesado sem aprovacao, material de treinamento Do it yourself. |

## Especificacao de layout base

### Layout 1 - `cover_executive_map`

Aplicar no slide 1.

Regras:

- Usar marca Winning por asset oficial, nao texto solto.
- Titulo deve ser executivo: arquitetura de funil do produto/cliente.
- Dois blocos de funil devem ficar claros e conectados por handoff.
- Microcopy deve explicar o desenho pronto, nao ensinar o cliente a criar.
- Reservar espaco para `{{NOME_CLIENTE}}`, `{{NOME_PRODUTO}}`, `{{VERSAO}}`, `{{DATA_GERACAO}}`.

### Layout 2 - `funnel_overview_2x5`

Aplicar no slide 2.

Regras:

- Comunicar progressao e handoff, nao apenas inventario.
- Manter 2 funis x ate 5 estagios.
- Numeros `01..05` devem ter componente fixo, sem quebra de linha.
- O handoff deve ser visualmente mais forte que uma nota secundaria.
- Inspirar clareza narrativa de REF-01/REF-04, sem linguagem de treinamento.

### Layout 3 - `funnel_detail_table`

Aplicar nos slides 3 e 4.

Regras:

- Usar nome real do funil como titulo/contexto quando possivel.
- Reduzir sensacao de tabela densa com hierarquia e espacamento.
- Etapa, descricao e criterio de saida precisam ser legiveis em thumbnail.
- Corrigir qualquer texto invertido/rotacionado.
- Tratar estes slides como consulta operacional premium.

### Layout 4 - `management_cards`

Aplicar no slide 5.

Regras:

- Metas, rituais e decisoes devem parecer compromissos operacionais.
- REF-02 inspira clareza executiva e premissas, nao logica de ROI.
- REF-03 inspira variaveis, criterios de saida, contexto Low/Mid/High Touch, origem dos leads, percepcao de valor e proximo passo.
- REF-04 inspira proximos passos e decisao, nao proposta/DBS.
- Listas devem suportar 3-5 bullets curtos.

## Contrato de texto para placeholders

| Campo | Limite inicial | Regra de layout |
|---|---:|---|
| `{{NOME_CLIENTE}}` | 34 caracteres | Deve caber em footer/header sem reduzir abaixo de leitura confortavel. |
| `{{NOME_PRODUTO}}` | 36 caracteres | Titulo deve aceitar quebra controlada. |
| Nome do funil | 28 caracteres | Nunca depender de uma unica linha obrigatoria. |
| Proposito do funil | 110 caracteres | Caixa deve aceitar 2-3 linhas. |
| Nome de estagio | 24 caracteres | Se passar, quebrar em 2 linhas dentro do card sem empurrar numero. |
| Descricao de estagio | 95 caracteres | Caixa deve comportar texto real em corpo legivel. |
| Criterio de saida | 95 caracteres | Mesma regra da descricao. |
| Handoff principal | 140 caracteres | Usar box dedicado, nao nota apertada. |
| Metas/rituais/decisoes | 3-5 bullets de ate 70 caracteres | Quebra controlada; sem overflow. |

Se o dev identificar que esses limites nao cabem com a escala visual aprovada, deve voltar para ajuste do contrato antes de aplicar find-replace em artefato real.

## Ordem de execucao recomendada para Wave 5B

1. Confirmar permissao e alvo correto do Google Slides master.
2. Localizar assets oficiais de logo/wordmark e fontes recomendadas no Design System.
3. Fazer copia de trabalho do master antes de qualquer edicao destrutiva.
4. Corrigir P0: texto invertido no slide 4 e numeracao quebrada.
5. Aplicar escala tipografica Jost/Inter em Slides.
6. Criar ou simular master/layouts base: capa, overview 2x5, detalhe, management cards.
7. Melhorar slide 2 como fluxo/handoff usando REF-01, REF-03 e REF-04 como benchmark de narrativa.
8. Melhorar slides 3 e 4 como consulta operacional premium, incorporando criterios de saida mais fortes da REF-03.
9. Melhorar slide 5 como gestao executiva com inspiracao limitada de REF-02, REF-03 e REF-04.
10. Testar com textos no limite do contrato.
11. Gerar thumbnails por slide e validar visualmente.
12. Registrar QA e pendencias para Wave 6.

## Mudancas de runtime/templates/checklists - plano, nao execucao

Estas mudancas so devem acontecer com aprovacao explicita.

| Area | Mudanca sugerida | Motivo |
|---|---|---|
| `TEMPLATE_REGISTRY.md` | Registrar limites de texto e regra de 2 funis x ate 5 estagios. | Evitar overflow e ambiguidade no runtime. |
| `generate-funnel-kpis.md` | Incluir limpeza de cards/linhas nao usados e QA visual por thumbnail. | Evitar placeholders vazios e quebra visual. |
| `find-replace-placeholders.md` | Reforcar limites por tipo de placeholder, se skill permitir. | Proteger layout em clientes reais. |
| `camada-b-01-funil-kpis.md` | Adicionar checks de numeracao, overflow, texto invertido e identidade Winning. | Transformar achados da auditoria em gate. |
| `identidade-visual-dupla.md` | Se necessario, explicitar como combinar Winning + cliente em Slides. | Manter consistencia visual. |

## QA gates da Wave 5B

| Gate | Criterio de aceite |
|---|---|
| G1 - Identidade Winning | Paleta, tipografia, logo/wordmark e espacamento aderentes ao Design System. |
| G2 - Placeholder seguro | Nenhum placeholder fica sem espaco previsto; teste com texto no limite. |
| G3 - Numeracao | `01..05` nao quebra em nenhum slide. |
| G4 - Orientacao | Nenhum texto aparece invertido ou rotacionado incorretamente. |
| G5 - Narrativa | Slide 2 mostra fluxo/handoff; slide 5 mostra gestao/decisao. |
| G6 - Done for you | Nenhuma linguagem de aula/workshop fica visivel no deck final. |
| G7 - Nativo/editavel | Deck final continua Google Slides nativo e editavel. |
| G8 - Evidencia visual | Thumbnails geradas por slide alterado e anexadas ao QA. |

## Definition of Done da Wave 5B

- Master/copia aprovada do F1 ajustada em Google Slides nativo.
- 5 slides preservados, salvo aprovacao explicita para alterar quantidade.
- Defeitos P0 resolvidos.
- Base visual Winning aplicada.
- Variaveis preservadas e testadas com limites.
- Nenhuma referencia Do it yourself copiada como aula.
- Mudancas em runtime, se houver, aprovadas e rastreadas.
- QA visual registrado para entrada na Wave 6.

## Feedback estrategico

A separacao em `00`, `01`, `02`, `03` e `04-stories` e a forma mais limpa para evitar confusao de waves:

- `00` guarda insumo e benchmark.
- `01` preserva a Wave 5A ja executada.
- `02` decide o que entra ou nao antes da execucao.
- `03` vira handoff unico para o dev.
- `04-stories` organiza trabalho para SM/dev sem fingir que Wave 5B ja aconteceu.

Nao criar `04-execucao-wave5b-log.md` agora. Se a Wave 5B for executada depois, criar `05-qa-pos-execucao.md` ou equivalente somente com evidencias reais.
