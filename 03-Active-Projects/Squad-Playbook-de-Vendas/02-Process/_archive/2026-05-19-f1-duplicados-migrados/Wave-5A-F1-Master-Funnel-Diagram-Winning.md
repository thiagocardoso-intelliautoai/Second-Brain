---
created_at: 2026-05-19
status: concluida
wave: 5A
artifact: F1 master-funnel-diagram-winning
runtime_modified: false
drive_modified: false
detail_doc: Wave-5A-F1-Auditoria-Detalhada.md
wave7_doc: Wave-7-F1-Referencias-Intake-e-Benchmark.md
pre_5b_plan: Plano-de-Acao-F1-Pre-Wave-5B.md
---

# Wave 5A - F1 `master-funnel-diagram-winning`

## Decisao de organizacao

Este documento fica como **base executiva da Wave 5A**: decisao, estado atual, bloqueios e criterios para a proxima etapa.

O detalhe do que ja foi feito fica em:

- `02-Process/Wave-5A-F1-Auditoria-Detalhada.md`

As referencias/inspiracoes ficam em:

- `02-Process/Wave-7-F1-Referencias-Intake-e-Benchmark.md`

O plano de execucao fica em:

- `02-Process/Plano-de-Acao-F1-Pre-Wave-5B.md`

Motivo: Wave 5A documenta a auditoria e a base; Wave 7 compara referencias; o plano pre-5B organiza a fila de execucao; Wave 5B aplica mudancas aprovadas no template.

## Minha analise sobre 5A, 5B e 7

Thiago leu corretamente: **Wave 5B nao deve ser um documento de planejamento**. Ela e a etapa de aplicacao final e polimento.

Fluxo mais eficaz:

1. **Wave 5A:** auditar o F1, diagnosticar, definir rota tecnica, base visual, gaps e criterios.
2. **Wave 7:** analisar inspiracoes/referencias reais da Winning, uma por vez.
3. **Plano pre-Wave 5B:** consolidar o que entra, o que nao entra, ordem de acao, riscos e aprovacoes.
4. **Wave 5B:** aplicar no master/template apenas depois do plano aprovado.

Assim evitamos confundir a IA com tres waves misturadas no mesmo documento.

## Estado atual confirmado

| Item | Estado |
|---|---|
| Artefato | F1 `master-funnel-diagram-winning` |
| Tipo | Google Slides nativo |
| Drive ID | `1MLhe3oKxK5hvwF6wQG-djjsTZsiOGHckpeGAV99tEMc` |
| Titulo lido | `master-funnel-diagram-winning` |
| Slide count | 5 slides |
| Rota recomendada | Google Slides nativo |
| Alteracao no Drive | Nao feita |
| Alteracao no runtime | Nao feita |

## Rota tecnica recomendada

**Manter Google Slides nativo.**

Justificativa:

- O registry ja define F1 como Slides nativo.
- O master atual ja e Google Slides editavel.
- O fluxo do squad depende de duplicacao e find-replace de placeholders.
- O conector conseguiu ler deck, texto e thumbnails.
- HTML/CSS pode ajudar como prototipo visual, mas nao deve virar entrega final do F1.

## Diagnostico resumido da Wave 5A

O F1 atual e funcional, mas ainda nao tem acabamento Winning suficiente para virar base visual forte.

Principais achados:

- usa Arial em vez de Jost/Inter;
- usa `WINNING SALES` como texto, nao como asset oficial de logo/wordmark;
- numeracao de etapas quebra em duas linhas nos slides 2, 3 e 4;
- slide 4 tem texto/rodape de criterio de leitura invertido;
- ha muito uso de cards e tabela, pouco visual de fluxo;
- falta contrato de limite de texto por placeholder;
- template assume sempre 2 funis x 5 estagios;
- identidade Winning aparece na paleta, mas nao ainda na tipografia, logo, ritmo e acabamento.

Diagnostico completo por slide: ver `Wave-5A-F1-Auditoria-Detalhada.md`.

## Base visual recomendada

| Elemento | Recomendacao |
|---|---|
| Master | 16:9, safe margin 48-64px, grid consistente |
| Fundo | `bone` ou `paper`, com dark apenas em momentos de contraste |
| Logo | usar asset oficial `logo-gradient.png` no claro e `logo-white.png` no escuro |
| Tipografia | Jost para titulos/eyebrows, Inter para corpo, mono para numeracao |
| Eyebrows | ALL CAPS com tracking 0.22em |
| Cards | branco, borda sutil, raio 8-14px, sombra discreta |
| Numeracao | componente fixo de 2 digitos, sem quebra |
| QA | thumbnail LARGE por slide alterado |

Layouts-base:

| Layout | Uso |
|---|---|
| `cover_executive_map` | Slide 1 |
| `funnel_overview_2x5` | Slide 2 |
| `funnel_detail_table` | Slides 3-4 |
| `management_cards` | Slide 5 |

## Bloqueios antes da Wave 5B

| Bloqueio | Severidade | Motivo |
|---|---:|---|
| Corrigir texto invertido no slide 4 | Alta | Defeito visual confirmado em thumbnail |
| Corrigir numeracao quebrada | Alta | Afeta leitura em slides 2, 3 e 4 |
| Definir escala tipografica em pontos para Slides | Alta | Design System esta em tokens web, nao em contrato nativo de Slides |
| Aprovar limites de texto por placeholder | Alta | Sem limite, find-replace pode quebrar layout |
| Definir regra para menos/mais de 5 estagios | Media | Template presume sempre 5 estagios |
| Classificar referencias Wave 7 | Media | Inspiracoes podem ser `Do it yourself`, nao `Done for you` |

## Regra para referencias Winning

As referencias reais da Winning podem ser excelentes, mas devem ser classificadas antes de influenciar o F1.

Ponto critico:

- Referencia `Do it yourself`: Winning ensinando o cliente a fazer.
- F1 do Playbook: entregavel `Done for you`, pronto para o cliente usar.

Portanto, a referencia pode inspirar clareza, estrutura, narrativa, exemplos e visual, mas nao deve ser copiada como aula, manual, workshop ou instrucao ao cliente.

## Proximo passo objetivo

1. Thiago envia 1-3 referencias usando o template em `Wave-7-F1-Referencias-Intake-e-Benchmark.md`.
2. Rodar Wave 7 curta para cada referencia.
3. Atualizar o doc de Wave 7 com aprendizados aplicaveis, nao aplicaveis e riscos.
4. Atualizar `Plano-de-Acao-F1-Pre-Wave-5B.md`.
5. Pedir aprovacao para executar Wave 5B no template.

## Decisao mantida ate nova evidencia

F1 deve seguir como Google Slides nativo, com base Winning em slide master, 4 layouts-base e QA por thumbnail. Wave 5B so deve aplicar mudancas depois da Wave 7 aplicavel e do plano pre-5B aprovado.
