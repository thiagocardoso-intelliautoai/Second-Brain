---
source: Wave 2 Project OS conversion
created_at: 2026-05-16
status: active
classification: project-os
last_reviewed: 2026-05-21
external_repo: "D:\\1AWinningSales-Projetos\\squadfactory\\squads\\playbook-comercial-squad"
runtime_path: "04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/07-Runtime-Squad"
legacy_repo_status: "historico / nao editar por padrao"
---

# Squad Playbook de Vendas - Cockpit

## Estado atual confirmado

Este e o projeto ativo prioritario da Winning Sales no ciclo atual.

Fatos confirmados:

- Rafael direcionou a prioridade operacional para o Playbook de Vendas.
- O runtime principal do squad agora vive neste Project OS do Playbook, em `07-Runtime-Squad/`.
- O framework AIOX v5.2.7 foi instalado na raiz deste Project OS em 2026-05-18, com `.aiox-core/`, `.codex/`, `.claude/`, `.env.example` e `AGENTS.md` raiz.
- AIOX passa a ser camada de orquestracao/IDE; a fonte canonica do Playbook permanece em `07-Runtime-Squad/`.
- O repo externo antigo `D:\1AWinningSales-Projetos\squadfactory\squads\playbook-comercial-squad` virou legado/historico e nao deve receber trabalho novo por padrao.
- O runtime migrado tem agentes, tasks, workflows, skills, checklists, templates, registry, docs e validacoes locais.
- O manifesto do repo registra a versao `0.7.0`.
- O QA integrado de templates em 2026-05-14 registrou o squad como pronto para piloto end-to-end controlado.
- Existe um input bruto de melhoria em `C:\Users\thiag\Downloads\Melhorar Playbook de vendas Templates.txt`, capturado em [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/01-Inputs/2026-05-15-Melhorar-Playbook-de-vendas-Templates|input bruto da Wave 2]].
- A Wave 1 de migracao foi executada em 2026-05-17 e documentada em [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/02-Process/Runtime-Squad-Historico/MANIFESTO-DE-MIGRACAO|Manifesto de Migracao]].
- O cockpit operacional unico agora vive em [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/02-Process/00-Cockpit/STATUS-ATUAL|Status Atual - Squad Playbook de Vendas]].
- Regra operacional atual: story e a unidade de execucao; wave e agrupamento, marco historico ou checkpoint.

## Proxima acao real

Default operacional revisado:

> O repo `D:\1AWinningSales-Projetos\squadfactory\squads\playbook-comercial-squad` deve ser autossuficiente para operar e evoluir o squad. Contextos externos podem apoiar gestao e auditoria, mas decisoes, waves, prompts e criterios que afetem o squad precisam existir no repo operacional.

Fila operacional atual:

> Usar primeiro [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/02-Process/00-Cockpit/STATUS-ATUAL|Status Atual - Squad Playbook de Vendas]]. O backlog curto continua em [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/02-Process/Backlog-Operacional-Atual|Backlog Operacional Atual - Stories x Waves]]. Daqui para frente, story e a unidade de execucao; wave e agrupamento/marco. Quando houver wave historica, ela deve apontar para uma story ou story-espelho.

Ordem sugerida agora:

0. Na apresentacao da proxima etapa para Rafinha, pedir os insumos base para calcular a equacao de valor da automacao assistida: tempo medio antes e custo/hora ou custo mensal do consultor. Thiago calcula depois as horas economizadas e o R$ economizado quando tiver a etapa finalizada. Ver [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/02-Process/Equacao-de-Valor-ROI-Automacao-Assistida|Equacao de Valor - ROI da Automacao Assistida]].
1. F2 ja foi promovido por registry na Wave 6 e teve metadata/pasta normalizadas em 2026-05-20: o master oficial atual e `1uMch8PIUm_M3DkuAKxYRgjWdpbpxDsKzjLMSjlLup3g`, em `Templates Master/01-funil-kpis`. As Waves 3/4/6 agora estao espelhadas em `02-Process/Artefatos/F2-master-kpis-sheet-winning/00-stories-espelho.md`.
2. F11/ROI ja foi promovido por registry e teve metadata normalizada em 2026-05-20: o master oficial atual e `1OWeAadbcnuqcjXVtx8-6S16XAbgKnT4S2NkKwQWu8Zw`. A frente ROI agora esta espelhada em `02-Process/Artefatos/F11-master-roi-calculator-winning/07-stories-espelho.md`.
3. Para F1, tratar Stories 1-9 como concluidas e usar os contratos reforcados apenas em nova geracao/revisao.
4. Rodar Wave 2 quando a prioridade voltar a ser infra: MCP/Codex/Claude Code/Google Workspace + auditoria do Design System.
5. Se Rafael trouxer referencias, usar como insumo transversal para a wave ativa.

## Decisores e aprovadores

