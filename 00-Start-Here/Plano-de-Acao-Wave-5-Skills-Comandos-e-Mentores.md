---
source: user request
created_at: 2026-05-17
status: executed
related_plan: 00-Start-Here/Plano-de-Aprimoramento-Second-Brain.md
related_frameworks_backlog: 07-Frameworks-and-Processes/AI-Skills-and-Mentors/Frameworks-to-Skills-Backlog.md
related_clone_process: 07-Frameworks-and-Processes/AI-Skills-and-Mentors/Processo-para-Criacao-de-Clone.md
external_reference: https://github.com/SynkraAI/aiox-core/blob/main/.claude/skills/clone-mind.md
---

# Plano de Acao - Wave 5 - Skills, Comandos e Mentores

## Objetivo da Wave 5

Criar a camada operacional minima para skills, comandos e mentores no Second Brain sem transformar o vault em uma biblioteca gigante de prompts genericos.

A Wave 5 deve entregar:

- uma politica clara para decidir quando algo vira skill global, skill local ou mentor;
- uma pasta inicial para skills e mentores globais;
- a skill universal `Criar Mentor`, baseada no processo de clone/mentor de Thiago;
- um backlog pequeno e priorizado de skills e mentores candidatos;
- um criterio de teste para evitar criar artefato bonito que nao sera usado.

## Premissa importante

O prompt de clone/mentor ja foi fornecido por Thiago.

Fontes base:

- [[07-Frameworks-and-Processes/AI-Skills-and-Mentors/Processo-para-Criacao-de-Clone|Processo para Criacao de Clone]]
- GitHub: `SynkraAI/aiox-core/.claude/skills/clone-mind.md`

Portanto, a execucao da Wave 5 nao precisa pedir novamente:

```text
Me envia o prompt que voce tem para gerar clones/mentores.
```

A pergunta que ainda precisa existir antes da execucao e outra:

```text
Quais 1 ou 2 frentes mais precisam de uma skill ou mentor agora: Strategy OS, Winning Sales/Playbook, Marcelo, LinkedIn, automacao ou outra?
```

## Leitura obrigatoria antes de executar

Antes de mexer em arquivos, ler:

- `00-Start-Here/AI-READ-ME-FIRST.md`
- `00-Start-Here/System-Map.md`
- `00-Start-Here/Strategy-OS.md`
- `02-AI-Operating-System/AI-Behavior-and-Communication.md`
- `00-Start-Here/Plano-de-Aprimoramento-Second-Brain.md`
- `07-Frameworks-and-Processes/README.md`
- `07-Frameworks-and-Processes/AI-Skills-and-Mentors/Frameworks-to-Skills-Backlog.md`
- `07-Frameworks-and-Processes/AI-Skills-and-Mentors/Processo-para-Criacao-de-Clone.md`
- `04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/05-Skills/Skills-Locais-Candidatas.md`

Se a Wave 5 tocar LinkedIn, ler tambem:

- `02-AI-Operating-System/Voice-Preservation-Rules.md`
- `06-Personal-Brand/Personal-Brand-OS.md`
- `06-Personal-Brand/Voz-e-Estilo/Do-Not-Rewrite-My-Voice.md`

Se a Wave 5 tocar Marcelo, ler tambem:

- `05-Clients-and-Mentoring/Mentoria-IA/Marcelo/README.md`
- `05-Clients-and-Mentoring/Mentoria-IA/Marcelo/03-Plano-da-Mentoria.md`
- `05-Clients-and-Mentoring/Mentoria-IA/Marcelo/04-Roteiro-Proxima-Reuniao.md`

## Decisao de desenho

### O que entra como skill global

Uma skill global deve viver em:

```text
07-Frameworks-and-Processes/AI-Skills-and-Mentors/
```

Ela so entra como global quando:

- resolve um problema transversal;
- pode ser usada em mais de um projeto;
- tem input definido;
- tem output esperado;
- tem criterio de qualidade;
- tem limite claro de quando nao usar;
- nao depende de contexto privado de um cliente ou projeto especifico.

### O que entra como skill local

Uma skill local deve viver perto do projeto ou cliente:

