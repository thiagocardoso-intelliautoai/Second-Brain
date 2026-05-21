---
source: "original prompt recovery + external repo read-only inspection"
created_at: 2026-05-16
updated_at: 2026-05-20
status: process-map
external_repo: "D:\\1AWinningSales-Projetos\\squadfactory\\squads\\playbook-comercial-squad"
design_system: "D:\\1AWinningSales-Projetos\\squadfactory\\Design System"
strategic_position: "tornar o repo playbook-comercial-squad autossuficiente para operacao e evolucao"
---

# Mapa do Squad e Repo Externo

## Como ler este documento

Nota de governanca de 2026-05-21:

- O cockpit operacional atual vive em `02-Process/00-Cockpit/STATUS-ATUAL.md`.
- Story e a unidade de execucao; wave e agrupamento, marco historico ou checkpoint.
- Este mapa e contexto/roadmap. Ele nao deve ser usado como fila viva quando uma story especifica nao existir.

Este mapa tem duas naturezas diferentes:

- **Antes de `Waves operacionais do projeto`**: contexto arquitetural, limites, fontes canonicas e regras de leitura. Este bloco nao e uma fila de execucao.
- **A partir de `Waves operacionais do projeto`**: plano executavel. Toda acao concreta deve estar dentro de uma wave ou ser roteada para uma wave.

Regra pratica: se uma lacuna aparece no bloco de contexto, ela nao deve ser executada diretamente dali. Ela precisa virar item de uma wave, com dono, criterio de pronto, dependencia e evidencia esperada.

Regra de governanca adicionada em 2026-05-20: F1 foi tratado por stories; F2 esta documentado por waves. Daqui para frente, cada execucao concreta precisa ter story ou wave como documento de origem. Se um artefato usar os dois formatos, a story deve apontar para a wave correspondente e a wave deve apontar para a story correspondente. A fila curta atual vive em `02-Process/Backlog-Operacional-Atual.md`.

## Decisao estrategica

Posicao revisada em 2026-05-18: **o repo `playbook-comercial-squad` deve ser autossuficiente para operacao e evolucao do Squad Playbook Comercial**.

A formulacao anterior, em que o runtime principal ficava no Active Project e o repo externo virava legado, cria confusao quando uma IA abre diretamente:

```text
D:\1AWinningSales-Projetos\squadfactory\squads\playbook-comercial-squad
```

Regra atual:

- o repo do squad deve conter todos os insumos necessarios para operar, auditar e evoluir o squad;
- decisoes, waves, prompts e criterios que afetem o squad precisam existir dentro do repo, nao apenas em contexto externo de gestao;
- contextos externos podem servir como cockpit pessoal, log historico ou area de trabalho, mas nao como fonte operacional que o squad precise conhecer;
- `AGENTS.md` e `README.md` nao devem declarar o repo como legado se Thiago esta trabalhando diretamente nele;
- outputs pesados, previews e binarios temporarios podem continuar fora da documentacao operacional, desde que estejam inventariados quando forem relevantes.

## Por que o repo precisa ser autossuficiente

Ao abrir apenas o repo do squad, a IA precisa entender:

- qual e a arquitetura;
- quais agents, tasks, skills e checklists sao canonicos;
- quais decisoes estrategicas ja foram tomadas;
- qual e o roadmap por waves;
- quais prompts operacionais usar;
- quais criterios de QA e design aplicar;
- quais referencias externas dependem de acesso, arquivo ou validacao humana.

Se essas informacoes ficarem apenas em outro workspace, o agente pode rodar com contexto parcial, ignorar decisoes recentes ou tratar o repo como historico.

## O que nao precisa virar contexto operacional

Nem tudo precisa entrar como documento vivo do squad. Continuam podendo ficar apenas inventariados:

- previews PNG;
- PPTX/DOCX/XLSX temporarios;
- outputs em `tmp-wave*`;
- caches;
- arquivos pesados;
- exports usados apenas para auditoria historica.

## Fonte operacional por categoria

Esta tabela e um mapa de local correto para cada tipo de informacao. Ela nao e backlog paralelo. Itens marcados como lacuna so devem ser criados ou alterados quando uma wave correspondente mandar executar.

| Categoria                       | Fonte operacional correta                           | Estado atual         |
| ------------------------------- | --------------------------------------------------- | -------------------- |
| Decisoes estrategicas           | `docs/DECISOES.md` no repo do squad                 | Lacuna roteada       |
| Roadmap / waves                 | `docs/ROADMAP-WAVES.md` no repo do squad            | Lacuna roteada       |
| Prompt operacional              | `docs/PROMPTS-OPERACIONAIS.md` no repo do squad     | Lacuna roteada       |
| Agent canonico                  | `agents/`                                           | Existe               |
| Skill canonica do squad         | `skills/`                                           | Existe               |
| Task de entregavel              | `tasks/`                                            | Existe               |
| Codigo / scripts / validadores  | `scripts/`                                          | Existe               |
| Template registry               | `templates/TEMPLATE_REGISTRY.md` + Google Drive     | Existe               |
| Artefato final Google Workspace | Google Drive / Docs / Sheets / Slides               | Existe por links/IDs |
| Referencia externa              | `docs/REFERENCIAS-E-INSUMOS.md` no repo do squad    | Lacuna roteada       |
| Log de decisao e execucao       | `docs/DECISOES.md` ou `docs/logs/` no repo do squad | Lacuna roteada       |

### Triagem das lacunas roteadas

Esta secao classifica lacunas documentais, mas nao executa a criacao delas. Ela serve para orientar o que uma wave futura pode criar sem carregar lixo historico para o repo operacional.

Regra de transporte:

- transportar decisoes, dependencias, criterios e prompts que afetam diretamente `agents/`, `tasks/`, `skills/`, `checklists/`, `templates/`, `config/` ou `scripts/`;
- nao transportar rascunho bruto, texto com encoding ruim, logs narrativos, workspaces temporarios, previews, outputs pesados ou listas de candidatos ainda nao validadas;
- tudo que depender de pesquisa MCP/connector/plugin atualizada fica fora dos novos docs operacionais ate a Wave 2 ser executada e registrada com evidencia;
- manter no repo apenas o contrato generico ja existente de capacidade/fallback MCP (`config/mcp-capabilities.md` e `config/mcp-fallback-strategy.md`), porque isso e regra de portabilidade, nao escolha de fornecedor.

