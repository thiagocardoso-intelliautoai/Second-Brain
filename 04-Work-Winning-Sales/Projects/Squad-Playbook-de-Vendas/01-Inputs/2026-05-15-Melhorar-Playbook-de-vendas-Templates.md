---
source: "C:\\Users\\thiag\\Downloads\\Melhorar Playbook de vendas Templates.txt"
source_last_write: 2026-05-15 18:00:55
captured_at: 2026-05-16
updated_at: 2026-05-17
status: raw-input-recovered
recovered_from: "briefing de Thiago em 2026-05-17"
---

# Melhorar Playbook de Vendas - Templates

## Contexto

Input bruto capturado da pasta Downloads durante a Wave 2.

Correcao de 2026-05-17:

- a captura inicial estava incompleta e com encoding ruim;
- este arquivo agora preserva tambem a versao recuperada do prompt original passada por Thiago;
- isto nao marca nenhuma tarefa como concluida;
- tudo que depende de pesquisa externa atualizada fica como `a pesquisar`;
- tudo que depende de insumo do Rafael fica como `a separar`.

Regra:

- manter o texto original preservado;
- usar como insumo para proxima etapa no runtime novo `07-Runtime-Squad/`;
- nao tratar isto como decisao final de arquitetura;
- nao inventar agent, skill, blocker, prazo, dono ou decisao.

## Leitura operacional atualizada

O prompt original nao era apenas "melhorar templates". Ele continha cinco frentes que precisam orientar o Project OS.

Revisao de 2026-05-17: antes de rodar essas frentes, a nova Wave 1 passa a ser a migracao completa do Squad para `07-Runtime-Squad/` dentro deste Active Project. Isso evita que o Project OS fique dependendo de uma extracao "seletiva" ambigua ou de dois runtimes vivos.

| Frente | Wave | Estado |
|---|---|---|
| Migracao completa do Squad para o Active Project | Wave 1 | Migrada em 2026-05-17 |
| MCP / Claude Code / Google Workspace | Wave 2 | A pesquisar, com auditoria local obrigatoria antes |
| Metodo, criterios e contratos dos entregaveis | Wave 3 | A executar antes de Wave 4/5 |
| `master-kpis-sheet-winning` com PROSPECCAO e Low/Mid/High touch | Wave 4 | A analisar e decidir |
| Redesign de apresentacoes | Wave 5 | A analisar uma apresentacao por vez |
| QA gate Sim/Nao de templates alterados | Wave 6 | Protocolo documentado, aplicacao pendente |
| Referencias do Rafael | Wave 7 | A separar e classificar |

## Prompt original recuperado

### Tarefa 1 - MCP / Claude Code / Google Workspace

Documentar uma tarefa de pesquisa para descobrir, com fontes atualizadas de 2025 ou mais recentes, qual o melhor MCP server para integrar Claude Code com:

- Google Sheets;
- Google Drive;
- Google Docs;
- Google Slides como prioridade maxima.

Criterios:

- cobertura real de tools/operacoes;
- profundidade em Slides, incluindo criacao/edicao granular com shapes, text boxes, layouts, formatacao e `batch_update_presentation`;
- maturidade: release/commit recente, stars, issues abertas;
- OAuth 2.x, multi-user se possivel;
- compatibilidade real com Claude Code via `claude mcp add`.

A tarefa tambem exige auditoria local obrigatoria antes de buscar skills externas:

```text
D:\1AWinningSales-Projetos\squadfactory\Design System
```

Essa auditoria deve levantar:

- skills existentes no Design System;
- brand guidelines;
- templates de Slides/Docs/Sheets;
- componentes/tokens de design;
- o que o Design System ja cobre;
- gaps reais.

Separar skills em:

- skills de operacao do MCP para Sheets, Drive, Docs e Slides;
- skills de design para Slides, incluindo Impeccable, Layout skill, Claude Design, mcpmarket.com e skills ja instaladas como `anthropic-skills:ui-principles`, `anthropic-skills:pptx`, `anthropic-skills:winning-sales-brand`, `design:design-critique`, `design:design-system`.

Registrar plano de instalacao:

- comando exato do MCP;
- skills a instalar;
- prerequisitos;
- teste rapido de validacao.

Status: `a pesquisar`, agora como Wave 2. Nao executar pesquisa web dentro deste input.

### Tarefa 4 - Aprimorar `master-kpis-sheet-winning`

Documento atual:

```text
https://docs.google.com/spreadsheets/d/13YLWDeRIXpo7iHaM4N4JCdn3yx17fGiKAJ5bJZvYebo/edit?gid=559901545#gid=559901545
```

Referencia:

```text
https://docs.google.com/spreadsheets/d/1wL98viKIWGUx-0Pwz3F6gh4plshl4VKw/edit?gid=2128190769#gid=2128190769
```

Objetivo:

Aprimorar o master KPI sheet mantendo todos os KPIs existentes e a identidade Winning Sales.

Escopo:

- incorporar apenas a aba de PROSPECCAO da referencia;
- considerar variacao por complexidade de ticket: Low touch, Mid touch, High touch;
- decidir entre aba dinamica, tres abas separadas ou outra solucao;
- se a solucao dinamica for overengineering, usar 3 abas e documentar regra para o Squad excluir as 2 que nao se aplicam;
- manter todos os KPIs existentes;
- preservar identidade Winning Sales.

Parte critica:

- localizar qual agent + skill do Squad gera esse entregavel;
- mapear mudancas necessarias nesse agent/skill;
- definir fluxo ponta a ponta do Squad ate o sheet entregue.

Leitura local ja confirmada em 2026-05-17:

- template: F2 `master-kpis-sheet-winning`;
- registry: `templates/TEMPLATE_REGISTRY.md`, secao F2;
- agent dono provavel: `foundation-agent`;
- task dona: `tasks/generate-funnel-kpis.md`;
- skills envolvidas: `skills/find-replace-placeholders.md` e `skills/identidade-visual-dupla.md`;
- checklist afetado: `checklists/camada-b-01-funil-kpis.md`;
- dependencia cross: `checklists/camada-c-cross-deliverable.md` e ROI F11.

Status: `a analisar`. A decisao Low/Mid/High ainda nao foi tomada.

### Tarefa 6 - Analises tecnicas de templates

Criar prompts/processos para validar, um artefato por vez, se subagents + skills + MCP conseguem preencher variaveis sem:

- substituir texto fixo indevidamente;
- gerar textao que estoura layout;
- quebrar formulas, validacoes, logica condicional ou referencias cruzadas.

Separar em tres analises:

1. Apresentacoes: por slide, com chunking de 30 slides.
2. Sheets: por planilha/aba/celula, cobrindo formulas, validacoes e logica.
3. Docs: por documento/secao/variavel, cobrindo tabela, bullet, paginacao, TOC e formatacao.

Cada analise precisa ter veredito obrigatorio:

```text
Sim ou Nao, sem "depende".
```

Status: protocolo documentado em `04-Feedback/2026-05-14-QA-Templates.md`; aplicacao por artefato ainda pendente.

### Tarefa 7 - Melhorar design das apresentacoes

Criar prompt/processo para transformar apresentacoes existentes em modelos reutilizaveis profissionais.

Obrigatorio:

- uma apresentacao por vez;
- ler integralmente o Design System Winning antes de decidir visual;
- referenciar regra do Design System em toda decisao visual;
- diagnosticar problemas atuais: visual generico, densidade de texto, pouca imagem/icone/grafico, numeracao hardcoded, fluidez ruim, design sem diferencial;
- responder por slide criterios de hierarquia, grid, densidade, tipografia, cor, visuais, consistencia, numeracao, narrativa e identidade Winning;
- mapear elementos em Universal, Variavel de apresentacao, Variavel de slide ou Hardcoded ruim;
- foco e slide-mestre + mapa de variaveis, nao implementacao da logica.

Apresentacoes afetadas a considerar:

- F1 `master-funnel-diagram-winning`;
- F5 Slides `master-prospecting-training-winning`;
- F7 `master-dba-template-winning`;
- F8 `master-dbs-template-winning`;
- F9 `master-proposal-deck-winning`;
- F10 `master-battle-cards-winning`;
- F12 Slides `master-social-proof-slides-winning`.

Status: `a analisar`. Nao redesenhar sem ler o Design System e sem escolher uma apresentacao por vez.

### Tarefa 8 - Referencias do Rafael

Registrar tarefa para:

1. Thiago separar todas as referencias enviadas pelo Rafael.
2. Criar prompt para IA analisar cada referencia, mostrar o que criou, identificar o que pode ser reaproveitado e o que esta melhor na referencia para replicar no modelo.
3. Se a referencia for apresentacao explicativa, e nao entregavel de cliente, deixar isso explicito no prompt.

Status: `a separar`. Depende de Thiago indicar onde estao os arquivos ou links.

## Prompts operacionais preservados

### Prompt - MCP / Claude Code / Google Workspace

```text
Pesquise, usando fontes de 2025 ou mais recentes, qual MCP server e a melhor escolha para integrar Claude Code com Google Workspace no contexto do Squad Playbook Comercial da Winning Sales.

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

### Prompt - KPI Sheet

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

### Prompt - QA tecnico de templates

```text
Valide um artefato do Squad Playbook Comercial por vez.

Objetivo: decidir se subagents + skills + MCP conseguem preencher variaveis sem:
- substituir texto fixo indevidamente;
- gerar textao que estoura layout;
- quebrar formulas, validacoes, logica condicional ou referencias cruzadas;
- deixar placeholders remanescentes;
- apagar estrutura fixa que deveria continuar no template.

Separe a analise por tipo:
1. Apresentacoes: por slide, com chunking de 30 slides.
2. Sheets: por planilha, aba e celula.
3. Docs: por documento, secao e variavel.

Ao final, responda obrigatoriamente:
- Veredito: Sim ou Nao.