```text
04-Work-Winning-Sales/Projects/<Projeto>/05-Skills/
05-Clients-and-Mentoring/<Cliente>/05-Skills/
```

Ela entra como local quando:

- o uso esta preso a um projeto, cliente, repo ou entregavel especifico;
- depende de contexto canonico local;
- ainda nao foi provada como metodo transversal;
- seria perigoso generalizar cedo demais.

### O que entra como mentor ou clone mental

Mentor ou clone mental nao e autoridade final nem imitacao perfeita de uma pessoa.

E uma lente operacional para:

- decidir melhor;
- criticar output;
- fazer perguntas melhores;
- revisar trade-offs;
- transformar principios e modelos mentais em criterio pratico.

Todo mentor deve declarar:

- origem da inspiracao;
- fontes usadas;
- caso de uso;
- limites;
- anti-padroes;
- perguntas tipicas;
- criterio de qualidade;
- quando nao usar.

## Plano de execucao

### Fase 0 - Intake minimo

Antes de executar, perguntar somente o que falta para escolher foco real:

```text
Quais 1 ou 2 frentes mais precisam de uma skill ou mentor agora: Strategy OS, Winning Sales/Playbook, Marcelo, LinkedIn, automacao ou outra?

Para a primeira frente, voce quer:
- uma skill operacional;
- um mentor/lente;
- ou os dois?
```

Nao perguntar de novo pelo prompt de clone/mentor, porque Thiago ja apontou a fonte.

### Fase 1 - Criar estrutura base

Criar a pasta:

```text
07-Frameworks-and-Processes/AI-Skills-and-Mentors/
```

Criar arquivos iniciais:

- `README.md`
- `Politica-de-Skills-e-Mentores.md`
- `Backlog-Skills-e-Mentores.md`
- `Criar-Mentor.md`

Atualizar links em:

- `07-Frameworks-and-Processes/README.md`
- `00-Start-Here/MOC-Frameworks.md`
- `00-Start-Here/Plano-de-Aprimoramento-Second-Brain.md`

### Fase 2 - Criar a politica de skills e mentores

O arquivo `Politica-de-Skills-e-Mentores.md` deve conter:

- diferenca entre framework, prompt, template, skill, comando e mentor;
- regra global vs local;
- regra de promocao de framework para skill;
- regra de criacao de mentor;
- regra de teste;
- regra de descarte ou arquivamento;
- exemplos de uso dentro do vault.

Nao criar burocracia demais. O objetivo e impedir dois erros:

- criar prompt generico sem uso real;
- enterrar uma boa skill local dentro de uma nota solta.

### Fase 3 - Adaptar o clone-mind para `Criar Mentor`

O prompt `clone-mind` do GitHub deve ser tratado como metodologia de referencia, nao como infraestrutura literal.

Nao assumir que o vault tem:

- os mesmos agentes lendarios;
- os mesmos scripts Python;
- os mesmos caminhos `outputs/minds/{slug}`;
- o mesmo comando `/clone-mind`.

A skill `Criar-Mentor.md` deve adaptar a logica para Markdown local e uso por IA no Second Brain.

Estrutura minima da skill:

1. Quando usar.
2. Quando nao usar.
3. Inputs obrigatorios.
4. Modo de fonte:
   - figura publica com fontes abertas;
   - pessoa/conhecimento privado com materiais locais;
   - mentor sintetico baseado em principios internos;
   - atualizacao de mentor existente.
5. Pipeline adaptado:
   - L0 - viabilidade;
   - L1 - fontes;
   - L2 - padroes comportamentais;
   - L3 - gatilhos e transicoes de estado;
   - L4 - modelos mentais;
   - L5 - arquitetura cognitiva;
   - L6 - valores;
   - L7 - obsessoes;
   - L8 - contradicoes produtivas;
   - L9 - sintese e implementacao.
6. Checkpoint humano obrigatorio em L6-L8.
7. Output esperado:
   - `Mentor-Brief`;
   - `Mapa-de-Fontes`;
   - `Modelos-Mentais`;
   - `Perguntas-Tipicas`;
   - `Anti-Padroes`;
   - `System-Prompt-ou-Skill`;
   - `Relatorio-de-Qualidade`.
8. Quality gates.
9. Como testar.
10. Como atualizar ou arquivar.