| Lacuna | Funcao arquitetural | Pode entrar quando uma wave executar | Nao transportar |
|---|---|---|---|
| `docs/DECISOES.md` | Registro enxuto de decisoes arquiteturais e de governanca. | Decisao de repo autossuficiente; canonicos vs wrappers; nao copiar outputs pesados; Wave 3 antes de Wave 4/5; Wave 6 como gate final; Design System atual como referencia a auditar; Low/Mid/High ainda nao decidido. | Log completo da Wave 1, texto bruto do prompt recuperado, historico de ida-e-volta entre Active Project e repo externo, candidatos MCP, detalhes de instalacao futura e paths temporarios. |
| `docs/ROADMAP-WAVES.md` | Indice operacional das Waves 0-7, com status, dependencia, proxima acao e links para docs especificos. | Sequenciamento revisado; Wave 2 como pesquisa/auditoria ainda pendente; Wave 3/6 apontando para os docs ja existentes; Wave 4 KPI Sheet; Wave 5A/5B apresentacoes; Wave 7 referencias do Rafael como insumo transversal. | Corpo longo ja duplicado em `WAVE-3-CONTRATOS-VARIAVEIS.md` e `WAVE-6-QA-GATE.md`; prompt completo de MCP; listas de ferramentas/skills candidatas; narrativas de logs. |
| `docs/PROMPTS-OPERACIONAIS.md` | Biblioteca de prompts repetiveis de execucao do squad. | Prompts de KPI Sheet, contratos/variaveis por artefato, auditoria/base de design de apresentacoes, aplicacao final de apresentacoes, QA Sim/Nao e referencias do Rafael, todos com precondicoes e outputs claros. | Prompt de pesquisa MCP/Claude Code/Google Workspace, candidatos como Impeccable/Layout/mcpmarket, comando `claude mcp add`, criterios de stars/issues/releases e qualquer recomendacao de instalacao antes da Wave 2. |
| `docs/REFERENCIAS-E-INSUMOS.md` | Indice limpo de referencias operacionais externas, nao copia de conteudo. | Design System atual, path `Design.md winning sales` marcado como `a verificar`, KPI sheet atual e referencia, referencias do Rafael como `a separar`, ROI se houver referencia real, observacao de acesso/owner dos artefatos Google. | Lista completa duplicada do registry, URLs de schema que ja vivem em `data/perfil-schema.json`, Notion/Downloads como historico, AIOX/IDE do Active Project, tmp-wave outputs, previews PNG/PPTX/DOCX/XLSX e candidatos MCP. |
| `docs/logs/` ou `docs/DECISOES.md` para logs | Mecanismo de rastro quando uma wave alterar arquivos ou templates. | Resumo de mudanca, data, arquivos afetados, validacoes rodadas e veredito quando houver alteracao real no repo operacional. | Logs conversacionais extensos, logs do cockpit pessoal, detalhes de execucao que nao mudam o contrato do squad e historico de outputs temporarios. |

Resultado pratico: os arquivos novos continuam fazendo sentido, mas a criacao deles deve acontecer via wave. O principal corte e: **MCP fica na Wave 2**, exceto a regra generica de capacidade/fallback que ja e parte do runtime.

## Repo operacional alvo

```text
D:\1AWinningSales-Projetos\squadfactory\squads\playbook-comercial-squad
```

Arquivos-guia lidos ou referenciados:

| Arquivo | Uso |
|---|---|
| `AGENTS.md` | instrucoes operacionais e regras de portabilidade |
| `README.md` | visao geral do squad e arquitetura |
| `squad.yaml` | manifesto do squad, componentes e versao `0.7.0` |
| `templates/TEMPLATE_REGISTRY.md` | registry de templates, Drive IDs e contratos |
| `02-Process/Runtime-Squad-Historico/wave4.2-template-qa.md` | QA integrado de templates |
| `config/mcp-fallback-strategy.md` | estrategia de fallback quando MCP falhar |
| `config/mcp-capabilities.md` | capacidades esperadas de MCP |
| `.mcp.example.json` | exemplo seguro, ainda sem comando real de MCP |
| `docs/repo-autossuficiente-plano.md` | plano local para fechar lacunas de decisoes, waves, prompts e referencias |

## Arquitetura atual do squad

O repo declara 7 agentes:

- `orchestrator`
- `onboarding-agent`
- `foundation-agent`
- `sales-content-agent`
- `training-agent`
- `specialty-agent`
- `reviewer-agent`

Regra importante do repo:

- `agents/*.md` sao a fonte canonica dos agentes;
- `.codex/agents/*.toml` e `.claude/agents/*.md` sao wrappers de plataforma;
- estrategia, regras e fluxo devem ser alterados primeiro nos arquivos canonicos e depois sincronizados.

Componentes principais:

| Pasta | Papel |
|---|---|
| `agents/` | 7 agentes canonicos |
| `tasks/` | tasks por entregavel e validacao |
| `workflows/` | fluxos de geracao, ciclo de entregavel e regeneracao em cascata |
| `skills/` | tecnicas reutilizaveis de prompt do squad |
| `checklists/` | validacao em camadas A, B e C |
| `templates/` | registry de templates no Google Drive |
| `config/` | padroes, stack, voz, MCP e fallback |
| `data/` | schema de perfil do cliente |
| `scripts/` | validacoes utilitarias |

## Fluxo padrao de execucao

1. Comecar pelo `orchestrator`.
2. Confirmar ferramentas e MCPs disponiveis.
3. Rodar `onboarding-agent`.
4. Gerar entregaveis pelo agente responsavel.
5. Revisar cada entregavel com `reviewer-agent`.
6. Pausar para validacao humana.
7. Usar fallback manual quando MCP nao estiver disponivel.

## Waves operacionais do projeto

