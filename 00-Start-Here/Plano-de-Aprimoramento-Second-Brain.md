---
source: Codex audit refinement
created_at: 2026-05-16
status: active-plan
related_audit: 00-Start-Here/Auditoria-Valor-Real-2026-05-16.md
related_methodology_audit: 00-Start-Here/Auditoria-Metodologia-AI-Second-Brain-Video-2026-05-16.md
---

# Plano de Aprimoramento - Second Brain

## Premissa

Thiago nao quer executar este plano manualmente. A IA/Codex deve executar as melhorias em waves, usando o vault como fonte principal e perguntando a Thiago apenas quando faltar contexto real que nao pode ser inferido com seguranca.

O papel de Thiago:

- dar contexto em blocos;
- validar decisoes importantes;
- responder perguntas abertas quando o estado real do trabalho nao estiver no vault.

O papel da IA:

- ler o contexto certo;
- identificar lacunas;
- fazer as edicoes;
- criar artefatos uteis;
- evitar placeholders mortos;
- registrar decisoes, duvidas e proximos passos.

## Regra contra placeholders mortos

Nao preencher campos operacionais com vazio permanente.

Se a IA nao souber algo como:

- estado atual;
- bloqueio;
- proxima acao;
- quem decide;
- artefato esperado;
- criterio de pronto;
- decisao que mudou;

ela deve fazer uma pergunta aberta para Thiago antes de editar a wave correspondente.

Formato preferido:

```text
Me da um contexto geral sobre [projeto/area]:
- onde isso esta hoje;
- o que aconteceu desde a ultima nota;
- o que esta travando;
- o que voce quer que exista como entrega;
- quem precisa aprovar ou decidir;
- como voce saberia que ficou pronto.
```

Depois da resposta, a IA deve extrair os campos necessarios. Se ainda faltar algo critico, perguntar somente o minimo.

## Pesquisa antes da execucao

Nao pesquisar agora. Esta lista define o que deve ser pesquisado quando a wave exigir informacao externa ou atual.

### Pesquisa provavelmente necessaria

#### 1. Convencoes do Codex/AGENTS

Quando mexer em instrucoes globais de agentes, validar se o padrao atual do Codex continua sendo `AGENTS.md`, quais escopos ele respeita e se existe alguma diferenca relevante para vaults locais.

Objetivo:

- garantir que o AI Operating System seja lido no inicio;
- evitar depender apenas de memoria do usuario ou prompt manual.

#### 2. Obsidian para dashboards leves

Antes de criar dashboards mais avancados, pesquisar se vale usar:

- Obsidian Bases;
- Dataview;
- Properties/frontmatter;
- Templates;
- Canvas.

Objetivo:

- evitar overengineering;
- escolher um formato que Thiago realmente use;
- nao criar dependencia de plugin sem necessidade.

#### 3. Automacao de LinkedIn e risco de plataforma

Antes de recomendar arquitetura para Social Selling Automation, pesquisar estado atual de:

- politicas/restricoes do LinkedIn;
- risco de bloqueio;
- limites de automacao;
- ferramentas como HeyReach, LinkedInHelper, Apify, Snov, Tavily e similares.

Objetivo:

- nao recomendar automacao fragil ou arriscada;
- diferenciar pesquisa, enriquecimento, engajamento assistido e envio automatizado.

#### 4. CRM e governanca de campos

Antes de transformar a mentoria do Marcelo em templates mais maduros, pesquisar documentacao ou boas praticas dos CRMs que ele realmente usa.

Pesquisar so depois que Thiago ou Marcelo confirmar quais CRMs importam.

Objetivo:

- criar checklist e matriz de campos com aderencia real;
- evitar framework generico demais.

#### 5. Claims publicos para LinkedIn

Antes de fechar posts com afirmacoes fortes sobre mercado, ROI, ferramentas ou tendencias, pesquisar fontes atuais apenas quando a afirmacao depender de dado externo.

Objetivo:

- manter opiniao forte sem virar chute;
- sustentar posts que fazem claims verificaveis.

#### 6. Ferramentas especificas de IA/automacao

Quando uma wave exigir escolha de ferramenta, pesquisar documentacao oficial, precos, limites e integracoes atuais.

Objetivo:

- nao documentar stack desatualizada;
- separar decisao tecnica de preferencia pessoal.

### Pesquisa provavelmente nao necessaria

Nao precisa pesquisar para:

- reorganizar notas internas;
- criar cockpit de projetos com base no contexto de Thiago;
- transformar frameworks existentes em prompts/checklists;
- preservar voz;
- destilar raw imports;
- criar logs, templates e MOCs simples.

Nesses casos, o gargalo e contexto interno, nao informacao externa.

## Principios incorporados da metodologia do video

Esta versao do plano incorpora a auditoria aprovada da metodologia do video:

- [[00-Start-Here/Auditoria-Metodologia-AI-Second-Brain-Video-2026-05-16|Auditoria - Metodologia AI Second Brain do Video]]

Principios que entram no plano:

1. Camada 1: `Strategy OS` para decidir foco, objetivos, revisoes e trade-offs.
2. Camada 2: `Project OS` para executar projetos com inputs, processo, outputs, feedback e skills locais.
3. Skills locais ficam perto do projeto; skills universais ficam em frameworks/processos.
4. Toda automacao precisa preservar ou aumentar qualidade do output.
5. Feedback volta para o sistema e muda proximas decisoes.
6. O vault deve funcionar com Codex, Claude ou outra IA que leia Markdown local.

## Politica de Strategy OS e Project OS

### Strategy OS

O Strategy OS responde:

> O que importa agora e por que?

Ele deve conter:

- objetivos atuais;
- prioridades do trimestre ou ciclo atual;
- regra de atualizacao sem ritual manual;
- decisoes estrategicas;
- trade-offs de foco;
- lista de projetos ativos com status real;
- perguntas que precisam de decisao humana.

Regra:

> A IA pode organizar e desafiar estrategia, mas nao deve inventar destino, ambicao ou prioridade pessoal de Thiago.

### Project OS

O Project OS responde:

> Como este projeto gera output real?

Projetos grandes devem ser estruturados com:

```text
00-Project-Brief.md
01-Inputs/
02-Process/
03-Outputs/
04-Feedback/
05-Skills/
06-Logs/
PROJECT.md
```

Projetos pequenos continuam como arquivo unico com cockpit.

Regra de decisao:

- arquivo unico: projeto curto, baixo volume, pouca recorrencia;
- pasta Project OS: projeto recorrente, muitos inputs, multiplos outputs, feedback, cliente ou automacao relevante;
- pasta de cliente: quando confidencialidade, sessoes e entregaveis por cliente forem importantes;
- pipeline de conteudo: quando o foco for publicar e medir conteudo.

## Politica de skills, comandos e mentores

Criar uma boa skill nao e simples. Uma skill so entra no sistema quando tiver:

- caso de uso claro;
- input definido;
- output esperado;
- criterios de qualidade;
- exemplos;
- limites;
- como testar;
- quando nao usar;
- onde ela vive: global ou local.