- Thiago: owner operacional de IA/automacao e manutencao deste cockpit.
- Rafael/Rafinha: decisor de prioridade e aprovador da direcao do Playbook.
- Consultor usuario do squad: validador pratico quando o squad entrar em piloto.

## Links principais

- Runtime principal: `04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/07-Runtime-Squad/`
- Cockpit operacional: [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/02-Process/00-Cockpit/STATUS-ATUAL|Status Atual - Squad Playbook de Vendas]]
- Glossario stories/waves: [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/02-Process/00-Cockpit/GLOSSARIO-STORIES-WAVES|Glossario - Stories, Waves e Artefatos]]
- Framework AIOX: `04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/.aiox-core/`
- Instrucoes raiz AIOX/Codex: `04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/AGENTS.md`
- Instrucoes do runtime: `04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/07-Runtime-Squad/AGENTS.md`
- Manifesto do squad: `04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/07-Runtime-Squad/squad.yaml`
- Registry de templates: `04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/07-Runtime-Squad/templates/TEMPLATE_REGISTRY.md`
- QA historico de templates: `04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/02-Process/Runtime-Squad-Historico/wave4.2-template-qa.md`
- Repo legado: `D:\1AWinningSales-Projetos\squadfactory\squads\playbook-comercial-squad`
- Historico interno do runtime: [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/02-Process/Runtime-Squad-Historico/README|Runtime Squad Historico]]
- Manifesto da migracao: [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/02-Process/Runtime-Squad-Historico/MANIFESTO-DE-MIGRACAO|Manifesto de Migracao]]
- Referencias externas do runtime: [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/02-Process/Runtime-Squad-Historico/REFERENCIAS-EXTERNAS|Referencias Externas]]
- Artefatos legados: [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/02-Process/Runtime-Squad-Historico/ARTEFATOS-LEGADOS|Artefatos Legados]]
- Mapa do repo no Second Brain: [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/02-Process/Mapa-do-Squad-e-Repo-Externo|Mapa do Squad e Repo Externo]]
- Backlog operacional atual: [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/02-Process/Backlog-Operacional-Atual|Backlog Operacional Atual - Stories x Waves]]
- Wave 1 migracao: [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/02-Process/Wave-1-Exportacao-Repo-para-Second-Brain|Wave 1 - Migracao Completa do Squad para o Project OS]]
- Artefatos externos: [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/03-Outputs/Links-e-Artefatos-Externos|Links e Artefatos Externos]]
- Guia local de feedback: [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/04-Feedback/README|Feedback - Squad Playbook de Vendas]]
- QA destilado: [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/04-Feedback/2026-05-14-QA-Templates|QA Templates]]

## Decisoes abertas

- A proxima entrega para Rafael deve ser melhoria especifica dos templates, validacao geral do squad ou piloto end-to-end controlado?
- A proxima evolucao real do F2 deve ser QA de geracao real, nao nova decisao Low/Mid/High; essa decisao foi fechada como aba unica `PROSPECCAO`.
- A melhoria visual de apresentacoes deve virar skill local do Playbook ou criterio dentro dos agents de geracao de slides?
- Quais modelos reais de DBA/DBS/ROI Rafael quer usar como referencia canonica?
- Qual criterio minimo define que o output esta bom o suficiente para demonstrar a cliente ou consultor?
- Qual foi o ROI operacional da automacao assistida do Playbook: horas economizadas por playbook, custo/hora do consultor e R$ economizado?

## O que nao fazer aqui

- Nao voltar a tratar o repo legado como runtime vivo.
- Nao copiar outputs pesados para o runtime sem manifesto e motivo.
- Nao manter dois runtimes vivos depois da migracao validada.
- Nao copiar outputs pesados, imagens, `tmp-wave*`, workspaces ou builds temporarios.
- Nao editar `.codex/` ou `.claude/` diretamente como fonte de estrategia; no runtime, a fonte canonica fica em `agents/*.md` e arquivos compartilhados.
- Nao tratar os agentes AIOX da raiz como substitutos dos agentes canonicos do Playbook em `07-Runtime-Squad/agents/`.
- Nao preencher `.env` com credenciais reais dentro do projeto compartilhavel; manter secrets locais e privados.
- Nao pesquisar ferramentas externas nesta wave.

## Subpastas

- [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/00-Project-Brief|00 - Project Brief]]
- [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/01-Inputs/2026-05-15-Melhorar-Playbook-de-vendas-Templates|01 - Inputs]]
- [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/02-Process/Mapa-do-Squad-e-Repo-Externo|02 - Process]]
- [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/02-Process/00-Cockpit/STATUS-ATUAL|02 - Cockpit operacional]]
- [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/03-Outputs/Links-e-Artefatos-Externos|03 - Outputs]]
- [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/04-Feedback/README|04 - Feedback]]
- [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/05-Skills/Skills-Locais-Candidatas|05 - Skills]]
- [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/06-Logs/2026-05-16-Wave-2-Conversao-Project-OS|06 - Logs]]
- [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/07-Runtime-Squad/README|07 - Runtime Squad]]