| Wave   | Frente                                           | Status operacional                            | Resultado esperado                                                       |
| ------ | ------------------------------------------------ | --------------------------------------------- | ------------------------------------------------------------------------ |
| Wave 0 | Conversao inicial do Project OS                  | Feita, mas revisada                           | cockpit inicial, input recuperado e logs                                 |
| Wave 1 | Auditoria/migracao inicial do runtime            | Concluida em 2026-05-17; estrategia revisada  | inventario, manifestos, dependencias externas e validacoes               |
| Wave 2 | MCP / Codex / Claude Code / Google Workspace     | A pesquisar/a auditar                         | toolchain escolhida, Design System auditado, plano de instalacao e teste |
| Wave 3 | Metodo, criterios e contratos dos entregaveis    | Backlog bloqueador antes de alterar templates | rota por tipo, criterios previos e mapa placeholder -> dono -> fallback  |
| Wave 4 | KPI Sheet / PROSPECCAO / Low-Mid-High touch      | Backlog prioritario de template               | decisao de estrutura do sheet e mudancas no squad                        |
| Wave 5A | Auditoria e base de design de apresentacoes     | Backlog de qualidade visual                   | diagnostico por slide, slide-mestre, mapa de variaveis e criterios Winning |
| Wave 5B | Aplicacao final e polimento de apresentacoes    | Depende de Wave 5A e Wave 7 quando aplicavel  | template final aplicado sem quebrar logica, variaveis ou narrativa aprovada |
| Wave 6 | QA gate tecnico Sim/Nao                          | Protocolo base existe                         | evidencia ao vivo e veredito Sim/Nao por artefato alterado               |
| Wave 7 | Referencias do Rafael e benchmark de entregaveis | Insumo transversal dependente de Thiago       | mapa referencia -> aprendizado -> modelo afetado                         |

## Analise de eficacia das waves

Diagnostico em 2026-05-18:

- A estrutura geral esta correta, mas ainda estava arriscada porque a Wave 3 aparecia na tabela e nao existia como corpo operacional. Isso criava salto direto de infraestrutura para mudanca de template.
- A Wave 6 estava misturando duas naturezas: metodo/criterio antes da leitura e QA final depois da alteracao. Isso criava dependencia estranha de waves anteriores em uma wave posterior.
- A Wave 2 misturava duas coisas diferentes: infraestrutura MCP e auditoria do Design System. As duas podem ficar na mesma wave, mas os outputs precisam sair separados.
- A Wave 7 nao deve ser tratada como etapa final linear. Referencias do Rafael sao insumo transversal para Wave 4, Wave 5A, Wave 5B e Wave 6 assim que Thiago separar os arquivos ou links.
- Wave 4 e Wave 5A nao devem comecar "no olho". Cada artefato precisa passar antes por um recorte da Wave 3, que agora inclui metodo, criterios e contrato.
- As waves precisam produzir rastros verificaveis: matriz, evidencia, decisao, arquivos afetados e definicao de pronto. Sem isso, o agente tende a fazer diagnostico bonito mas pouco acionavel.

Sequenciamento recomendado depois da Wave 1:

1. Rodar Wave 2 para auditar Design System e decidir capacidades reais de MCP/Google Workspace.
2. Rodar Wave 3 pelo menos para o artefato que sera trabalhado primeiro, incluindo metodo, criterios e contrato.
3. Executar Wave 4 ou Wave 5A um artefato por vez.
4. Executar Wave 5B apenas para apresentacoes com Wave 5A concluida e, quando houver referencia relevante do Rafael, depois de incorporar a Wave 7.
5. Aplicar Wave 6 como gate de QA no fim de cada artefato alterado.
6. Incorporar Wave 7 como input assim que as referencias existirem; nao esperar o fim do projeto se uma referencia puder melhorar uma wave atual.

### Recorte operacional atual - F1 master-funnel-diagram-winning

Em 2026-05-19, o F1 foi separado em uma pasta propria para reduzir confusao entre Wave 5A, Wave 5B e Wave 7:

- `02-Process/Artefatos/F1-master-funnel-diagram-winning/00-referencias-e-benchmark.md`
- `02-Process/Artefatos/F1-master-funnel-diagram-winning/01-auditoria-1-wave5a.md`
- `02-Process/Artefatos/F1-master-funnel-diagram-winning/02-consolidacao-pre-wave5b.md`
- `02-Process/Artefatos/F1-master-funnel-diagram-winning/03-plano-de-acao-tecnico.md`
- `02-Process/Artefatos/F1-master-funnel-diagram-winning/04-stories-sm.md`
- `02-Process/Artefatos/F1-master-funnel-diagram-winning/06-story-9-regressao-f1-entregavel-01.md`
- `02-Process/Artefatos/F1-master-funnel-diagram-winning/07-qa-regressao-f1-entregavel-01.md`
- `02-Process/Artefatos/F1-master-funnel-diagram-winning/08-registro-drive-runtime-story9.md`

Decisao especifica do F1:

1. `00-referencias-e-benchmark.md` guarda as referencias ja enviadas por Thiago. REF-01, REF-02, REF-03 e REF-04 foram analisadas.
2. `01-auditoria-1-wave5a.md` preserva a Wave 5A ja executada. Ela nao deve ser tratada como pendente ou "antiga".
3. `02-consolidacao-pre-wave5b.md` separa o que entra, o que nao entra e o que depende de aprovacao antes de qualquer edicao.
4. `03-plano-de-acao-tecnico.md` e o handoff unico para o dev executar a Wave 5B depois de aprovacao.
5. `04-stories-sm.md` salva as stories do SM e foi atualizado apos o QA para refletir que Stories 5, 6, 8 e 9 estao concluidas. Para o F1, este e o backlog de stories; evidencias de execucao continuam em `05-qa-pos-execucao.md` e `evidencias-regressao-story9/`.
6. `06-story-9-regressao-f1-entregavel-01.md`, `07-qa-regressao-f1-entregavel-01.md` e `08-registro-drive-runtime-story9.md` fecham a regressao F1 do #01 com apresentacao QA correta no Drive, veredito Sim e runtime atualizado.

Para este recorte, a ordem operacional correta e:

`Referencias/benchmark -> Auditoria 1 consolidada -> Consolidacao pre-Wave 5B -> Plano tecnico -> Execucao Wave 5B aprovada -> QA pos-execucao -> Regressao Story 9 aprovada`.

Fila operacional atual: ver `02-Process/Backlog-Operacional-Atual.md`.

## Wave 1 - Auditoria e migracao inicial do runtime

Plano detalhado:

- [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/02-Process/Wave-1-Exportacao-Repo-para-Second-Brain|Wave 1 - Migracao Completa do Squad para o Active Project]]