### Tipos

#### Skill global

Usada em varios projetos.

Local provavel:

- `07-Frameworks-and-Processes/AI-Skills-and-Mentors/`

Exemplos:

- criar novo projeto;
- sincronizacao estrategica por gatilho natural;
- criar mentor/clone mental;
- revisar output com quality gate;
- transformar nota em framework;
- processar transcricao.

#### Skill local

Usada dentro de um projeto, cliente ou pipeline especifico.

Local provavel:

- `05-Skills/` dentro de uma pasta Project OS;
- ou pasta equivalente dentro de cliente/conteudo.

Exemplos:

- gerar battlecard do Squad Playbook;
- revisar mensagem de social selling;
- gerar timestamp de call de mentoria;
- avaliar post pela voz de Thiago.

#### Mentor ou clone mental

Nao e uma imitacao perfeita de uma pessoa. E uma lente operacional inspirada em:

- principios;
- frameworks;
- criterios de decisao;
- perguntas tipicas;
- anti-padroes;
- modo de avaliar trade-offs.

Uso:

- ajudar a tomar decisoes;
- revisar estrategia;
- criticar projeto;
- orientar execucao;
- criar outras skills.

Regra:

> Mentor/clone mental deve ser tratado como lente de pensamento, nao como autoridade final.

### Skill universal prioritÃ¡ria: Criar Mentor

Contexto atualizado em 2026-05-17:

- Thiago ja apontou o prompt de clones/mentores em `07-Frameworks-and-Processes/AI-Skills-and-Mentors/Processo-para-Criacao-de-Clone.md` e no GitHub `SynkraAI/aiox-core/.claude/skills/clone-mind.md`.
- Portanto, a IA nao deve pedir esse prompt de novo para a Wave 5.

Texto original da regra antes de Thiago fornecer o prompt:

```text
Me envia o prompt que voce tem para gerar clones/mentores. Vou usar isso para criar uma skill universal de Criar Mentor, capaz de gerar mentores locais ou globais com criterio, limites e exemplos.
```

Depois disso, a IA deve:

- analisar o prompt de Thiago;
- sugerir melhorias;
- criar a skill universal `Criar Mentor`;
- definir onde ela sera guardada;
- criar criterios para quando um mentor vira global ou local;
- sugerir mentores/frameworks uteis por projeto;
- pedir aprovacao antes de criar cada mentor importante.

Local inicial recomendado:

- `07-Frameworks-and-Processes/AI-Skills-and-Mentors/Criar-Mentor.md`

Esse local ainda deve ser criado apenas na wave correspondente.

## Waves de execucao

### Wave 0 - Bootstrapping da IA

Objetivo:

Garantir que uma IA saiba ler o AI Operating System antes de mexer no vault.

Status inicial:

- `AGENTS.md` criado na raiz do vault.
- `AGENTS.md` aponta para `AI-READ-ME-FIRST`, `System-Map` e arquivos do `02-AI-Operating-System`.
- Em 2026-05-17, o padrao foi confirmado como `AGENTS.md`; nao depender de `AGENT.md` singular.

Execucao da IA:

- revisar `AGENTS.md` para incluir Strategy OS, Project OS e politica de skills;
- garantir que o hub principal aponte para auditorias e plano;
- nao instalar plugins nem mudar ferramenta.

Entregaveis:

- instrucoes globais claras;
- regra de leitura inicial;
- regra contra invencao de contexto;
- referencia ao plano atual.

Criterio de pronto:

- uma IA que abra o vault entende onde comecar, que papel assumir e quais regras respeitar.

Pesquisa:

- pesquisar convencoes atuais do Codex/`AGENTS.md` apenas se for necessario depender de escopo por subpasta.

### Wave 0.5 - Strategy OS e contexto vivo

Status:

- concluida em 2026-05-16.
- entregavel principal criado em `00-Start-Here/Strategy-OS.md`.

Objetivo:

Criar uma camada leve para objetivos, prioridades, revisoes e decisoes estrategicas.

Antes de executar, perguntar a Thiago:

```text
Me da um contexto geral da sua estrategia agora:
- quais sao seus objetivos principais nos proximos 30-90 dias;
- quais projetos mais importam;
- o que voce quer evitar;
- que tipo de oportunidade voce quer criar;
- quais trade-offs estao vivos na sua cabeca;
- que decisoes voce quer que a IA te ajude a pensar melhor.
```

Execucao da IA:

- criar um arquivo leve de Strategy OS;
- registrar objetivos, prioridades e trade-offs;
- criar regra de atualizacao por gatilhos naturais, sem depender de revisao semanal ou mensal manual;
- conectar Strategy OS aos projetos ativos;
- separar fatos, decisoes e perguntas.

Entregaveis:

- `00-Start-Here/Strategy-OS.md` ou nome equivalente;
- protocolo leve de atualizacao oportunista;
- lista de prioridades com criterios.

Criterio de pronto:

- a IA entende o que importa agora antes de mexer em projetos.

Pesquisa:

- nao necessaria.

### Wave 1 - Classificacao dos projetos e Project OS template

Status:

- plano de execucao montado em 2026-05-16.
- executada em 2026-05-16 depois de intake de contexto com Thiago.
- conversao de projetos ficou para a Wave 2.

Objetivo:

Decidir quais projetos continuam como arquivo unico e quais viram Project OS.

Antes de executar, perguntar a Thiago:

```text
Me da um contexto geral dos projetos ativos:
- quais sao projetos pequenos;
- quais sao projetos grandes ou recorrentes;
- quais tem varios inputs/outputs;
- quais precisam de feedback e log;
- quais merecem skills locais;
- quais estao parados ou podem ser arquivados.
```

Execucao da IA:

- classificar projetos ativos;
- criar o template de Project OS;
- definir criterio para converter arquivo em pasta;
- nao converter projeto grande sem contexto suficiente;
- preservar links existentes.

Entregaveis:

- criterio documentado de projeto pequeno vs Project OS;
- template de Project OS;
- lista de projetos candidatos a conversao.

Criterio de pronto:

- fica claro qual estrutura cada projeto merece e por que.

Pesquisa:

- nao necessaria.

#### Plano de execucao da Wave 1

Intencao:

- transformar a Wave 1 em uma decisao estrutural pequena e segura;
- classificar os projetos ativos com criterio explicito;
- criar um template reutilizavel de Project OS;
- deixar a Wave 2 pronta para executar conversoes, cockpits ou arquivamentos com menos ambiguidade.

Nao fazer nesta wave:

- nao converter projeto em pasta sem contexto suficiente;
- nao criar skills locais ainda;
- nao pesquisar ferramentas externas;
- nao preencher estado atual, bloqueio, aprovador, prazo ou criterio de pronto por chute;
- nao mexer em conteudo de projeto alem do necessario para documentar a classificacao.

Arquivos base para leitura:

- `00-Start-Here/AI-READ-ME-FIRST.md`
- `00-Start-Here/System-Map.md`
- `00-Start-Here/Strategy-OS.md`
- `02-AI-Operating-System/AI-Behavior-and-Communication.md`
- `04-Work-Winning-Sales/Projects/README.md`
- `00-Start-Here/MOC-Work-Winning-Sales.md`
- `04-Work-Winning-Sales/Winning-Sales-Strategic-Context.md`
- `04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas.md`
- `04-Work-Winning-Sales/Projects/Social-Selling-Automation-Samuel.md`
- `04-Work-Winning-Sales/Projects/Central-de-IA-Winning-Sales.md`

Pergunta de intake antes de executar a classificacao:

```text
Me da um contexto geral dos projetos ativos:
- quais sao projetos pequenos;
- quais sao projetos grandes ou recorrentes;
- quais tem varios inputs/outputs;
- quais precisam de feedback e log;
- quais merecem skills locais;
- quais estao parados ou podem ser arquivados.

Se puder, separa por projeto:
- Squad Playbook de Vendas;
- Social Selling Automation - Samuel;
- Central de IA - Winning Sales;
- qualquer outro projeto ativo que ainda nao esteja no vault.
```

Passo 1 - Inventario dos projetos ativos:

- listar todos os arquivos em `04-Work-Winning-Sales/Projects/`;
- registrar para cada projeto: objetivo, fonte, status declarado, proximos passos, decisoes abertas, outputs citados, links relacionados e sinais de recorrencia;
- marcar lacunas reais como `Perguntas para Thiago`, sem criar placeholders operacionais vazios;
- verificar se existe projeto ativo citado no Strategy OS ou no MOC que ainda nao tem arquivo proprio.

Passo 2 - Matriz de classificacao:

Criar uma tabela de classificacao com estes campos:

| Campo | Uso |
|---|---|
| Projeto | Nome do projeto ou frente |
| Evidencia no vault | Trecho, secao ou arquivo que sustenta a leitura |
| Tipo sugerido | Arquivo unico, cockpit, Project OS, arquivar ou transformar em framework |
| Motivo | Por que essa estrutura faz sentido |
| Inputs/outputs | Baixo, medio ou alto volume |
| Recorrencia | Pontual, recorrente ou incerta |
| Feedback/log | Necessario, util ou desnecessario agora |
| Skills locais | Sim, talvez ou nao |
| Contexto faltante | Pergunta especifica para Thiago |
| Proxima acao estrutural | O que fazer na Wave 2 |

Passo 3 - Criterio de decisao:

Usar esta regra inicial:

- `arquivo unico`: projeto curto, pouco recorrente, baixo volume de input/output e sem necessidade clara de log;
- `cockpit`: projeto ativo que precisa de clareza operacional, mas ainda nao justifica pasta completa;
- `Project OS`: projeto recorrente, com muitos inputs/outputs, feedback, entregaveis, cliente interno/externo, automacao relevante ou skills locais provaveis;
- `arquivar`: frente parada, encerrada ou sem acao relevante no ciclo atual;
- `framework`: material que deixou de ser projeto vivo e virou metodo reutilizavel.

Passo 4 - Hipoteses iniciais, sem converter ainda:

Estas hipoteses servem apenas para orientar a conversa de intake:

| Projeto | Hipotese inicial | Motivo visivel no vault | Decisao pendente |
|---|---|---|---|
| Squad Playbook de Vendas | forte candidato a Project OS | tem multiplos entregaveis, fases, validacao humana, possiveis subagentes e skills | confirmar estado atual, aprovador, piloto e entregavel prioritario |
| Social Selling Automation - Samuel | candidato a Project OS ou cockpit tecnico | tem fluxo com varias ferramentas, risco tecnico, decisoes abertas e necessidade de pesquisa futura | confirmar se esta ativo, escopo real, nivel de automacao permitido e proximo input do Samuel |
| Central de IA - Winning Sales | candidato a cockpit ou Project OS | parece produto/plataforma com taxonomia, feedbacks e risco de comportamento | confirmar se e projeto ativo de produto, backlog vivo ou apenas conceito estrategico |

Passo 5 - Template de Project OS:

Criar um template reutilizavel, preferencialmente em:

- `07-Frameworks-and-Processes/Second-Brain-System/Project-OS-Template.md`

Estrutura minima do template:

```text
# Nome do Projeto

## 00 - Project Brief
- objetivo;
- por que importa agora;
- owner/decisor, se confirmado;
- criterio de pronto;
- restricoes;
- links principais.

## 01 - Inputs
- fontes;
- transcricoes;
- anexos;
- decisoes recebidas;
- contexto bruto preservado.

## 02 - Process
- fluxo de trabalho;
- etapas;
- criterios de qualidade;
- pontos de validacao humana;
- automacoes ou agentes envolvidos.

## 03 - Outputs
- entregaveis finais;
- drafts;
- versoes aprovadas;
- exemplos reutilizaveis.

## 04 - Feedback
- feedback recebido;
- metricas;
- problemas encontrados;
- aprendizados aplicaveis.

## 05 - Skills
- skills locais candidatas;
- quando usar;
- input/output esperado;
- criterio de qualidade.

## 06 - Logs
- decisoes;
- mudancas de escopo;
- sessoes relevantes;
- proximas acoes.

## PROJECT.md
- cockpit operacional do projeto;
- estado atual;
- proxima acao;
- decisoes abertas;
- links para inputs, outputs, feedback e logs.
```

Passo 6 - Entregaveis da Wave 1:

- atualizar `04-Work-Winning-Sales/Projects/README.md` com a regra de classificacao;
- criar `07-Frameworks-and-Processes/Second-Brain-System/Project-OS-Template.md`;
- criar ou atualizar uma secao de classificacao no plano atual, com a lista de projetos e decisao recomendada;
- deixar uma lista curta de perguntas para Thiago, somente onde a classificacao depender de contexto real;
- preparar a Wave 2 com uma ordem sugerida de execucao.

Passo 7 - Criterio de pronto especifico:

A Wave 1 estara pronta quando:

- todos os projetos ativos conhecidos estiverem classificados;
- cada classificacao tiver evidencia ou pergunta pendente;
- o template de Project OS existir e puder ser reutilizado;
- os projetos grandes nao tiverem sido convertidos sem contexto;
- a Wave 2 tiver uma lista clara do que atualizar, converter, manter como cockpit ou arquivar.

#### Resultado da execucao da Wave 1

Executado em 2026-05-16.

Arquivos criados:

- `07-Frameworks-and-Processes/Second-Brain-System/Project-OS-Template.md`
- `99-Archive/Second-Brain-Improvement/Classificacao-Wave-1-2026-05-16.md`

Arquivos atualizados:

- `04-Work-Winning-Sales/Projects/README.md`
- `04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas.md`
- `04-Work-Winning-Sales/Projects/Social-Selling-Automation-Samuel.md`
- `04-Work-Winning-Sales/Projects/Central-de-IA-Winning-Sales.md`
- `00-Start-Here/Strategy-OS.md`
- `00-Start-Here/MOC-Work-Winning-Sales.md`
- `00-Start-Here/MOC-Frameworks.md`
- `06-Personal-Brand/Linkedin/README.md`
- `07-Frameworks-and-Processes/README.md`