### Fase 4 - Montar backlog inicial

Criar `Backlog-Skills-e-Mentores.md` com uma tabela curta:

| Candidato | Tipo | Global/local | Onde testar | Evidencia no vault | Risco de criar cedo demais | Decisao |
|---|---|---|---|---|---|---|

Fontes para o backlog:

- [[07-Frameworks-and-Processes/AI-Skills-and-Mentors/Frameworks-to-Skills-Backlog|Frameworks to Skills Backlog]]
- [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/05-Skills/Skills-Locais-Candidatas|Skills Locais Candidatas do Playbook]]
- [[00-Start-Here/Strategy-OS|Strategy OS]]
- [[05-Clients-and-Mentoring/Mentoria-IA/Marcelo/03-Plano-da-Mentoria|Plano da Mentoria Marcelo]]

Backlog inicial provavel:

| Candidato | Tipo | Provavel destino | Motivo |
|---|---|---|---|
| Criar Mentor | skill | global | Thiago ja tem processo e prompt; uso transversal |
| Promover Framework para Skill | skill | global | evita toolificacao prematura e conecta Wave 4 com Wave 5 |
| Sincronizacao Estrategica por Gatilho Natural | skill | global | Strategy OS precisa mudar por evidencias, nao por ritual |
| Melhorar Apresentacao de Entregavel | skill | local Playbook | apareceu como necessidade concreta no projeto prioritario |
| Skills locais do Playbook | skill | local Playbook | adiar ate Thiago retomar foco no Playbook e definir melhor o uso |
| Mentor de Estrategia e Foco | mentor | global ou Strategy OS | ajuda a decidir trade-offs sem inventar prioridade |
| Mentor de Automacao e Processo | mentor | global | conversa com Winning Sales, Marcelo e frameworks |
| Mentor de Vendas Consultivas | mentor | local Marcelo ou global futuro | util, mas depende de fontes e criterio do metodo |
| Mentor de Voz/LinkedIn | mentor/skill | local Personal Brand | exige preservacao de voz e nao deve apagar linguagem de Thiago |

### Fase 5 - Escolher primeira leva

Regra:

- criar no maximo 2 skills globais;
- criar no maximo 1 skill local;
- criar no maximo 1 mentor draft;
- qualquer mentor baseado em pessoa especifica precisa de aprovacao antes.

Primeira leva recomendada, se Thiago nao der outro foco:

1. `Criar Mentor` como skill global.
2. `Promover Framework para Skill` como skill global leve.
3. Nenhum mentor definitivo ainda; apenas backlog e criterio de escolha.

Se Thiago escolher Playbook como foco:

1. `Criar Mentor` global.
2. Nao criar skill local automaticamente.
3. Reabrir o contexto do Playbook e perguntar qual uso real se repetiu antes de transformar candidata em skill.

Se Thiago escolher Marcelo como foco:

1. `Criar Mentor` global.
2. `Processar Transcricao/Diagnostico de Mentoria` como candidata local ou global.
3. Mentor de vendas/processos fica como draft somente depois de definir fonte.

Se Thiago escolher LinkedIn:

1. `Criar Mentor` global.
2. `Criar Post sem Apagar Voz` como candidata local de Personal Brand.
3. Qualquer mentor de copy precisa respeitar os arquivos de preservacao de voz.

### Fase 6 - Testar a skill `Criar Mentor`

Teste minimo:

- escolher um caso controlado;
- rodar o pipeline ate L5;
- parar no checkpoint L6-L8;
- mostrar para Thiago valores, obsessoes e contradicoes produtivas propostos;
- so continuar se houver aprovacao ou revisao.

Casos seguros para teste:

- mentor sintetico de estrategia e foco baseado no Strategy OS;
- mentor sintetico de automacao e processo baseado nos frameworks internos;
- mentor local do Playbook baseado apenas no repo/cockpit, sem inventar pessoa externa.

Evitar no primeiro teste:

- clonar figura publica sem tempo para pesquisa de fontes;
- criar mentor de LinkedIn sem ler regras de voz;
- criar mentor comercial definitivo sem validar fontes e criterio com Thiago.

### Fase 7 - Atualizar indices e plano principal

