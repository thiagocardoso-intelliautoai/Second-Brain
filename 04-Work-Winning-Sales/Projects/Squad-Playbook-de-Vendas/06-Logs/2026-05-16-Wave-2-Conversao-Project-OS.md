---
source: Codex execution
created_at: 2026-05-16
updated_at: 2026-05-17
status: log
---

# Log - Wave 2 Conversao Project OS

## Decisao original

O Playbook de Vendas virou Project OS no Second Brain.

Motivo:

- e a prioridade ativa da Winning Sales;
- tem repo externo operacional;
- tem muitos inputs, outputs, validacoes, agentes, skills e feedback;
- arquivo unico estava ficando fraco para acompanhar o estado real.

## Atualizacao de 2026-05-17

Esta atualizacao corrigiu uma perda de contexto: quatro arquivos tinham sido criados a partir de um prompt incompleto e deixaram sumir frentes importantes do prompt original.

Nao foi feita pesquisa web de MCP. A pesquisa de MCP continua marcada como `a pesquisar`, porque depende de fontes atualizadas de 2025 ou mais recentes.

Nao foi editado o repo externo. A leitura do repo e do Design System foi apenas para orientar a documentacao.

## Revisao estrategica posterior em 2026-05-17

Thiago questionou a decisao "extrair seletivamente" por ela ser ambigua e possivelmente overengineered.

Decisao revisada novamente:

- abandonar "extrair seletivamente" e tambem abandonar o meio-termo "cockpit aqui, runtime la";
- transformar a nova Wave 1 em **migracao completa do Squad para o Active Project**;
- criar `07-Runtime-Squad/` como runtime novo;
- fazer copia mecanica primeiro, com proveniencia;
- destilar depois;
- criar criterios de migracao para garantir completude;
- verificar referencias fora de `D:\1AWinningSales-Projetos\squadfactory\squads\playbook-comercial-squad` antes de considerar a migracao boa;
- marcar o repo antigo como legado/historico depois da validacao.

Arquivo criado:

- [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/02-Process/Wave-1-Exportacao-Repo-para-Second-Brain|Wave 1 - Migracao Completa do Squad para o Active Project]]

Atualizacao posterior em 2026-05-17: a Wave 1 foi executada e o runtime novo passou a viver em [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/02-Process/Runtime-Squad-Historico/MANIFESTO-DE-MIGRACAO|07-Runtime-Squad]].

## Diagnostico dos arquivos fracos

| Arquivo | Problema encontrado | Correcao aplicada |
|---|---|---|
| `02-Process/Mapa-do-Squad-e-Repo-Externo.md` | Assumia "nao duplicar repo" rapido demais e depois ficou ambiguo com "extrair seletivamente" | Refeito com decisao de migracao completa para `07-Runtime-Squad/` |
| `03-Outputs/Links-e-Artefatos-Externos.md` | Listava links basicos, mas nao registrava Design System, MCP, sheets de referencia, artefatos pendentes e status | Refeito como indice de artefatos externos com status, links, paths e proximas acoes |
| `04-Feedback/2026-05-14-QA-Templates.md` | Era apenas destilacao do QA original e nao continha o protocolo tecnico de Slides/Sheets/Docs pedido no prompt | Transformado em protocolo de QA Sim/Nao para Slides, Sheets e Docs |
| `06-Logs/2026-05-16-Wave-2-Conversao-Project-OS.md` | Registrava so a conversao inicial e nao explicava o que ficou faltando | Atualizado com diagnostico, decisoes, pendencias e backlog por wave |

## Decisoes tomadas nesta atualizacao

1. Posicao estrategica revisada: migrar o squad completo para o Active Project.
2. O Active Project deve conter decisao, roadmap, prompts, criterios de qualidade, links, status, logs e runtime novo.
3. O repo externo antigo vira legado/historico depois da validacao.
4. A migracao deve ser mecanica antes de ser interpretativa.
5. Duplicacao sem inventario vira risco; migracao com contagem, exclusoes mecanicas e mapa de dependencias reduz esse risco.
6. A Wave 2 de MCP/Claude Code precisa primeiro auditar o Design System local antes de procurar skills externas.
7. A Wave 4 do `master-kpis-sheet-winning` nao deve ser tratada como ajuste simples de planilha: ela pode afetar agent, task, skill, checklist, registry e fluxo ponta a ponta.
8. A Wave 5 de apresentacoes deve focar em slide-mestre + mapa de variaveis antes de implementar logica.
9. A Wave 6 exige veredito obrigatorio Sim/Nao por artefato, sem "depende".
10. Referencias do Rafael entram como Wave 7 e precisam ser separadas por Thiago antes de benchmark util.

## Waves operacionais registradas

| Wave | Frente | Status atual | Proxima acao |
|---|---|---|---|
| Wave 0 | Conversao inicial do Project OS | Feita, revisada | Manter como historico do cockpit inicial |
| Wave 1 | Migracao completa do squad para o Active Project | Concluida em 2026-05-17 | Runtime migrado, manifestos criados, validacoes passaram e repo legado virou historico |
| Wave 2 | Migracao/infra Claude Code + MCP Google Workspace | A pesquisar | Auditar Design System e pesquisar MCPs com fontes 2025+ |
| Wave 3 | Templates e variaveis dos entregaveis | Backlog | Criar mapa de variaveis por entregavel |
| Wave 4 | KPI Sheet / PROSPECCAO / Low-Mid-High touch | Backlog prioritario | Comparar master atual com referencia e decidir estrutura |
| Wave 5 | Redesign de apresentacoes | Backlog | Analisar uma apresentacao por vez com Design System lido |
| Wave 6 | QA tecnico de Slides, Sheets e Docs | Protocolo documentado | Aplicar QA Sim/Nao ao primeiro artefato |
| Wave 7 | Referencias do Rafael e benchmark | Dependente de Thiago | Separar referencias e rodar analise uma por vez |