Decisoes estruturais:

| Projeto/frente | Decisao Wave 1 | Proxima acao |
|---|---|---|
| Squad Playbook de Vendas | virar Project OS na Wave 2 | conectar cockpit ao repo externo `D:\1AWinningSales-Projetos\squadfactory\squads\playbook-comercial-squad` e capturar input de melhoria vindo de Downloads |
| Social Selling Automation - Samuel | estacionar como backlog/parked | nao pesquisar ferramentas agora; decidir depois se arquiva ou retoma |
| Central de IA - Winning Sales | registrar como entregue | confirmar se existe backlog vivo; se nao, mover para referencia/arquivo |
| Thiago Marketing OS / LinkedIn | nao virar app central do fluxo | tratar como insumo para uma wave de LinkedIn simples, importando apenas o que ajuda publicar, agendar, escrever ou visualizar posts |

Resposta a decisao sobre o Playbook:

- nao mover o repo inteiro do squad para dentro do Second Brain;
- manter o repo externo como fonte canonica de execucao;
- usar o Second Brain como cockpit, memoria decisoria, logs, inputs importantes e links para o repo real.

### Wave 2 - Projetos ativos como cockpit ou Project OS

Status:

- executada em 2026-05-16.
- Playbook convertido em Project OS.
- Social Selling mantido como parked/backlog.
- Central de IA registrada como entregue/referencia.

Arquivos iniciais:

- `04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas.md`
- `04-Work-Winning-Sales/Projects/Social-Selling-Automation-Samuel.md`
- `04-Work-Winning-Sales/Projects/Central-de-IA-Winning-Sales.md`

Antes de executar, perguntar a Thiago:

```text
Me da um contexto geral dos 3 projetos ativos:
- onde cada um esta hoje;
- o que aconteceu desde a ultima nota;
- o que esta travado;
- qual entrega precisa existir em cada projeto;
- quem decide ou aprova;
- como voce sabe que cada um ficou pronto.
```

Execucao da IA:

- atualizar cada projeto com cockpit;
- converter para Project OS apenas quando fizer sentido;
- separar `Inputs`, `Process`, `Outputs`, `Feedback` e `Logs` nos projetos grandes;
- registrar decisoes abertas;
- criar `Perguntas para Thiago` apenas quando houver duvida real;
- evitar placeholders vazios.

Entregaveis:

- projetos ativos com proxima acao real;
- cockpits ou Project OS criados;
- feedback/log preparado.

Criterio de pronto:

- ao abrir cada projeto, Thiago e uma IA sabem exatamente o que fazer em seguida.

Pesquisa:

- nao pesquisar para estruturar;
- pesquisar apenas quando uma decisao tecnica depender de informacao atual.

#### Resultado da execucao da Wave 2

Arquivos criados:

- `04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/PROJECT.md`
- `04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/00-Project-Brief.md`
- `04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/01-Inputs/2026-05-15-Melhorar-Playbook-de-vendas-Templates.md`
- `04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/02-Process/Mapa-do-Squad-e-Repo-Externo.md`
- `04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/03-Outputs/Links-e-Artefatos-Externos.md`
- `04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/04-Feedback/2026-05-14-QA-Templates.md`
- `04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/05-Skills/Skills-Locais-Candidatas.md`
- `04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/06-Logs/2026-05-16-Wave-2-Conversao-Project-OS.md`

Arquivos atualizados:

- `04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas.md`
- `04-Work-Winning-Sales/Projects/README.md`
- `04-Work-Winning-Sales/Projects/Social-Selling-Automation-Samuel.md`
- `04-Work-Winning-Sales/Projects/Central-de-IA-Winning-Sales.md`
- `00-Start-Here/MOC-Work-Winning-Sales.md`
- `00-Start-Here/Strategy-OS.md`
- `00-Start-Here/Obsidian-Home.md`
- `00-Start-Here/MOC-Frameworks.md`

Decisoes:

| Frente | Decisao Wave 2 | Proxima acao |
|---|---|---|
| Squad Playbook de Vendas | virou Project OS | triagem do input de melhoria dos templates e decisao com Rafael sobre proxima entrega |
| Social Selling Automation - Samuel | manter parked/backlog | retomar somente se Samuel/Rafael recolocarem prioridade e trouxerem contexto real |
| Central de IA - Winning Sales | manter como entregue/referencia | criar backlog novo somente se surgir demanda viva |

Criterio de pronto atingido:

- Playbook tem cockpit, brief, input bruto, mapa de processo, links externos, feedback, skills candidatas e log.
- O arquivo antigo do Playbook virou ponte para preservar links.
- Active Projects separa ativo, parked e entregue.
- Nenhuma pesquisa externa foi feita nesta wave.

### Wave 3 - Marcelo como trilha de mentoria executavel

Status:

- executada em 2026-05-17.
- foco corrigido: mentoria e proxima reuniao, nao consultoria nem pacote operacional para Marcelo.

Arquivos base:

- `05-Clients-and-Mentoring/Mentoria-IA/Marcelo/README.md`
- `05-Clients-and-Mentoring/Mentoria-IA/Marcelo/00-Contexto-do-Cliente.md`
- `05-Clients-and-Mentoring/Mentoria-IA/Marcelo/02-Diagnostico-Estruturado.md`
- `05-Clients-and-Mentoring/Mentoria-IA/Marcelo/05-Decisoes-e-Proximos-Passos.md`

Decisao de correcao:

- manter `02-Diagnostico-Estruturado.md` como contexto historico da Sessao 0;
- remover os antigos arquivos de oportunidades e plano de acao, porque puxavam para consultoria;
- organizar a mentoria em 4 fases e 7 sessoes;
- criar um roteiro pratico para a proxima reuniao;
- criar a apresentacao visual da proxima reuniao.

Arquivos criados:

- `05-Clients-and-Mentoring/Mentoria-IA/Marcelo/03-Plano-da-Mentoria.md`
- `05-Clients-and-Mentoring/Mentoria-IA/Marcelo/04-Roteiro-Proxima-Reuniao.md`
- `05-Clients-and-Mentoring/Mentoria-IA/Marcelo/Apresentacao-Proxima-Reuniao.html`

Arquivos removidos:

- `05-Clients-and-Mentoring/Mentoria-IA/Marcelo/03-Oportunidades-de-IA-e-Automacao.md`
- `05-Clients-and-Mentoring/Mentoria-IA/Marcelo/04-Plano-de-Acao.md`

Execucao da IA:

- atualizar links da pasta Marcelo e do MOC de clientes;
- deixar claro que o diagnostico e contexto, nao promessa de entrega;
- registrar o que sera apresentado na proxima reuniao;
- criar uma apresentacao visual curta para Thiago apresentar a trilha;
- nao pesquisar boas praticas de CRM nesta wave.

Entregaveis:

- plano da mentoria organizado;
- roteiro da proxima reuniao;
- apresentacao visual da proxima reuniao;
- links corrigidos para nao apontar para arquivos excluidos.

Criterio de pronto:

- Thiago abre a pasta do Marcelo e sabe exatamente o que apresentar na proxima reuniao;
- nao sobra link para arquivos removidos;
- o plano nao promete CRM pronto, auditoria, copiloto de diagnostico ou automacao completa;
- LinkedIn e ofertas futuras aparecem apenas como fechamento ou contexto secundario.

Pesquisa:

- nao necessaria nesta wave.

### Wave 4 - Frameworks virando ferramentas

Status:

- executada em 2026-05-17 como correcao estrategica;
- a toolificacao completa foi adiada ate existir uso recorrente real.

Arquivos prioritarios:

- `07-Frameworks-and-Processes/04-Work-Winning-Sales/Technology-Mapping-and-Process-Diagnosis.md`
- `07-Frameworks-and-Processes/04-Work-Winning-Sales/Assistida-Workflow-Agent.md`
- `07-Frameworks-and-Processes/04-Work-Winning-Sales/AI-Automation-Project-Documentation.md`

Pergunta antes de executar:

```text
Quando voce usa esses frameworks na pratica, qual tipo de saida voce mais quer gerar: diagnostico para cliente, plano tecnico, post, proposta, aula, ou documento interno?
```

Nota de execucao:

- Thiago respondeu que essa pergunta estava vaga demais;
- nao repetir essa pergunta como se ela resolvesse a decisao;
- usar a pergunta substituta registrada no resultado da Wave 4 e em `07-Frameworks-and-Processes/AI-Skills-and-Mentors/Frameworks-to-Skills-Backlog.md`.

Escopo original da Wave 4, substituido pela decisao abaixo:

- adicionar inputs;
- adicionar checklist;
- adicionar prompt/template;
- adicionar output esperado;
- adicionar criterio de qualidade;
- adicionar quality gate;
- criar exemplo preenchido usando Marcelo ou Winning Sales quando fizer sentido.

Entregaveis originais esperados:

- frameworks aplicaveis por IA e humano;
- menos tese solta;
- mais ferramenta operacional.

Criterio de pronto original:

- uma IA consegue aplicar o framework sem pedir explicacao do zero.

Pesquisa:

- normalmente nao necessaria;
- pesquisar apenas se o exemplo ou ferramenta depender de dado externo.

#### Resultado da execucao da Wave 4

Executada em 2026-05-17 como correcao estrategica, nao como toolificacao completa.

Decisao:

- a pergunta original sobre output estava vaga demais;
- sem uso recorrente claro, transformar todos os frameworks em templates, prompts ou exemplos preenchidos criaria manutencao falsa;
- os frameworks devem ficar como lentes, checklists leves e insumos para skills futuras;
- exemplos com Marcelo ou Winning Sales so devem ser criados quando nascerem de uso real, nao como preenchimento especulativo.

Arquivos criados:

- `07-Frameworks-and-Processes/AI-Skills-and-Mentors/Frameworks-to-Skills-Backlog.md`

Arquivos atualizados:

- `07-Frameworks-and-Processes/README.md`
- `00-Start-Here/MOC-Frameworks.md`
- `07-Frameworks-and-Processes/04-Work-Winning-Sales/Technology-Mapping-and-Process-Diagnosis.md`
- `07-Frameworks-and-Processes/04-Work-Winning-Sales/Assistida-Workflow-Agent.md`
- `07-Frameworks-and-Processes/04-Work-Winning-Sales/AI-Automation-Project-Documentation.md`

Regra operacional definida:

- um framework so vira prompt, template ou skill quando tiver caso de uso concreto, input recorrente, output esperado, criterio de qualidade e 2 ou 3 usos reais, ou uma demanda viva que claramente vai se repetir;
- criar skill local primeiro quando o uso estiver preso a um projeto ou cliente;
- promover para skill global apenas quando o metodo se provar transversal.

Criterio de pronto atingido:

- uma IA futura sabe que nao deve perguntar genericamente "qual output voce quer gerar";
- a melhor pergunta passa a ser: qual uso real se repetiu e quais outputs concretos ja existem;
- a Wave 5 agora tem um backlog inicial de skills candidatas sem criar uma biblioteca prematura.

### Wave 5 - Skills, comandos e mentores

Status:

- executada em 2026-05-17.
- plano detalhado e resultado em [[00-Start-Here/Plano-de-Acao-Wave-5-Skills-Comandos-e-Mentores|Plano de Acao - Wave 5 - Skills, Comandos e Mentores]].

Objetivo:

Criar a camada operacional de skills/comandos sem cair em prompt generico.

Plano de acao detalhado:

- [[00-Start-Here/Plano-de-Acao-Wave-5-Skills-Comandos-e-Mentores|Plano de Acao - Wave 5 - Skills, Comandos e Mentores]]

Nota:

- Thiago ja apontou o prompt de clone/mentor em [[07-Frameworks-and-Processes/AI-Skills-and-Mentors/Processo-para-Criacao-de-Clone|Processo para Criacao de Clone]] e no GitHub `SynkraAI/aiox-core/.claude/skills/clone-mind.md`.
- A proxima pergunta da Wave 5 nao deve pedir o prompt de novo. Deve perguntar quais 1 ou 2 frentes mais precisam de skill ou mentor agora.

Antes de executar, a IA deve pedir:

```text
Quais 1 ou 2 frentes mais precisam de uma skill ou mentor agora: Strategy OS, Winning Sales/Playbook, Marcelo, LinkedIn, automacao ou outra?

Para a primeira frente, voce quer uma skill operacional, um mentor/lente, ou os dois?
```

Execucao da IA:

- propor primeiro uma lista de skills candidatas;
- separar skills convencionais de mentores/clones mentais;
- avaliar quais sao globais e quais sao locais;
- criar a skill universal `Criar Mentor` com base no prompt de Thiago;
- sugerir mentores/frameworks uteis por projeto;
- criar no maximo poucas skills iniciais, testaveis;
- documentar teste, input, output, limites e quality gate de cada skill;
- nao criar biblioteca gigante antes de uso real.

Exemplos de skills candidatas:

- Criar Mentor;
- Novo Projeto Ativo;
- Sincronizacao Estrategica por Gatilho Natural;
- Processar Transcricao de Diagnostico;
- Transformar Framework em Ferramenta;
- Revisar Output por Quality Gate;
- Criar Post sem Apagar Voz;
- Gerar Handoff de Projeto;
- Promover Nota para Framework.

Exemplos de mentores/lentes candidatas:

- mentor de estrategia e foco;
- mentor de operacao B2B;
- mentor de produto/SaaS;
- mentor de copy/conteudo;
- mentor de automacao e processo;
- mentor de vendas consultivas;
- mentor de design de sistemas.

Observacao:

A escolha de pessoas/frameworks especificos deve acontecer nessa wave, com sugestoes da IA e aprovacao de Thiago. A IA deve pedir o prompt de clones antes de criar qualquer mentor.

Entregaveis:

- politica global/local de skills;
- pasta ou indice para skills e mentores;
- skill universal `Criar Mentor`;
- primeira leva pequena de skills testaveis;
- sugestoes de mentores por projeto.