Resultado historico:

- `07-Runtime-Squad/` criado como copia auditada do runtime.
- 86 arquivos de runtime/contexto migrados com checagem SHA256.
- `.codex/` e `.claude/` migrados inteiros como wrappers derivados.
- `.tmp/`, `tmp-wave3/` e `tmp-wave4/` ficaram fora do runtime principal e foram inventariados.
- Referencias externas foram classificadas.
- Validacoes minimas passaram no novo runtime.
- Esta decisao foi revisada em 2026-05-18: o repo `playbook-comercial-squad` volta a ser tratado como fonte operacional alvo e precisa receber os insumos que ainda estavam fora dele.

Arquivos de controle:

- [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/02-Process/Runtime-Squad-Historico/MANIFESTO-DE-MIGRACAO|Manifesto de Migracao]]
- [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/02-Process/Runtime-Squad-Historico/ARTEFATOS-LEGADOS|Artefatos Legados]]
- [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/02-Process/Runtime-Squad-Historico/REFERENCIAS-EXTERNAS|Referencias Externas]]
- [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/06-Logs/2026-05-17-Wave-1-Migracao-Runtime-Squad|Log da Migracao Wave 1]]

Achado importante:

- `02-Process/Runtime-Squad-Historico/template-factory-plan.md` menciona `D:\1AWinningSales-Projetos\squadfactory\Design.md winning sales`.
- Esse path existe, mas parece uma versao legada/parcial em relacao ao Design System atual em `D:\1AWinningSales-Projetos\squadfactory\Design System`.
- Ate a auditoria da Wave 2 ou Wave 5A, usar `Design System` como referencia padrao e marcar `Design.md winning sales` como `a verificar`.

## Wave 2 - MCP / Codex / Claude Code / Google Workspace

Objetivo: pesquisar, com fontes atualizadas de 2026 ou mais recentes, qual MCP server deve integrar codex (e compativel ao claude code também) com Google Workspace.

Regra de pesquisa:

- usar fontes externas atuais quando a wave for executada;
- registrar data da pesquisa e links consultados;
- separar fato confirmado de inferencia;
- nao recomendar MCP, skill ou plugin sem comando de instalacao, prerequisitos e teste minimo;
- validar compatibilidade real com Codex e Claude Code separadamente.

Prioridade de integracao:

1. Google Slides, prioridade maxima.
2. Google Sheets.
3. Google Drive.
4. Google Docs.

Criterios obrigatorios da pesquisa:

- cobertura real de tools e operacoes;
- profundidade em Slides, incluindo criacao/edicao granular com shapes, text boxes, layouts, formatacao e `batch_update_presentation`;
- maturidade: release ou commit recente, stars e issues abertas;
- OAuth 2.x, multi-user se possivel;
- compatibilidade real com Claude Code via `claude mcp add`; E conexão com Codex real também
- comando exato de instalacao;
- prerequisitos;
- teste rapido de validacao.

Auditoria local obrigatoria antes de buscar skills externas:

```text
D:\1AWinningSales-Projetos\squadfactory\Design System
```

A auditoria deve levantar:

- skills existentes no Design System;
- brand guidelines;
- templates de Slides, Docs e Sheets;
- componentes e tokens de design;
- o que o Design System ja cobre;
- gaps reais antes de instalar skill externa.

Itens ja visiveis em leitura rapida, ainda sem auditoria completa:

- `README.md`
- `SKILL.md`
- `REFERENCE.md`
- `PATTERNS.md`
- `DESIGN.md`
- `VALIDATION.md`
- `colors_and_type.css`
- `tokens.yaml`
- `tokens.tailwind.js`
- `assets/`
- `ui_kits/`
- `v2/`

Separar skills em duas familias:

| Familia | Exemplos / candidatos |
|---|---|
| Operacao MCP | Sheets, Drive, Docs e Slides; foco em operacoes reais de Google Workspace |
| Design para Slides | Impeccable, Layout skill, Claude Design, mcpmarket.com e skills instaladas como `anthropic-skills:ui-principles`, `anthropic-skills:pptx`, `anthropic-skills:winning-sales-brand`, `design:design-critique`, `design:design-system` |

Outputs obrigatorios:

- matriz comparativa de candidatos MCP/connector/plugin;
- veredito recomendado para Slides, Sheets, Docs e Drive separadamente;
- inventario do Design System com o que ja existe e o que falta;
- lista do que nao precisa ser instalado porque o Design System local ja cobre;
- plano de instalacao com comando exato, prerequisitos, riscos, rollback e teste minimo;
- decisao sobre o que entra no repo operacional do squad e o que fica apenas como referencia externa.

Prompt operacional preservado:

```text
Pesquise, usando fontes de 2026 ou mais recentes, qual MCP server e a melhor escolha para integrar Claude Code com Google Workspace no contexto do Squad Playbook Comercial da Winning Sales.

Priorize Google Slides acima de Sheets, Drive e Docs. Para cada candidato, avalie:
- cobertura real de tools e operacoes;
- profundidade em Slides: criar e editar apresentacoes, shapes, text boxes, layouts, formatacao, imagens, speaker notes quando aplicavel e batch_update_presentation;
- maturidade: release ou commit recente, stars, issues abertas e sinais de manutencao;
- OAuth 2.x e suporte multi-user quando existir;
- compatibilidade real com Claude Code via claude mcp add;
- comando exato de instalacao;
- prerequisitos;
- teste rapido de validacao.

Antes de recomendar qualquer skill externa, audite localmente:
D:\1AWinningSales-Projetos\squadfactory\Design System

Levante:
- skills existentes;
- brand guidelines;
- templates de Slides, Docs e Sheets;
- componentes e tokens de design;
- o que o Design System ja cobre;
- gaps reais.

Separe a recomendacao em:
1. skills ou MCPs de operacao para Sheets, Drive, Docs e Slides;
2. skills de design para Slides.

Inclua plano de instalacao com comando, prerequisitos, riscos e teste minimo.
Marque como "a pesquisar" tudo que depender de fonte externa atualizada.
```

## Wave 3 - Metodo, criterios e contratos dos entregaveis

Objetivo: antes de alterar qualquer template, definir a melhor rota de producao, os criterios de avaliacao e o contrato testavel entre template, registry, agents, tasks, skills e checklists.