## O que foi criado na conversao inicial

- `PROJECT.md` como cockpit.
- `00-Project-Brief.md` como brief vivo.
- `01-Inputs/2026-05-15-Melhorar-Playbook-de-vendas-Templates.md` com input bruto preservado.
- `02-Process/Mapa-do-Squad-e-Repo-Externo.md` com mapa do repo.
- `03-Outputs/Links-e-Artefatos-Externos.md` com links e artefatos externos.
- `04-Feedback/2026-05-14-QA-Templates.md` com destilacao do QA.
- `05-Skills/Skills-Locais-Candidatas.md` com candidatas reais, sem criar skills ainda.

## O que ficou fora, por decisao naquele momento

- Codigo e arquivos operacionais do repo externo, depois migrados na Wave 1 para `07-Runtime-Squad/`.
- Outputs pesados em `tmp-wave3` e `tmp-wave4`.
- Wrappers `.codex` e `.claude`, depois migrados na Wave 1 como derivados dos agentes canonicos.
- Pesquisa externa de ferramentas.
- Execucao de piloto.
- Edicao do repo externo.
- Instalacao real de MCP ou skills externas.

## Achados de leitura do repo externo

Repo operacional:

```text
D:\1AWinningSales-Projetos\squadfactory\squads\playbook-comercial-squad
```

Leitura confirmou:

- `squad.yaml` registra versao `0.7.0`;
- o squad declara 7 agentes;
- `agents/*.md` sao fonte canonica;
- `.codex/agents/*.toml` e `.claude/agents/*.md` sao wrappers;
- MCP deve ser tratado por capacidade, nao por fornecedor fixo;
- `master-kpis-sheet-winning` e F2 no registry;
- agent dono provavel do KPI sheet: `foundation-agent`;
- task dona: `tasks/generate-funnel-kpis.md`;
- skills envolvidas: `find-replace-placeholders` e `identidade-visual-dupla`;
- checklist afetado: `checklists/camada-b-01-funil-kpis.md`;
- coerencia com ROI passa por `checklists/camada-c-cross-deliverable.md`.

## Achados de leitura do Design System

Path:

```text
D:\1AWinningSales-Projetos\squadfactory\Design System
```

Leitura rapida confirmou a existencia de:

- `README.md`;
- `SKILL.md`;
- `REFERENCE.md`;
- `PATTERNS.md`;
- `DESIGN.md`;
- `VALIDATION.md`;
- `colors_and_type.css`;
- `tokens.yaml`;
- `tokens.tailwind.js`;
- `assets/`;
- `ui_kits/`;
- `v2/`.

Isto nao substitui a auditoria da Wave 2/Wave 5. Apenas confirma que ha material local antes de buscar skills externas.

## Pendencias abertas

| Pendencia | Wave | Tipo |
|---|---|---|
| Migrar contexto e runtime do repo para `07-Runtime-Squad/` com inventario e criterios de completude | Wave 1 | Concluido em [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/02-Process/Runtime-Squad-Historico/MANIFESTO-DE-MIGRACAO|Manifesto de Migracao]] |
| Escanear referencias fora do repo e classificar dependencias | Wave 1 | Concluido em [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/02-Process/Runtime-Squad-Historico/REFERENCIAS-EXTERNAS|Referencias Externas]] |
| Criar `07-Runtime-Squad/` dentro do Active Project | Wave 1 | Concluido |
| Pesquisar MCP server para Claude Code + Google Workspace com fontes 2025+ | Wave 2 | A pesquisar |
| Definir comando `claude mcp add`, prerequisitos e teste rapido | Wave 2 | A pesquisar |
| Auditar Design System local antes de skills externas | Wave 2 / Wave 5 | A auditar |
| Comparar `master-kpis-sheet-winning` com aba PROSPECCAO da referencia | Wave 4 | A analisar |
| Decidir Low/Mid/High touch: aba dinamica vs 3 abas vs alternativa simples | Wave 4 | A decidir |
| Mapear mudancas em agent/task/skill/checklist/registry do KPI sheet | Wave 4 | A implementar no repo apos decisao |
| Redesenhar apresentacoes uma por vez com Design System como fonte | Wave 5 | A analisar |
| Aplicar QA Sim/Nao por artefato | Wave 6 | A executar |
| Separar referencias do Rafael | Wave 7 | Depende de Thiago |

## Proximos passos recomendados

1. Wave 4: analisar `master-kpis-sheet-winning` contra a referencia de PROSPECCAO e decidir a estrutura Low/Mid/High touch.
2. Atualizar no runtime novo os arquivos afetados pelo KPI sheet somente depois da decisao: registry, task, agent, skill/checklist e validadores.
3. Wave 6: aplicar o protocolo Sim/Nao ao KPI Sheet antes de considerar pronto.
4. Wave 5: escolher uma apresentacao real para redesign, provavelmente DBA ou DBS, e rodar a analise uma por vez.
5. Wave 7: Thiago separar referencias do Rafael para benchmark de DBA, DBS, ROI e slides explicativos.
6. Wave 2: quando a prioridade for infra, pesquisar MCP Google Workspace para Claude Code com fontes atualizadas.

## Perguntas para Thiago

- Depois da Wave 1, qual frente roda primeiro: KPI Sheet, redesign de apresentacoes ou pesquisa MCP/Claude Code?
- Onde estao as referencias do Rafael que precisam entrar na Wave 7?
- A conta que vai executar o squad tera permissao de edicao nos Google Sheets/Slides/Docs usados como masters?