Criterio de pronto:

- existe um metodo para criar skills boas e mentores uteis sem baguncar o vault.

Pesquisa:

- pesquisar somente se um mentor depender de obra, framework ou pessoa especifica que precise de precisao.

#### Resultado da execucao da Wave 5

Arquivos criados:

- `07-Frameworks-and-Processes/AI-Skills-and-Mentors/README.md`
- `07-Frameworks-and-Processes/AI-Skills-and-Mentors/Politica-de-Skills-e-Mentores.md`
- `07-Frameworks-and-Processes/AI-Skills-and-Mentors/Backlog-Skills-e-Mentores.md`
- `07-Frameworks-and-Processes/AI-Skills-and-Mentors/Criar-Mentor.md`
- `07-Frameworks-and-Processes/AI-Skills-and-Mentors/Promover-Framework-para-Skill.md`
- `07-Frameworks-and-Processes/AI-Skills-and-Mentors/Mentores/Alex-Hormozi-Mentor-de-Teste.md`
- `05-Clients-and-Mentoring/Mentoria-IA/05-Skills/README.md`
- `05-Clients-and-Mentoring/Mentoria-IA/05-Skills/Processar-Transcricao-Diagnostico-de-Mentoria.md`

Arquivos atualizados:

- `07-Frameworks-and-Processes/README.md`
- `00-Start-Here/MOC-Frameworks.md`
- `05-Clients-and-Mentoring/Mentoria-IA/README.md`
- `00-Start-Here/MOC-Clients-and-Mentoring.md`
- `00-Start-Here/Plano-de-Acao-Wave-5-Skills-Comandos-e-Mentores.md`

Decisoes:

| Frente | Decisao Wave 5 |
|---|---|
| Criar Mentor | criada como skill global baseada no processo de clone/mentor |
| Promover Framework para Skill | criada como skill global leve |
| Mentoria IA | criada skill compartilhada de processamento de transcricao e diagnostico |
| Playbook | skills especificas adiadas; nao criar `Localizar Dono de Mudanca no Squad` agora |
| Alex Hormozi | criado mentor de teste em status `draft-test`, com checkpoint L6-L8 pendente |

Criterio de pronto atingido:

- existe politica global/local;
- existe backlog de skills e mentores;
- primeira leva ficou pequena;
- o mentor de teste tem fontes e limites;
- o checkpoint humano impede transformar o rascunho em autoridade final sem validacao.

### Wave 6 - Feedback loops e quality gates

Status:

- plano de aplicacao preparado em 2026-05-17;
- executada em 2026-05-17;
- plano detalhado em [[00-Start-Here/Plano-de-Acao-Wave-6-Feedback-Loops-e-Quality-Gates|Plano de Acao - Wave 6 - Feedback Loops e Quality Gates]].

Objetivo:

Fazer outputs voltarem para o sistema como aprendizado, nao como arquivo morto.

Execucao da IA:

- criar template de feedback por projeto;
- criar quality gate geral para outputs;
- criar quality gate especifico para automacao;
- criar regra de quando automatizar e quando manter humano;
- conectar feedback a Strategy OS, Project OS e frameworks.

Entregaveis:

- template de feedback;
- checklist de qualidade;
- regra de automacao sem queda de output;
- campos minimos para metricas e aprendizados.

Criterio de pronto:

- cada output importante tem um caminho para gerar aprendizado e proxima iteracao.

Pesquisa:

- nao necessaria, salvo metricas ou benchmarks externos.

#### Resultado da execucao da Wave 6

Executada em 2026-05-17.

Arquivos criados:

- `07-Frameworks-and-Processes/Second-Brain-System/Feedback-Loops-and-Quality-Gates.md`
- `04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/04-Feedback/README.md`

Arquivos atualizados:

- `07-Frameworks-and-Processes/README.md`
- `00-Start-Here/MOC-Frameworks.md`
- `07-Frameworks-and-Processes/Second-Brain-System/Project-OS-Template.md`
- `04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/PROJECT.md`
- `04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/04-Feedback/2026-05-14-QA-Templates.md`
- `00-Start-Here/Plano-de-Acao-Wave-6-Feedback-Loops-e-Quality-Gates.md`

Decisoes:

| Frente | Decisao Wave 6 |
|---|---|
| Framework global | criar um unico arquivo leve para feedback loops e quality gates |
| Project OS Template | apontar `04-Feedback/` para o framework, sem exigir formulario para microajuste |
| Playbook | usar como piloto padrao, porque e prioridade ativa e ja tinha QA real |
| Strategy OS | nao atualizar, porque o feedback do QA muda o projeto, nao prioridade ou trade-off estrategico |
| Skills | nao criar skill global de revisao ainda; testar o framework como checklist antes |
| Dashboards/Dataview/Bases | nao criar agora |

Criterio de pronto atingido:

- existe framework global leve;
- o template de Project OS aponta para ele;
- o Playbook tem guia local de feedback;
- o QA existente foi roteado como `quality-review`;
- a regra de propagacao protege Strategy OS de feedback local;
- nao houve backfill historico nem criacao de dashboard.

### Wave 7 - Marca pessoal e LinkedIn

Status:

- executada em 2026-05-17 como `LinkedIn Content OS`.
- plano detalhado em [[00-Start-Here/Plano-de-Acao-Wave-7-LinkedIn-Content-OS|Plano de Acao - Wave 7 - LinkedIn Content OS]].
- foco corrigido: nao e apenas fechar um post; e substituir o Thiago Marketing OS pesado por um pipeline simples dentro do Second Brain.

Arquivos base:

- `06-Personal-Brand/Personal-Brand-OS.md`
- `06-Personal-Brand/Linkedin/AGENTS.md`
- `06-Personal-Brand/Linkedin/Pipeline-de-Conteudo.md`
- `06-Personal-Brand/Linkedin/Posts/segundo-cerebro/POST.md`
- `06-Personal-Brand/Linkedin/Ideias-Brutas/README.md`
- `07-Frameworks-and-Processes/06-Personal-Brand/LinkedIn-Idea-to-Post-Workflow.md`

Antes de executar, perguntar a Thiago:

```text
Me da o contexto da sua marca pessoal agora:
- qual objetivo dos proximos 30 dias;
- que tipo de oportunidade voce quer atrair;
- quais posts ou ideias voce mais quer tirar do papel;
- que tom voce quer manter;
- o que voce nao quer parecer.
```

Contexto respondido por Thiago em 2026-05-17:

- Thiago tinha um sistema externo em `D:\1AWinningSales-Projetos\thiagomarketingos`.
- O sistema tinha visual e squads uteis, mas ficou overengineered.
- O comportamento real de captura era escrever rapido em ideias brutas, antes no Notion e agora no Obsidian.
- Thiago quer organizacao melhor de pastas, uma ideia por pasta quando fizer sentido, e um fluxo de ideia para post.
- `Swipe-File` nao era usado.
- `Posts-Publicados` nao precisa existir; depois de agendar no LinkedIn nao precisa registrar por padrao.
- O squad `pesquisa-conteudo-linkedin` deve ser simplificado para hook, estrutura e retencao do texto.
- `seed-pautas-centrais` nao deve ser migrado.
- `comentarios-linkedin` deve virar workflow manual/draft, sem UI/Supabase/CCC.
- `capas-linkedin` e `carrosseis-linkedin` devem virar workflows futuros, removendo dependencia da UI do Thiago Marketing OS.