Decisao revisada em 2026-05-18: **nao criar teste completo de cada entregavel como primeira acao da Wave 3**. A primeira acao deve ser analise automatizada e manual do modelo/contrato. Teste completo entra apenas para o artefato priorizado, para um smoke test representativo ou depois que o modelo estiver estabilizado.

Decisao revisada em 2026-05-18: **a antiga etapa de metodo/criterios que estava dentro da Wave 6 foi movida para a Wave 3**. Pesquisa de metodo e definicao de criterios precisam acontecer antes da leitura/alteracao; a Wave 6 fica apenas como QA gate final Sim/Nao.

Por que esta wave existe:

- evita pular direto para redesign ou mudanca de planilha sem saber quem preenche cada variavel;
- evita diagnosticar Slides, Sheets ou Docs sem criterios definidos antes;
- reduz risco de placeholder sem dono, texto variavel grande demais, formula quebrada ou instrucao operacional aparecendo no entregavel final;
- cria base para Wave 4, Wave 5A, Wave 5B e Wave 6 funcionarem com criterio, nao por intuicao.

Escopo:

- todos os entregaveis F1-F14 do `templates/TEMPLATE_REGISTRY.md`;
- priorizar primeiro o artefato que entrar em execucao, por exemplo F2 se a proxima frente for KPI Sheet;
- considerar Docs, Sheets, Slides e auxiliares como contratos separados quando o mesmo F tiver mais de um artefato;
- usar outputs legados `tmp-wave3/` e `tmp-wave4/` apenas como evidencia historica, nao como fonte viva.

Entradas obrigatorias por entregavel:

- especificacao no `templates/TEMPLATE_REGISTRY.md`;
- template real no Google Drive ou exportacao local verificavel;
- agent dono;
- task dona;
- skills usadas;
- checklist Camada A, Camada B e, quando aplicavel, Camada C;
- dependencias com outros entregaveis;
- fallback MCP/manual relevante.

Matriz obrigatoria de variaveis:

| Campo | Pergunta |
|---|---|
| Placeholder | Qual token exato aparece no template real? |
| Artefato | Em qual F, arquivo, aba, slide, secao ou celula ele aparece? |
| Tipo | Texto curto, texto longo, numero, data, lista, imagem, tabela, link ou formula? |
| Dono | Qual agent/task/skill e responsavel por preencher? |
| Origem | De onde vem o dado: onboarding, perfil, entregavel anterior, benchmark, input manual ou calculo? |
| Limite | Qual tamanho maximo seguro para nao quebrar layout, formula ou leitura? |
| Transformacao | Precisa resumir, normalizar, traduzir, formatar moeda, data, porcentagem ou lista? |
| Fallback | O que acontece se a variavel nao existir ou MCP falhar? |
| Risco | Placeholder sem dono, textao, formula vulneravel, variavel visual, hardcoded ruim ou dependencia externa? |
| Arquivos afetados | Registry, agent, task, skill, checklist, template ou prompt operacional? |

Metodo e criterios obrigatorios antes da leitura:

| Tipo | Decisao antes de diagnosticar |
|---|---|
| Slides | Melhor rota de producao: Google Slides nativo, HTML/CSS -> PPTX, PptxGenJS, PowerPoint nativo, screenshots de HTML ou outra. Criterios: narrativa, hierarquia, grid, densidade, tipografia, cor, imagens/icones/graficos, speaker usability e identidade Winning. |
| Sheets | Melhor rota de producao: duplicar master, criar via API, editar via conector/plugin ou outra. Criterios: clareza de input, formulas auditaveis, validacoes, protecoes, formatacao condicional, referencias cruzadas, locale/timezone e tolerancia a placeholders. |
| Docs | Melhor rota de producao: Docs nativo, Markdown/HTML -> Docs ou outra. Criterios: estrutura, headings, tabelas, bullets, TOC, paginacao, estilos, densidade e legibilidade. |

Processo recomendado:

1. Rodar no repo operacional: `python scripts\analyze-template-contracts.py`.
2. Ler o relatorio `docs/WAVE-3-CONTRACT-AUDIT-REPORT.md`.
3. Para o tipo de artefato priorizado, definir rota de producao e criterios antes da leitura.
4. Para o artefato priorizado, ler registry, agent, task, skill e checklist antes de abrir o template.
5. Extrair/listar placeholders reais do template ou do export disponivel, se houver acesso.
6. Comparar placeholder real vs registry vs task vs agent.
7. Classificar cada elemento como Universal, Variavel de apresentacao, Variavel de slide/secao/celula ou Hardcoded ruim.
8. Registrar achados enquanto le, com evidencia e localizacao. Nao guardar tudo para o final.
9. Criar backlog de correcao por arquivo afetado.
10. Fazer smoke test minimo apenas se a analise de contrato nao responder um risco critico.
11. So depois liberar Wave 4 ou Wave 5A para aquele artefato.

Definition of Done:

- matriz de variaveis completa para o artefato analisado;
- rota de producao e criterios definidos para o tipo de artefato;
- relatorio automatico de contrato gerado;
- divergencias registry/template/task/agent/checklist listadas;
- placeholders sem dono marcados como bloqueio;
- limites de texto definidos para variaveis que entram em slide, tabela, celula ou bullet;
- impacto em MCP/fallback registrado;
- prompt operacional do entregavel atualizado ou pronto para ser atualizado.

Prompt operacional:

```text
Analise um entregavel do Squad Playbook Comercial por vez e monte o contrato de variaveis antes de qualquer redesenho ou alteracao de template.

Antes da analise manual, rode:
python scripts\analyze-template-contracts.py

Use o relatorio gerado para escolher onde concentrar a leitura humana/IA.

Leia primeiro:
- templates/TEMPLATE_REGISTRY.md;
- agent dono;
- task dona;
- skills usadas;
- checklists Camada A/B/C relevantes;
- fallback MCP/manual relevante.

Depois compare com o template real ou export verificavel.

Para cada placeholder ou elemento variavel, registre:
- token exato;
- localizacao;
- tipo de dado;
- dono;
- origem;
- limite de tamanho;
- transformacao necessaria;
- fallback;
- risco;
- arquivos afetados.

Anote os achados enquanto encontrar, com evidencia. Nao espere o final para reconstruir de memoria.

Ao final, entregue:
1. matriz de variaveis;
2. divergencias encontradas;
3. riscos por severidade;
4. arquivos do squad que precisam mudar;
5. bloqueios antes de Wave 4 ou Wave 5A.
```

