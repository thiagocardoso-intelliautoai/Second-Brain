---
created_at: 2026-05-19
status: rascunho-aguardando-wave7
artifact: F1 master-funnel-diagram-winning
runtime_modified: false
drive_modified: false
depends_on:
  - Wave-5A-F1-Master-Funnel-Diagram-Winning.md
  - Wave-7-F1-Referencias-Intake-e-Benchmark.md
---

# Plano de Acao F1 - Pre-Wave 5B

## Papel deste documento

Este documento e a ponte entre Wave 5A, Wave 7 e Wave 5B.

Ele **nao e a Wave 5B**. A Wave 5B e a execucao/aplicacao no template.

Este plano existe para evitar que a IA aplique mudancas antes de:

- entender as referencias;
- separar Done for you de Do it yourself;
- priorizar gaps;
- pedir aprovacao para mexer no master e/ou runtime.

## Entrada

| Fonte | Papel |
|---|---|
| Wave 5A F1 | Diagnostico, rota, gaps e base visual |
| Auditoria detalhada F1 | Evidencias por slide e mapa de variaveis |
| Wave 7 F1 | Referencias e aprendizados aplicaveis |
| Design System Winning | Fonte visual de verdade |

## Ordem de decisao

1. Resolver bloqueadores confirmados da Wave 5A.
2. Incorporar aprendizados Wave 7 que sejam compativeis com Done for you.
3. Separar mudancas de template vs runtime.
4. Aprovar escopo da Wave 5B.
5. Executar Wave 5B.

## Plano inicial antes das referencias

| Prioridade | Acao | Origem | Gap que resolve | Artefato afetado | Precisa aprovacao? |
|---|---|---|---|---|---|
| P0 | Corrigir texto/rodape invertido do slide 4 | Wave 5A thumbnail | Defeito visual bloqueador | Template F1 | Sim |
| P0 | Corrigir numeracao quebrada em `01..05` | Wave 5A thumbnails | Leitura ruim dos estagios | Template F1 | Sim |
| P1 | Trocar Arial por Jost/Inter conforme contrato de Slides | Design System + Wave 5A | Identidade Winning fraca | Template F1 | Sim |
| P1 | Inserir logo/wordmark asset oficial no master | Design System + Wave 5A | Marca aparece como texto | Template F1 | Sim |
| P1 | Definir limites de texto por placeholder | Wave 5A | Risco de overflow no find-replace | Registry/task/checklist | Sim |
| P2 | Revisar layout do slide 2 para comunicar fluxo/handoff | Wave 5A + Wave 7 futura | Slide parece inventario | Template F1 | Sim |
| P2 | Criar regra para menos/mais de 5 estagios | Wave 5A | Template rigido demais | Registry/task/checklist/template | Sim |

## Entrada futura da Wave 7

Quando uma referencia for analisada, adicionar linhas abaixo:

| Prioridade | Acao inspirada na referencia | Referencia | Tipo da referencia | Conversao necessaria | Entra na Wave 5B? |
|---|---|---|---|---|---|
| A preencher | A preencher | A preencher | Done for you / Do it yourself / misto | A preencher | Sim / Nao / Pendente |

## Criterios para entrar na Wave 5B

Uma acao so entra na Wave 5B se:

- melhora um gap confirmado da Wave 5A;
- respeita o Design System Winning;
- nao transforma o F1 em aula/manual/workshop;
- preserva editabilidade nativa no Google Slides;
- nao quebra placeholders e find-replace;
- tem aprovacao humana quando afetar template master ou runtime.

## O que fica fora da Wave 5B

- Redesign pesado sem referencia aprovada.
- Mudanca em agents/tasks/skills/checklists sem plano explicito.
- Copia direta de material Do it yourself.
- Instrucao interna visivel no entregavel final.
- HTML/CSS como entrega final do F1.

## Definition of Ready para executar Wave 5B

| Item | Estado |
|---|---|
| Wave 5A concluida | Sim |
| Auditoria detalhada preservada | Sim |
| Referencias Wave 7 relevantes analisadas | Pendente |
| Plano pre-5B priorizado | Rascunho |
| Aprovacao para alterar Google Slides master | Pendente |
| Aprovacao para alterar runtime, se necessario | Pendente |

## Proximo passo

Receber referencias pelo template de `Wave-7-F1-Referencias-Intake-e-Benchmark.md`, analisar, atualizar este plano e so entao pedir aprovacao para Wave 5B.