Execucao da IA:

- manter originais preservados;
- criar `06-Personal-Brand/Linkedin/AGENTS.md`;
- criar `Pipeline-de-Conteudo.md`;
- reorganizar ideias brutas em pastas por ideia;
- transformar `Posts-Rascunhos` em `Posts/<slug>/`;
- mover o post do Segundo Cerebro para `Posts/segundo-cerebro/`;
- criar `PREVIEW.md` e `visual/brief.md` para visualizar texto e imagem sem UI pesada;
- destilar workflows dos squads antigos;
- remover areas ativas que Thiago nao usa.

Entregaveis:

- LinkedIn Content OS em Markdown;
- post do Segundo Cerebro em pasta propria;
- ideias brutas separadas;
- workflow de post;
- workflows futuros de comentarios, capa e carrossel;
- decisao documentada sobre squads antigos.

Criterio de pronto:

- Thiago abre a pasta de LinkedIn e sabe qual post vem agora e por que.

Pesquisa:

- pesquisar somente se o post fizer claims externos sobre mercado, ROI, ferramentas ou dados atuais.

#### Resultado da execucao da Wave 7

Arquivos criados:

- `00-Start-Here/Plano-de-Acao-Wave-7-LinkedIn-Content-OS.md`
- `06-Personal-Brand/Linkedin/AGENTS.md`
- `06-Personal-Brand/Linkedin/Pipeline-de-Conteudo.md`
- `06-Personal-Brand/Linkedin/Ideias-Brutas/README.md`
- `06-Personal-Brand/Linkedin/Ideias-Brutas/00-Captura-Rapida.md`
- `06-Personal-Brand/Linkedin/Ideias-Brutas/segundo-cerebro/IDEIA.md`
- `06-Personal-Brand/Linkedin/Ideias-Brutas/processo-pre-automacao/IDEIA.md`
- `06-Personal-Brand/Linkedin/Ideias-Brutas/aristoteles-automacao/IDEIA.md`
- `06-Personal-Brand/Linkedin/Ideias-Brutas/skill-agent-workflow/IDEIA.md`
- `06-Personal-Brand/Linkedin/Ideias-Brutas/sdrs-nao-deveriam-prospectar/IDEIA.md`
- `06-Personal-Brand/Linkedin/Ideias-Brutas/hype-acabou/IDEIA.md`
- `06-Personal-Brand/Linkedin/Posts/README.md`
- `06-Personal-Brand/Linkedin/Posts/segundo-cerebro/POST.md`
- `06-Personal-Brand/Linkedin/Posts/segundo-cerebro/PREVIEW.md`
- `06-Personal-Brand/Linkedin/Posts/segundo-cerebro/visual/brief.md`
- `06-Personal-Brand/Linkedin/Workflows/Criar-Post-a-Partir-de-Ideia.md`
- `06-Personal-Brand/Linkedin/Workflows/Gerar-Comentarios-LinkedIn.md`
- `06-Personal-Brand/Linkedin/Workflows/Criar-Capa.md`
- `06-Personal-Brand/Linkedin/Workflows/Criar-Carrossel.md`
- `06-Personal-Brand/Linkedin/Workflows/Decisoes-Squads-Antigos.md`

Arquivos removidos como areas ativas:

- `06-Personal-Brand/Linkedin/Ideias-Brutas/Ideias-Iniciais-Notion.md`
- `06-Personal-Brand/Linkedin/Posts-Rascunhos/Post-Segundo-Cerebro.md`
- `06-Personal-Brand/Linkedin/Posts-Rascunhos/README.md`
- `06-Personal-Brand/Linkedin/Swipe-File/README.md`
- `06-Personal-Brand/Linkedin/Posts-Publicados/README.md`

Arquivos atualizados:

- `06-Personal-Brand/Linkedin/README.md`
- `00-Start-Here/MOC-Personal-Brand.md`
- `00-Start-Here/Obsidian-Home.md`
- `AGENTS.md`
- `07-Frameworks-and-Processes/04-Work-Winning-Sales/Assistida-Workflow-Agent.md`

Decisoes:

| Frente | Decisao Wave 7 |
|---|---|
| Thiago Marketing OS | nao e mais centro operacional; vira fonte de criterios |
| Captura | usar `00-Captura-Rapida.md` e pastas por ideia |
| Publicacao | nao registrar por padrao depois de agendar |
| Swipe File | remover como area ativa |
| Posts Publicados | remover como etapa ativa |
| Seed Pautas | nao migrar |
| Comentarios | migrar como workflow manual/draft |
| Capas/Carrosseis | deixar como workflows futuros |

Criterio de pronto atingido:

- abrir a pasta LinkedIn mostra o fluxo real;
- ideias principais deixaram de ficar em um arquivo unico;
- o post do Segundo Cerebro tem `POST`, `PREVIEW` e brief visual;
- os squads antigos foram destilados sem trazer UI, Supabase ou CCC.

### Wave 8 - Raw imports virando fila de ativos

Status:

- cancelada como wave propria em 2026-05-17.
- absorvida pela Wave 7.

Decisao:

- quase tudo que havia valor no export historico do Notion ja foi extraido para o Second Brain;
- raw imports continuam como fonte/proveniencia;
- nao faz sentido rodar uma wave separada para reprocessar tudo;
- quando uma parte dos imports for util para conteudo, projeto, framework ou oferta, ela deve ser destilada no contexto da wave ou tarefa viva.

Arquivos:

- `10-Legacy-Imports/Notion-Export-2026-05/Marketing/Marketing-Raw-Import.md`
- `10-Legacy-Imports/Notion-Export-2026-05/Winning-Sales/Winning-Sales-Raw-Import.md`
- `10-Legacy-Imports/Notion-Export-2026-05/Meus-Processos/Meus-Processos-Raw-Import.md`

Pergunta antes de executar:

```text
Dos imports antigos, o que voce mais quer destravar primeiro: conteudo, oferta, projeto da Winning Sales, framework, ou organizacao geral?
```

Execucao da IA:

- extrair candidatos a post, framework, projeto, skill, mentor e oferta;
- criar lista curta de ativos;
- marcar o que fica apenas como fonte;
- evitar reprocessar tudo sem objetivo;
- conectar ativos a Strategy OS ou Project OS.

Entregaveis:

- fila de destilacao;
- ativos priorizados;
- menos dependencia de garimpo manual.

Criterio de pronto:

- raw imports permanecem como fonte;
- nao ha reprocessamento sem objetivo;
- conteudo util de Marketing foi absorvido no LinkedIn Content OS.

Pesquisa:

- nao necessaria para triagem;
- necessaria apenas para validar claims externos ou ferramentas citadas.