## Wave 4 - `master-kpis-sheet-winning`

Documento atual:

```text
https://docs.google.com/spreadsheets/d/13YLWDeRIXpo7iHaM4N4JCdn3yx17fGiKAJ5bJZvYebo/edit?gid=559901545#gid=559901545
```

Referencia:

```text
https://docs.google.com/spreadsheets/d/1wL98viKIWGUx-0Pwz3F6gh4plshl4VKw/edit?gid=2128190769#gid=2128190769
```

Objetivo: aprimorar o master KPI sheet mantendo todos os KPIs existentes e a identidade Winning Sales.

Escopo preservado do prompt original:

- incorporar apenas a aba de PROSPECCAO da referencia;
- considerar variacao por complexidade de ticket: Low touch, Mid touch, High touch;
- decidir entre aba dinamica, tres abas separadas ou outra solucao;
- se a solucao dinamica for overengineering, usar 3 abas e documentar regra para o Squad excluir as 2 que nao se aplicam;
- manter todos os KPIs atuais;
- localizar qual agent e skill do Squad geram esse entregavel;
- mapear mudancas necessarias no agent/skill;
- definir fluxo ponta a ponta do Squad ate o sheet entregue.

Leitura local ja confirmada:

| Item | Estado atual |
|---|---|
| Template | F2 `master-kpis-sheet-winning` |
| Registry | `templates/TEMPLATE_REGISTRY.md` secao F2 |
| Agent dono provavel | `foundation-agent` |
| Task dona | `tasks/generate-funnel-kpis.md` |
| Skills envolvidas | `skills/find-replace-placeholders.md`, `skills/identidade-visual-dupla.md` |
| Checklist afetado | `checklists/camada-b-01-funil-kpis.md` |
| Dependencia cross | `checklists/camada-c-cross-deliverable.md` e ROI F11 para coerencia de KPIs |

Nao tratar a decisao Low/Mid/High como tomada. Ela ainda precisa de analise comparando o master atual, a aba PROSPECCAO da referencia e o custo de manutencao no squad.

Precondicoes antes de alterar F2:

- executar recorte da Wave 3 para `master-kpis-sheet-winning`;
- definir na Wave 3 a rota e os criterios de Sheets antes de diagnosticar;
- listar abas, celulas, formulas, validacoes, placeholders e dependencias cross-deliverable;
- registrar evidencias durante a leitura da planilha atual e da referencia;
- so depois decidir entre aba dinamica, tres abas ou alternativa simples.

Prompt operacional preservado:

```text
Analise o `master-kpis-sheet-winning` atual e a planilha de referencia.

Objetivo: melhorar o master KPI sheet da Winning Sales mantendo todos os KPIs existentes, identidade Winning Sales e contrato atual do squad.

Use apenas a aba de PROSPECCAO da referencia. Ignore as demais abas, a menos que sejam necessarias para entender formulas ou criterios da aba de PROSPECCAO.

Considere a variacao por complexidade de ticket medio:
- Low touch;
- Mid touch;
- High touch.

Compare tres opcoes:
1. aba dinamica com seletor de complexidade;
2. tres abas separadas, uma por complexidade;
3. outra solucao mais simples.

Para cada opcao, avalie:
- risco de overengineering;
- clareza para consultor;
- risco de erro por cliente;
- impacto em formulas, validacoes e referencias cruzadas;
- impacto no agent, task, skill, checklist e registry.

Se a solucao dinamica for complexa demais, recomende 3 abas e escreva a regra operacional para o squad orientar o consultor a excluir as 2 abas que nao se aplicam e manter apenas a complexidade correta.

Parte critica:
- localizar qual agent e qual skill geram esse entregavel;
- mapear exatamente quais arquivos do squad precisam mudar;
- definir o fluxo ponta a ponta desde onboarding/decisao de complexidade ate o sheet entregue.

Nao invente dados da planilha. Onde nao houver acesso ou confirmacao, marque como "a verificar".
```

## Wave 5A/5B - Redesign de apresentacoes

Objetivo geral: transformar apresentacoes existentes em modelos reutilizaveis profissionais, sem pular a leitura do Design System Winning e sem aplicar acabamento final antes das referencias relevantes do Rafael.

Decisao estrutural: a Wave 5 fica dividida em duas camadas.

- **Wave 5A - Auditoria e base de design**: pode rodar antes da Wave 7. Gera diagnostico por slide, slide-mestre, mapa de variaveis, padroes visuais e criterios Winning.
- **Wave 5B - Aplicacao final e polimento**: so roda depois da Wave 5A e, quando houver referencia relevante do Rafael para aquele artefato, depois da Wave 7 correspondente.

### Wave 5A - Auditoria e base de design

Objetivo: criar base visual reutilizavel e diagnostico por slide sem transformar a analise em redesign final pesado.

Obrigatorio:

- uma apresentacao por vez;
- se a apresentacao tiver mais de 50 slides, dividir a analise em duas etapas: primeira metade + padroes globais, depois segunda metade + consolidacao;
- ler integralmente o Design System Winning antes de decidir visual;
- usar `frontend-design` e `refactoring-ui` apenas como lentes auxiliares de qualidade visual, nunca como substitutas do Design System Winning;
- referenciar regra do Design System em toda decisao visual;
- diagnosticar problemas atuais: visual generico, densidade de texto, pouca imagem/icone/grafico, numeracao hardcoded, fluidez ruim, design sem diferencial;
- responder por slide criterios de hierarquia, grid, densidade, tipografia, cor, visuais, consistencia, numeracao, narrativa e identidade Winning;
- mapear elementos em Universal, Variavel de apresentacao, Variavel de slide ou Hardcoded ruim;
- foco em slide-mestre, mapa de variaveis, layouts-base e criterios para preenchimento sem quebrar layout;
- separar fato confirmado de inferencia.

Nao escopo da Wave 5A:

- aplicar redesign final em massa;
- reescrever logica, narrativa ou variaveis como definitivas;
- promover template final sem Wave 7 quando houver referencia relevante pendente;
- alterar agents, skills, tasks, workflows, templates, checklists ou regras sem aprovacao explicita.