Nao responda "depende". Se houver dependencia nao resolvida, o veredito e Nao e a dependencia vira correcao exigida.
```

### Prompt - Redesign de apresentacoes

```text
Analise uma apresentacao do Squad Playbook Comercial por vez para transforma-la em modelo reutilizavel profissional.

Antes de avaliar o visual, leia integralmente:
D:\1AWinningSales-Projetos\squadfactory\Design System

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

O output esperado nao e implementar a logica. E propor:
1. slide-mestre;
2. mapa de variaveis;
3. mudancas no template;
4. criterios para agent/skill preencher sem quebrar layout.
```

### Prompt - Referencias do Rafael

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

## Conteudo bruto preservado da captura inicial

O bloco abaixo e a captura antiga da pasta Downloads. Ele foi preservado por proveniencia, apesar do encoding ruim e da numeracao incompleta.

```text
## Tarefa 1:
Migrar para o Claude Codinho
## Tarefa 2:
Aprimorar o ''master-kpis-sheet-winning''
# Prompt:

1. Aprimorar 'master-kpis-sheet-winning' pelo  o do 'https://docs.google.com/spreadsheets/d/1wL98viKIWGUx-0Pwz3F6gh4plshl4VKw/edit?gid=2128190769#gid=2128190769', na winning jÃƒÂ¡ temos um padrÃƒÂ£o desse documento, quero que adapte ao padrÃƒÂ£o porem com o visual da winning que estÃƒÂ¡ em "D:\1AWinningSales-Projetos\squadfactory\Design System" NÃƒÂ£o precisa de todas as abas, apenas o do prospecÃƒÂ§ÃƒÂ£o e dependendo da complexidade do ticket mÃƒÂ©dio vai ter ou low touch ou mid touch ou high touch. Pense em uma forma eficaz de aplicar isso. Hoje tem os KPIs no que vc criou ÃƒÂ© para vc manter isso. SÃƒÂ³ adicionar uma logica eficaz para oq eu jÃƒÂ¡ te falei, nÃƒÂ£o tenho ideia de qual ÃƒÂ© a forma mais eficaz dessa questÃƒÂ£o de dependendo da complexidade do tikcet ÃƒÂ©dio (dentro do docs que te enviei o link tem falando sobre essa variaÃƒÂ§ÃƒÂ£o de complexidade) vai ter um desses 3, se achar que ÃƒÂ© algo complexo ou overengineer deixe as 3 abas e dentro do squad quando tiver nessa etapa de criaÃƒÂ§ÃƒÂ£o deixar uma regra no prompt para que avise ele para excluir as 2 abas que nÃƒÂ£o for a complexidade de acordo e manter sÃƒÂ³ a complexidade de acordo. E isso com certeza nÃƒÂ£o vai mudar sÃƒÂ³ no sheets, como vai mudar o entregÃƒÂ¡vel do sheets vai mudar o sqaud tambÃƒÂ©m, nÃ£o sei qual o agent e qual a skill, sua tarefa ÃƒÂ© localizar qual ÃƒÂ© a que cuida dessa etapa, ver o que vai ser mudado baseado na analise.

2. Melhorar o design de cada apresentaÃ§Ã£o. Adiconar uma skill de apresentaÃ§Ã£o, adicionar mais imagem, deixar mais palatÃƒÂ¡vel, para que ao o consultor apresentar isso ao cliente seja uma apresentaÃ§Ã£o mais palatÃƒÂ¡vel, mais fluida, menos textÃƒÂ£o.

3. Ao enviar o prompt para melhorar a apresentaÃƒÂ§ÃƒÂ£o enviar como input o modelo de DBS que o Rafael jÃƒÂ¡ criou, e da para ele analisar como que ele criou a apresentaÃƒÂ§ÃƒÂ£o de forma que tem informaÃƒÂ§ÃƒÂµes padrÃƒÂ£o sem precisar de tantas variÃƒÂ¡veis


Separar os insumos que ele me deu e pensar como usar em cada prompt, aproveitar o insumo de DBA ou DBS

4. Enviar a calculadora de ROI de referencia
```

## Proxima triagem no runtime novo

- Localizar donos de `master-kpis-sheet-winning`: registry, task, agent e checklist.
- Localizar todos os entregaveis de apresentacao afetados: F1, F5 Slides, F7, F8, F9, F10 e F12 Slides.
- Separar referencias: planilha KPI, Design System, modelo DBS/DBA Rafael e calculadora ROI.
- Definir se as referencias sao bloqueadoras para piloto ou melhoria incremental.
- Auditar Design System antes de buscar skills externas.
- Pesquisar MCP Google Workspace somente quando a Wave 2 for ativada.
- Aplicar QA tecnico com veredito Sim/Nao antes de considerar template pronto.

## Perguntas para Thiago

- Onde estao as referencias do Rafael?
- A referencia de ROI e a F11 atual do squad ou outro arquivo enviado pelo Rafael?
- A proxima prioridade e KPI Sheet, apresentacoes ou infra MCP/Claude Code?