### Wave 9 - Learning e Sources com retorno pratico

Status:

- executada em 2026-05-17 como piloto de `AGENTS.md` por dominio.

Arquivos:

- `08-Learning/Learning-Priorities.md`
- `09-Sources-and-References/README.md`

Pergunta antes de executar:

```text
Como voce quer que estudo vire resultado: post, framework, aplicacao em projeto, card Anki, aula, mentor, ou referencia para decisao?
```

Execucao da IA:

- criar `08-Learning/AGENTS.md`;
- criar template minimo para nota de livro;
- criar template minimo para nota de fonte;
- criar regra de processamento;
- conectar estudos a projetos, marca pessoal, mentores ou frameworks;
- criar regra para mudar o `AGENTS.md` sem deixa-lo vulneravel a feedback solto.

Entregaveis:

- aprendizado com saida pratica;
- menos acumulacao de fonte solta;
- criterio de signal para fontes.

Criterio de pronto:

- uma nota de estudo nova ja nasce com caminho para uso.

Pesquisa:

- pesquisar conforme fonte especifica do estudo.

#### Resultado da execucao da Wave 9

Arquivos criados:

- `08-Learning/AGENTS.md`
- `08-Learning/Instruction-Change-Log.md`
- `08-Learning/Templates/Nota-de-Livro.md`
- `08-Learning/Templates/Nota-de-Fonte.md`

Arquivos atualizados:

- `08-Learning/README.md`
- `09-Sources-and-References/README.md`
- `AGENTS.md`
- `00-Start-Here/AI-READ-ME-FIRST.md`
- `02-AI-Operating-System/System-Maintenance-Rules.md`

Decisoes:

- usar o padrao `AGENTS.md`, nao `AGENT.md`;
- criar piloto primeiro em Learning, sem espalhar para todas as pastas;
- mudancas no `AGENTS.md` de Learning devem passar por `Instruction-Change-Log.md`;
- estudo deve virar aplicacao, criterio, post, framework, Anki, referencia ou repertorio consciente.

### Wave 10 - Captura rapida e mobile workflow

Status:

- executada em 2026-05-17 como `AGENTS.md` local do Inbox.

Objetivo:

Garantir que ideias entrem no sistema sem virar cemiterio.

Antes de executar, perguntar:

```text
Como voce captura ideias hoje fora do computador?
- celular;
- audio;
- WhatsApp/Telegram;
- Obsidian mobile;
- nota diaria;
- outra forma.
```

Execucao da IA:

- criar `01-Inbox/AGENTS.md`;
- atualizar `01-Inbox/README.md`;
- definir que, ao pedir "organiza o Inbox", a IA classifica e move capturas;
- conectar captura a LinkedIn, projetos, Learning, fontes, frameworks, clientes ou arquivo;
- nao instalar Dispatch/plugin.

Entregaveis:

- captura rapida com baixo atrito;
- rotina de triagem;
- menos ideias perdidas.

Criterio de pronto:

- uma ideia capturada tem caminho claro ate virar projeto, post, framework ou arquivo.

Pesquisa:

- pesquisar apenas se Thiago quiser investigar app/plugin/sync.

#### Resultado da execucao da Wave 10

Arquivos criados:

- `01-Inbox/AGENTS.md`

Arquivos atualizados:

- `01-Inbox/README.md`
- `00-Start-Here/Day-to-Day-Use.md`

Decisao:

- nao criar app, plugin ou rotina mobile agora;
- usar o Inbox como captura bruta;
- a IA organiza depois no computador quando Thiago pedir.

### Wave 11 - Loop de manutencao

Status:

- deprecada em 2026-05-17.
- nao executar como wave independente.
- substituida pelas regras de manutencao por gatilho em `02-AI-Operating-System/System-Maintenance-Rules.md`.
- grande parte do objetivo ja foi absorvida pelas Waves 0.5, 6, 9 e 10.

Objetivo:

Historico: fazer o sistema continuar vivo por gatilhos naturais, sem virar manutencao pesada.

Leitura atual:

- o Strategy OS ja define atualizacao sem ritual manual;
- feedback loops e quality gates ja dizem quando feedback deve propagar;
- Inbox e Learning ja tem `AGENTS.md` locais para manutencao quando Thiago pedir;
- `Day-to-Day-Use` ja documenta o comando pratico para organizar o Inbox;
- portanto, criar uma revisao mensal adicionaria compromisso que Thiago provavelmente nao vai cumprir.

Decisao:

- deprecar a Wave 11 como etapa de execucao;
- manter apenas a regra operacional: manutencao acontece quando uma tarefa real revelar acumulacao, duplicacao, instrucao quebrada, nota sem destino ou oportunidade clara de promocao/arquivamento;
- nao criar checklist mensal, dashboard, calendario ou ritual separado.

Execucao da IA:

- nao criar rotina mensal obrigatoria;
- nao criar dashboard, calendario ou checklist longo de auditoria;
- consolidar em `02-AI-Operating-System/System-Maintenance-Rules.md` os criterios minimos de arquivamento, promocao e controle de complexidade;
- aplicar manutencao somente quando uma tarefa real revelar acumulacao, duplicacao, instrucao quebrada ou nota sem destino;
- criar criterio de promocao: nota -> projeto, framework, skill, post ou mentor;
- criar criterio de arquivamento para conteudo antigo, encerrado ou sem acao relevante.

Entregaveis:

- rejeicao explicita de revisao mensal manual;
- criterio de arquivamento;
- criterio de promocao de notas;
- controle de complexidade.

Criterio de pronto:

- uma IA futura sabe quando limpar, arquivar, promover ou deixar quieto durante uso real;
- o vault melhora por uso real, nao por reorganizacao infinita.

## Ordem recomendada

1. Wave 0 - Bootstrapping da IA.
2. Wave 0.5 - Strategy OS e contexto vivo.
3. Wave 1 - Classificacao dos projetos e Project OS template.
4. Wave 2 - Projetos ativos como cockpit ou Project OS.
5. Wave 3 - Marcelo como trilha de mentoria executavel.
6. Wave 4 - Frameworks virando ferramentas.
7. Wave 5 - Skills, comandos e mentores.
8. Wave 6 - Feedback loops e quality gates.
9. Wave 7 - Marca pessoal e LinkedIn.
10. Wave 8 - Cancelada/absorvida pela Wave 7.
11. Wave 9 - Learning e Sources com retorno pratico.
12. Wave 10 - Captura rapida e mobile workflow.
13. Wave 11 - Deprecada; usar manutencao por gatilho.

## Definicao geral de pronto

Uma wave so esta pronta quando:

- os arquivos foram atualizados;
- as decisoes inferidas foram separadas de fatos confirmados;
- as duvidas reais foram agrupadas;
- nao ficaram placeholders vazios;
- existe proxima acao clara;
- outputs, feedback e quality gates estao conectados quando fizer sentido;
- skills criadas foram testadas ou deixadas explicitamente como draft;
- os artefatos criados podem ser usados em uma conversa futura com IA ou em trabalho real.