Precondicoes antes de diagnosticar cada apresentacao:

- executar recorte da Wave 3 para a apresentacao escolhida;
- definir na Wave 3 a melhor rota de producao de slides e os criterios de avaliacao;
- usar Design System Winning como fonte de regra, nao como inspiracao vaga;
- usar referencias do Rafael como benchmark se ja estiverem separadas;
- anotar problemas por slide enquanto aparecem, com evidencia, para evitar reconstrucao alucinada no final.

Entregaveis da Wave 5A:

1. decisao de rota tecnica para o artefato;
2. diagnostico por slide;
3. mapa de elementos Universal / Variavel de apresentacao / Variavel de slide / Hardcoded ruim;
4. padroes de slide-mestre e layouts-base recomendados;
5. mudancas necessarias no template e no runtime, apenas como plano;
6. bloqueios antes da Wave 5B;
7. proximo passo objetivo.

### Wave 5B - Aplicacao final e polimento

Objetivo: aplicar a base aprovada da Wave 5A no template final, ja incorporando aprendizados da Wave 7 quando houver referencia relevante.

Precondicoes:

- Wave 5A concluida para a apresentacao;
- Wave 7 analisada para referencias relacionadas ao mesmo artefato, quando existirem;
- decisao humana sobre incorporar ou descartar cada aprendizado da Wave 7;
- aprovacao explicita antes de alterar template master, agents, skills, tasks, workflows, checklists ou regras.

Entregaveis da Wave 5B:

1. template final ajustado;
2. evidencia visual por slide ou por chunks;
3. mapa final de variaveis e limites de texto;
4. arquivos do squad alterados;
5. bloqueios resolvidos ou mantidos;
6. entrada para Wave 6 Sim/Nao.

Apresentacoes afetadas a considerar, conforme registry/QA:

- F1 `master-funnel-diagram-winning`
- F5 Slides `master-prospecting-training-winning`
- F7 `master-dba-template-winning`
- F8 `master-dbs-template-winning`
- F9 `master-proposal-deck-winning`
- F10 `master-battle-cards-winning`
- F12 Slides `master-social-proof-slides-winning`

Prompt operacional da Wave 5A:

```text
Analise uma apresentacao do Squad Playbook Comercial por vez para criar a base de design reutilizavel da Wave 5A.

Antes de avaliar o visual, leia integralmente:
D:\1AWinningSales-Projetos\squadfactory\Design System

Use `frontend-design` e `refactoring-ui` apenas como lentes auxiliares de qualidade visual. A fonte de verdade visual continua sendo o Design System Winning.

Para cada decisao visual, cite qual regra do Design System sustenta a recomendacao. Nao invente estetica fora da marca.

Diagnostique problemas atuais:
- visual generico;
- densidade de texto;
- pouca imagem, icone ou grafico;
- numeracao hardcoded;
- fluidez ruim para apresentacao consultiva;
- design sem diferencial Winning Sales.

Para cada slide, responda:
- hierarquia;
- grid;
- densidade;
- tipografia;
- cor;
- visuais;
- consistencia;
- numeracao;
- narrativa;
- identidade Winning.

Mapeie cada elemento como:
- Universal;
- Variavel de apresentacao;
- Variavel de slide;
- Hardcoded ruim.

Se a apresentacao tiver mais de 50 slides, divida a analise em duas etapas: primeira metade + padroes globais; segunda metade + consolidacao.

O output esperado nao e implementar a logica nem aplicar redesign final. E propor:
1. rota tecnica;
2. diagnostico por slide;
3. slide-mestre e layouts-base;
4. mapa de variaveis;
5. mudancas necessarias no template e no runtime, apenas como plano;
6. criterios para agent/skill preencher sem quebrar layout;
7. bloqueios antes da Wave 5B;
8. proximo passo objetivo.
```

## Wave 6 - QA gate tecnico Sim/Nao

O protocolo detalhado de QA vive em:

- [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/04-Feedback/2026-05-14-QA-Templates|QA Templates - 2026-05-14]]
- `docs/WAVE-6-QA-GATE.md` no repo operacional do squad.

Decisao revisada em 2026-05-18: a Wave 6 nao deve conter pre-trabalho de metodo ou criterios. Isso pertence a Wave 3. A Wave 6 e o gate final de qualidade por artefato depois de uma mudanca proposta ou aplicada.

Regra central: cada analise precisa terminar com veredito obrigatorio **Sim** ou **Nao**, sem "depende".

Entradas obrigatorias:

- resultado da Wave 3 para o artefato: metodo, criterios, contrato e riscos;
- mudancas planejadas ou aplicadas no template;
- arquivos afetados: registry, agent, task, skill, checklist e template;
- evidencias de leitura do artefato real ou export verificavel;
- capacidades MCP/connector/fallback confirmadas.

Processo:

1. Confirmar que a Wave 3 foi executada para o artefato.
2. Reabrir o artefato real ou export verificavel.
3. Validar contra os criterios definidos na Wave 3.
4. Registrar achados enquanto le, com local, evidencia, risco, severidade e correcao provavel.
5. Validar arquivos do squad afetados: registry, agent, task, skill e checklist.
6. Emitir veredito final Sim/Nao.

Escopos obrigatorios:

- Slides: por apresentacao, por slide, com chunking de 30 slides;
- Sheets: por planilha, aba e celula, cobrindo formulas, validacoes, logica condicional e referencias cruzadas;
- Docs: por documento, secao e variavel, cobrindo tabela, bullet, paginacao, TOC e formatacao.

O veredito **Sim** so e permitido quando:

- variaveis tem dono, origem e limite;
- o artefato aguenta preenchimento real sem quebrar layout/logica;
- MCP/connector/fallback cobre as operacoes criticas;
- nao ha instrucao operacional visivel no entregavel final;
- os arquivos do squad afetados estao atualizados ou com mudancas explicitamente mapeadas.

O veredito **Nao** e obrigatorio quando:

- existe placeholder sem dono;
- texto variavel pode estourar layout;
- formula/validacao/referencia cruzada pode quebrar;
- a rota tecnica depende de ferramenta ainda nao confirmada;
- o diagnostico depende de acesso nao disponivel;
- a correcao exigida nao esta localizada.

