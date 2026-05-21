---
source: Wave 2 Project OS conversion
created_at: 2026-05-16
status: candidate-list
---

# Skills Locais Candidatas

Esta lista nao cria skills ainda. Ela registra candidatas reais que apareceram a partir do estado do repo e do input de melhoria.

## 1. Melhorar Apresentacao de Entregavel

Uso:

- melhorar DBA, DBS, proposta, battle cards, funil e outros slides;
- reduzir textao;
- adicionar imagem quando ajuda apresentacao real;
- preservar clareza para consultor apresentar ao cliente.

Input esperado:

- template atual;
- modelo de referencia Rafael;
- objetivo da apresentacao;
- nivel de personalizacao permitido.

Output esperado:

- recomendacoes de layout;
- criterios de densidade visual;
- lista de ajustes no template;
- prompt aplicavel ao agent responsavel.

## 2. Aprimorar KPI Sheet por Complexidade

Uso:

- atualizar `master-kpis-sheet-winning`;
- incorporar logica low touch / mid touch / high touch;
- decidir se a planilha deve ter abas separadas, seletor ou regra de limpeza.

Input esperado:

- planilha de referencia;
- Design System Winning Sales;
- contrato atual F2 no registry;
- criterios de complexidade do ticket medio.

Output esperado:

- decisao de estrutura;
- alteracoes necessarias no registry;
- agents/tasks/checklists afetados;
- regra operacional para consultor ou squad.

## 3. Triar Referencias de DBA/DBS/ROI

Uso:

- separar o que cada referencia real deve influenciar;
- evitar jogar todos os insumos no mesmo prompt.

Input esperado:

- modelo de DBS criado por Rafael;
- modelo de DBA, se existir;
- calculadora de ROI de referencia;
- objetivo de cada entregavel.

Output esperado:

- mapa referencia -> template afetado;
- regras reaproveitaveis;
- pontos que nao devem ser copiados.

## 4. Localizar Dono de Mudanca no Squad

Uso:

- antes de alterar o runtime novo `07-Runtime-Squad/`;
- encontrar agent, task, checklist, skill e registry envolvidos.

Input esperado:

- nome do entregavel ou template;
- mudanca desejada.

Output esperado:

- arquivos afetados;
- ordem segura de edicao;
- testes obrigatorios.

## Criterio para virar skill de verdade

Uma candidata so deve virar skill local quando tiver:

- caso de uso recorrente;
- input definido;
- output esperado;
- criterio de qualidade;
- exemplo minimo;
- quando nao usar.