Depois da execucao, atualizar:

- `07-Frameworks-and-Processes/README.md`
- `00-Start-Here/MOC-Frameworks.md`
- `00-Start-Here/Plano-de-Aprimoramento-Second-Brain.md`
- arquivos locais dos projetos tocados.

Registrar no plano principal:

- arquivos criados;
- skills criadas;
- mentores criados ou deixados como draft;
- perguntas pendentes;
- criterio de pronto atingido ou nao.

## Pesquisa externa

Pesquisa nao e necessaria para criar a estrutura da Wave 5.

Pesquisa passa a ser necessaria quando:

- o mentor for baseado em pessoa especifica;
- a skill depender de ferramenta atual;
- houver claims sobre mercado, ferramenta, ROI ou boas praticas externas;
- for preciso validar fontes primarias de uma figura publica.

Para mentores de figuras publicas, usar preferencialmente:

- livros, entrevistas longas, palestras, artigos e fontes primarias;
- materiais com autoria verificavel;
- triangulacao entre fontes.

Nao criar mentor com base em resumo superficial de internet.

## O que nao fazer na Wave 5

- Nao criar uma pasta cheia de mentores antes de saber onde eles serao usados.
- Nao transformar todo framework em skill.
- Nao criar clone como autoridade final.
- Nao prometer fidelidade psicologica sem fonte suficiente.
- Nao criar skill sem input, output e quality gate.
- Nao misturar skill local de projeto com skill global.
- Nao editar o repo externo do Playbook como parte da Wave 5, salvo se Thiago escolher explicitamente esse foco.
- Nao mexer em LinkedIn sem preservar a voz original de Thiago.

## Criterio de pronto da Wave 5

A Wave 5 estara pronta quando:

- a pasta `AI-Skills-and-Mentors` existir;
- a politica global/local estiver documentada;
- `Criar-Mentor.md` existir como skill universal testavel;
- o backlog de skills e mentores estiver priorizado com evidencia;
- a primeira leva tiver no maximo poucas skills, nao uma biblioteca gigante;
- pelo menos uma skill estiver testada ou marcada claramente como draft;
- qualquer mentor criado tiver fontes, limites e checkpoint humano;
- os indices principais apontarem para a nova camada;
- ficarem registradas as perguntas que dependem de decisao de Thiago.

## Perguntas pendentes para Thiago

Antes de executar a Wave 5, perguntar:

```text
Quais 1 ou 2 frentes mais precisam de uma skill ou mentor agora: Strategy OS, Winning Sales/Playbook, Marcelo, LinkedIn, automacao ou outra?

Para a primeira frente, voce quer uma skill operacional, um mentor/lente, ou os dois?

Se tiver uma pessoa especifica que voce quer transformar em mentor, qual e ela e quais fontes voce considera boas?
```

## Resultado da execucao

Executada em 2026-05-17.

Contexto dado por Thiago:

- Criar `Criar Mentor` como skill global.
- Criar `Promover Framework para Skill` como skill global leve.
- Nao criar `Localizar Dono de Mudanca no Squad`.
- Deixar skills especificas do Playbook para depois.
- Criar `Processar Transcricao/Diagnostico de Mentoria` como skill compartilhada do projeto de Mentoria de IA.
- Usar Alex Hormozi como mentor de teste da fase 6.

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
- `00-Start-Here/Plano-de-Aprimoramento-Second-Brain.md`

Decisoes:

| Frente | Decisao |
|---|---|
| Skills globais | criar apenas `Criar Mentor` e `Promover Framework para Skill` |
| Mentoria IA | criar skill compartilhada para processar transcricoes e diagnosticos |
| Playbook | nao criar skill nesta wave; retomar quando Thiago focar no Playbook |
| Alex Hormozi | criar mentor de teste em status `draft-test`, com checkpoint L6-L8 pendente |

Criterio de pronto:

- A pasta global de skills e mentores existe.
- A politica global/local existe.
- As duas skills globais foram criadas.
- A skill compartilhada de mentoria foi criada.
- O backlog registra o que foi criado, parked e adiado.
- O mentor Alex Hormozi foi criado como teste, mas nao como clone definitivo.
- Indices principais foram atualizados.
