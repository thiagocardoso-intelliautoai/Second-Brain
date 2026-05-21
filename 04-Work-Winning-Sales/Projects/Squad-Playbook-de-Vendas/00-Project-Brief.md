---
source: Wave 2 Project OS conversion
created_at: 2026-05-16
status: active-brief
---

# Project Brief - Squad Playbook de Vendas

## Objetivo

Automatizar e sistematizar a criacao do Playbook de Vendas da Winning Sales, saindo de um documento monolitico para um conjunto de entregaveis praticos, validaveis e reutilizaveis.

## Por que importa agora

Winning Sales e a prioridade operacional e financeira atual de Thiago. Rafael direcionou o foco imediato para o Playbook de Vendas.

O projeto tambem e estrategico porque transforma conhecimento de consultoria em sistema:

- aumenta capacidade de entrega;
- reduz dependencia de consultor senior para cada documento;
- cria ativos reutilizaveis;
- pode virar prova interna de como IA aumenta margem sem derrubar criterio.

## Contexto

A leitura original do Notion continua valida:

> O conteudo e bom - o formato monolitico mata o uso pratico.

O runtime migrado em `07-Runtime-Squad/` ja evoluiu para um squad markdown-first, com 7 subagentes, 12 entregaveis, validacao humana entre etapas, template-masters no Google Workspace e fallback manual quando MCPs nao estiverem disponiveis.

## Escopo

Dentro do escopo:

- cockpit e runtime principal do squad dentro deste Project OS do Playbook;
- registro de inputs relevantes;
- mapa do repo externo;
- migracao completa da camada de contexto e runtime do repo antigo para `07-Runtime-Squad/`;
- inventario de dependencias externas;
- criterios de pronto e qualidade;
- feedback de QA;
- logs de decisoes;
- lista curta de skills locais candidatas.

Fora do escopo da conversao inicial:

- editar o repo legado, salvo recuperacao/auditoria explicita;
- rodar piloto end-to-end;
- criar novas skills locais de fato;
- copiar outputs pesados, workspaces temporarios ou builds sem manifesto;
- pesquisar ferramentas externas.

## Entregaveis do squad

O squad externo trabalha com 12 entregaveis principais:

| # | Entregavel | Tipo |
|---|---|---|
| 0 | Guia de Uso / Indice Mestre | Docs |
| 1 | Funil de Vendas + KPIs | Slides + Sheets |
| 2 | ICP & Persona | Docs + Sheets + imagens |
| 3 | Guia de Prospeccao e Qualificacao | Docs + Slides |
| 4 | Sequencia de Outreach | Sheets |
| 5 | Guia de DBA | Docs + Slides |
| 6 | Guia de DBS | Docs + Slides |
| 7 | Deck de Proposta Comercial | Slides |
| 8 | Battle Cards | Slides |
| 9 | Calculadora de ROI | Sheets |
| 10 | Provas Sociais | Docs + Slides |
| 11 | Matriz de Objecoes | Sheets |

## Criterios de qualidade

Um output bom precisa:

- ser utilizavel por consultor e vendedor, nao apenas bonito;
- preservar criterio humano em pontos sensiveis;
- reduzir friccao de criacao sem esconder decisao importante;
- ter placeholders resolvidos ou pendencias explicitas;
- manter coerencia entre entregaveis;
- funcionar com MCP quando disponivel e fallback manual quando necessario;
- passar por revisao humana antes de proxima etapa relevante.

## Criterio de pronto da Wave 1 revisada

A Wave 1 revisada foi concluida em 2026-05-17 quando:

- o inventario do repo externo foi gerado;
- `07-Runtime-Squad/` foi criado;
- os arquivos de contexto e runtime foram migrados com proveniencia para o Project OS do Playbook;
- arquivos excluidos possuem motivo mecanico registrado em [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/02-Process/Runtime-Squad-Historico/ARTEFATOS-LEGADOS|Artefatos Legados]];
- referencias externas foram escaneadas e classificadas em [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/02-Process/Runtime-Squad-Historico/REFERENCIAS-EXTERNAS|Referencias Externas]];
- paths suspeitos, como caminhos antigos de Design System, foram marcados como `a verificar`;
- validacoes minimas foram rodadas no novo runtime;
- o Project OS aponta para o novo runtime;
- o repo antigo foi marcado operacionalmente como legado/historico no cockpit.

## Riscos

- Fazer migracao parcial e perder contexto importante.
- Copiar o repo sem criterio e sujar o vault com output pesado.
- Reescrever como resumo aquilo que deveria entrar como fonte bruta.
- Manter dois runtimes vivos depois da virada e gerar divergencia.
- Confundir melhoria de template com redesenho completo do squad.
- Tentar resolver low/mid/high touch com estrutura complexa demais.
- Melhorar apresentacoes visualmente sem criterio de uso em reuniao real.
- Rodar piloto antes de decidir se os ajustes de template sao bloqueadores.

## Perguntas para Thiago

- O que Rafael precisa ver primeiro: melhoria dos templates, validacao geral ou piloto controlado?
- Qual documento real de DBA/DBS do Rafael deve virar referencia principal?
- A calculadora de ROI de referencia ja esta em Drive/local path especifico?
