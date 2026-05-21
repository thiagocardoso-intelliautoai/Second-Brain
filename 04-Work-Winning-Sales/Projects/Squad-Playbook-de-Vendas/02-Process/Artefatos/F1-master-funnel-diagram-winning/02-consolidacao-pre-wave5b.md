---
created_at: 2026-05-19
status: pronto-para-revisao
artifact: F1 master-funnel-diagram-winning
runtime_modified: false
drive_modified: false
depends_on:
  - 00-referencias-e-benchmark.md
  - 01-auditoria-1-wave5a.md
feeds:
  - 03-plano-de-acao-tecnico.md
---

# 02 - Consolidacao Pre-Wave 5B

## Papel deste documento

Este documento decide o que entra, o que nao entra e o que fica pendente antes de chamar um dev para executar a Wave 5B.

Ele existe para evitar que a Wave 5B vire uma mistura de diagnostico, benchmark e execucao. A Wave 5B deve aplicar mudancas aprovadas no F1; este documento organiza a fila antes disso.

## Estado de decisao

| Item | Estado |
|---|---|
| Wave 5A/Auditoria 1 | Concluida e consolidada em `01-auditoria-1-wave5a.md`. |
| Referencias recebidas | REF-01, REF-02, REF-03, REF-04 recebidas. |
| Referencias analisadas | REF-01, REF-02, REF-03 e REF-04 analisadas. |
| Rota tecnica | Google Slides nativo. |
| Wave 5B | Nao executada. |
| Alteracao em Drive/runtime | Nao feita. |

## Entra na Wave 5B do F1

| Prioridade | Item | Origem | Resultado esperado |
|---|---:|---|---|
| P0 | Corrigir texto/rodape invertido no slide 4 | Wave 5A | Nenhum texto invertido ou rotacionado incorretamente em thumbnail. |
| P0 | Corrigir numeracao quebrada `01..05` | Wave 5A | Numeros de etapa aparecem inteiros em slides 2, 3 e 4. |
| P1 | Migrar base tipografica para padrao Winning | Design System + Wave 5A | Jost/Inter aplicados em escala nativa de Slides; Arial removido onde for controlavel. |
| P1 | Trocar `WINNING SALES` textual por logo/wordmark oficial | Design System + Wave 5A | Assinatura visual alinhada ao Design System. |
| P1 | Reestruturar slide 2 como fluxo/handoff, nao inventario | Wave 5A + REF-01/REF-03/REF-04 | Duas swimlanes ou estrutura equivalente com progressao, contexto e handoff mais claro. |
| P1 | Ajustar slides 3 e 4 como consulta operacional premium | Wave 5A + REF-01/REF-03 | Tabela/card de detalhe mais legivel, com criterios de saida mais fortes. |
| P1 | Reforcar slide 5 como gestao executiva | Wave 5A + REF-02/REF-03/REF-04 | Metas, rituais e decisoes lidos como compromissos operacionais, nao lista solta. |
| P1 | Formalizar limites de texto por placeholder no proprio plano/dev handoff | Wave 5A + REF-03 + observacao Thiago | Dev aplica caixas com overflow previsto e QA de limite. |
| P2 | Definir tratamento de menos/mais de 5 estagios | Wave 5A | Regra operacional documentada; se alterar runtime, precisa aprovacao separada. |

## Nao entra na Wave 5B do F1

| Item | Motivo |
|---|---|
| Copiar material Do it yourself como aula | F1 e entregavel Done for you. |
| Inserir golden tips, roteiro de vendedor ou instrucoes de workshop | Isso pertence a treinamento/runtime interno, nao ao deck final do cliente. |
| Executar plano do ROI/F11 dentro do F1 | REF-02 e benchmark de outro artefato; precisa frente propria. |
| Trocar entrega final para HTML/CSS | Quebra rota Google Slides nativo e editabilidade. |
| Alterar agents/tasks/skills/checklists/templates sem aprovacao | Regra local explicita. |
| Redesign pesado sem preservar placeholders | Risco de quebrar automacao e find-replace. |
| Editar URL original `1tnc5...` como se fosse master | Master alvo deve vir do registry, salvo confirmacao humana. |

## Pendente antes de congelar execucao

| Pendencia | Severidade | Decisao necessaria |
|---|---:|---|
| Asset oficial de logo/wordmark | Alta | Confirmar local/nome do asset dentro do Design System. |
| Escala Jost/Inter em pontos para Google Slides | Alta | Definir tamanho de titulo, subtitulo, corpo, caption e numero. |
| Limite formal de texto por placeholder | Alta | Aprovar limites do `01-auditoria-1-wave5a.md` como contrato inicial. |
| Relacao `1tnc5...` vs master registry `1ML...` | Media | Definir se `1tnc5...` e comparacao, gerado, ou alvo alternativo. |
| Mudancas no runtime | Media | Se forem necessarias, criar plano separado e pedir aprovacao explicita. |

## Criterios de aprovacao para entrar na Wave 5B

- F1 continua Google Slides nativo.
- Design System Winning continua fonte visual de verdade.
- REF-01/REF-03/REF-04 entram apenas como adaptacao Done for you.
- REF-02 vira backlog F11 e benchmark transversal, nao escopo F1.
- Nenhuma instrucao interna aparece no deck final.
- Placeholders continuam presentes e compativeis com find-replace.
- Numeracao, tipografia e cards suportam outputs reais dentro dos limites aprovados.
- Toda alteracao no master/template ou runtime tem aprovacao humana antes de acontecer.

## Definition of Ready para o dev

| Item | Ready? | Observacao |
|---|---|---|
| Auditoria 1 consolidada | Sim | `01-auditoria-1-wave5a.md`. |
| Benchmark registrado | Sim | REF-01, REF-02, REF-03 e REF-04 analisadas. |
| Escopo do F1 separado do ROI/F11 | Sim | REF-02 vai para backlog proprio. |
| Plano tecnico unico | Sim, apos `03-plano-de-acao-tecnico.md` | Este sera o handoff do dev. |
| Aprovacao para editar Google Slides master | Pendente | Necessaria antes da Wave 5B real. |
| Aprovacao para mexer em runtime | Pendente | So se o plano tecnico indicar mudanca. |

## Recomendacao

Executar primeiro a Wave 5B em modo conservador:

1. Corrigir defeitos bloqueadores.
2. Aplicar base visual Winning.
3. Adaptar narrativa/fluxo com REF-01, REF-03 e REF-04.
4. Usar REF-02 apenas para leitura executiva do slide 5 e manter ROI/F11 fora do F1.
5. Converter campos/roteiros da REF-03 em variaveis, criterios ou saidas prontas, sem levar workbook para o deck.