Prompt operacional:

```text
Valide um artefato do Squad Playbook Comercial por vez como gate final.

Antes de abrir o artefato, confirme que a Wave 3 definiu:
- rota de producao;
- criterios de avaliacao;
- contrato de variaveis;
- riscos e fallback.

Durante a leitura, registre cada achado no momento em que aparecer, com local, evidencia, risco, severidade, correcao provavel e arquivo afetado.

Objetivo: decidir se subagents + skills + MCP/connector/fallback conseguem preencher e entregar este artefato sem:
- substituir texto fixo indevidamente;
- gerar textao que estoura layout;
- quebrar formulas, validacoes, logica condicional ou referencias cruzadas;
- deixar placeholders remanescentes;
- apagar estrutura fixa que deveria continuar no template;
- produzir artefato feio, generico ou dificil de editar.

Ao final, responda obrigatoriamente:
1. metodo e criterios da Wave 3 usados;
2. achados com evidencia;
3. riscos por severidade;
4. mudancas exigidas no template;
5. mudancas exigidas em agent/task/skill/checklist/registry;
6. capacidades MCP/connector necessarias;
7. veredito final: Sim ou Nao.

Nao responda "depende". Se houver dependencia nao resolvida, o veredito e Nao e a dependencia vira correcao exigida.
```

## Wave 7 - Referencias do Rafael

Papel correto no sequenciamento: Wave 7 e transversal. Ela nao precisa esperar todas as waves anteriores, mas depende de Thiago separar os arquivos ou links. Quando uma referencia estiver disponivel, ela deve alimentar a wave ativa correspondente.

Tarefa registrada:

1. Thiago separar todas as referencias enviadas pelo Rafael.
2. Criar prompt para IA analisar cada referencia.
3. A IA deve mostrar o que a referencia criou, identificar o que pode ser reaproveitado e o que esta melhor na referencia para replicar no modelo.
4. Se a referencia for apresentacao explicativa, e nao entregavel de cliente, isso deve ficar explicito no prompt.

Roteamento recomendado:

| Tipo de referencia | Entra em |
|---|---|
| KPI, prospeccao ou planilha de funil | Wave 4 e Wave 6 Sheets |
| DBA, DBS, proposta ou treinamento em slides | Wave 5A se for benchmark de analise/base; Wave 5B se for incorporacao final; Wave 6 Slides |
| Documento explicativo interno | Wave 6 Docs ou benchmark narrativo, sem forcar formato de entregavel |
| Calculadora ROI | Wave 4 se afetar KPIs, Wave 6 Sheets e F11 |
| Benchmark visual geral | Wave 5A para diagnostico e padroes; Wave 5B para incorporacao final, com Design System Winning como regra final |

Prompt operacional preservado:

```text
Analise uma referencia enviada pelo Rafael por vez.

Antes de comparar com os modelos do squad, classifique a referencia:
- entregavel de cliente;
- apresentacao explicativa interna;
- benchmark visual;
- benchmark de estrutura;
- benchmark de conteudo;
- outro tipo.

Mostre:
1. o que essa referencia criou;
2. qual problema ela resolve;
3. que parte pode ser reaproveitada no modelo do squad;
4. o que esta melhor na referencia do que no modelo atual;
5. o que nao deve ser copiado;
6. quais templates/agents/skills/checklists seriam afetados se incorporarmos o aprendizado.

Se a referencia for apresentacao explicativa, e nao entregavel de cliente, deixe isso explicito e nao force o formato dela no template final.

Nao misture DBA, DBS, ROI e apresentacoes diferentes no mesmo prompt. Uma referencia por vez.
```

## Validacoes locais conhecidas

Comandos citados pelo repo:

```powershell
node scripts\validate-template-registry.js
node scripts\validate-template-registry.js --require-p0
node scripts\validate-template-registry.js --strict-drive-ids
node scripts\validate-platform-compatibility.js
```

Resultado registrado no QA de 2026-05-14:

- `validate-template-registry.js --require-p0`: PASS.
- `validate-template-registry.js --strict-drive-ids`: PASS.
- `validate-platform-compatibility.js`: PASS.

## Pontos de atencao

- A proxima alteracao no `master-kpis-sheet-winning` nao e apenas visual: ela pode alterar registry, task, agent, skill, checklist e validacao cross-deliverable.
- Antes de alterar F2, executar Wave 3 para definir metodo, criterios e contrato de Sheets.
- Antes de executar Wave 5A em apresentacoes, executar Wave 3 para definir metodo, criterios e contrato de Slides.
- A Wave 6 agora e apenas QA gate final Sim/Nao; metodo e criterios foram movidos para Wave 3.
- A pesquisa de MCP nao foi executada nesta atualizacao. Tudo que depende de fonte atualizada deve ficar como `a pesquisar` e passa para Wave 2.
- A auditoria do Design System foi apenas localizada, nao concluida.
- A Wave 1 verificou referencias fora do runtime e deixou um mapa historico em [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/02-Process/Runtime-Squad-Historico/REFERENCIAS-EXTERNAS|Referencias Externas]]; esse mapa precisa virar `docs/REFERENCIAS-E-INSUMOS.md` no repo operacional.
- Para o recorte F1 `master-funnel-diagram-winning`, Thiago ja enviou referencias e elas foram registradas em `02-Process/Artefatos/F1-master-funnel-diagram-winning/00-referencias-e-benchmark.md`; REF-01, REF-02, REF-03 e REF-04 ja foram analisadas. Para os demais artefatos, referencias do Rafael ainda dependem de Thiago separar os arquivos ou links.
- Nao editar wrappers `.codex` ou `.claude` como fonte de estrategia; atualizar primeiro os canonicos.

## Perguntas para Thiago

- Onde estao todas as referencias do Rafael: Drive, WhatsApp, arquivos locais ou links soltos?
- Qual artefato deve ser o primeiro recorte da Wave 3: F2 KPI Sheet, F7 DBA, F8 DBS, F9 proposta ou outro?
- Depois da Wave 1, a prioridade pratica e Wave 2 MCP/Claude Code, Wave 4 KPI Sheet ou Wave 5A auditoria/base de apresentacoes?
- O sheet de referencia de KPI pode ser aberto/editado pela conta que vai executar o squad?
