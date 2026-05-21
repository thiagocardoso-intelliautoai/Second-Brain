---
source: user intake + Codex inspection
created_at: 2026-05-16
status: archived-superseded
related_plan: 00-Start-Here/Plano-de-Aprimoramento-Second-Brain.md
superseded_by: 04-Work-Winning-Sales/Projects/
---

# Classificacao dos Projetos Ativos - Wave 1

Esta nota registra a classificacao estrutural dos projetos depois da Wave 0.5.

Objetivo da Wave 1:

- decidir o que continua como arquivo unico;
- decidir o que vira cockpit;
- decidir o que vira Project OS;
- decidir o que deve ser arquivado, estacionado ou tratado em outra wave.

## Resumo executivo

| Projeto | Tipo sugerido | Status operacional | Proxima acao estrutural |
|---|---|---|---|
| Squad Playbook de Vendas | Project OS | ativo e prioridade Winning Sales | converter em Project OS na Wave 2 |
| Social Selling Automation - Samuel | arquivo unico estacionado / backlog | pausado por mudanca de prioridade | marcar como parked e nao pesquisar ferramentas agora |
| Central de IA - Winning Sales | arquivo unico de referencia / candidato a arquivo | finalizado e publicado | registrar URL, resultado e mover para referencia/arquivo se nao houver backlog vivo |
| Thiago Marketing OS / LinkedIn | pipeline simples de conteudo, nao Project OS pesado | app/interface pouco usada; fluxo real esta no Second Brain | importar apenas o que ajuda publicar/agendar e reorganizar LinkedIn em wave propria |

## Criterio usado

### Arquivo unico

Projeto curto, pouco recorrente, baixo volume de inputs/outputs ou sem necessidade clara de feedback/log.

### Cockpit

Projeto ativo que precisa de estado atual, proxima acao e decisoes abertas, mas ainda nao justifica pasta completa.

### Project OS

Projeto recorrente, com muitos inputs/outputs, entregaveis, validacao humana, automacao, skills locais, logs e risco de perder decisoes em conversas soltas.

### Arquivar

Projeto encerrado, pausado sem acao neste ciclo ou substituido por outra prioridade.

### Framework

Projeto que deixou de ser frente viva e virou metodo reutilizavel.

## Classificacao detalhada

| Projeto | Evidencia no vault e no intake | Tipo sugerido | Motivo | Inputs/outputs | Recorrencia | Feedback/log | Skills locais | Contexto faltante | Proxima acao |
|---|---|---|---|---|---|---|---|---|---|
| Squad Playbook de Vendas | Thiago confirmou que a prioridade mudou para Playbook por Rafael; repo real em `D:\1AWinningSales-Projetos\squadfactory\squads\playbook-comercial-squad`; arquivo do Second Brain esta desatualizado; prompts de melhoria estao em `C:\Users\thiag\Downloads\Melhorar Playbook de vendas Templates.txt` | Project OS | projeto ativo, prioridade da Winning, com squad, skills, agentes, templates, outputs, validacao e revisao de modelos | alto | recorrente | necessario | sim | confirmar se o criterio de pronto da proxima etapa e piloto, validacao geral ou revisao dos modelos ruins | converter na Wave 2 |
| Social Selling Automation - Samuel | Thiago confirmou que foi uma reuniao com Samuel e perdeu prioridade depois que Rafael direcionou para Playbook | arquivo unico estacionado / backlog | tem risco tecnico e pesquisa futura, mas nao e prioridade operacional agora | medio | incerta | util depois, nao agora | talvez no futuro | confirmar se deve ir para `99-Archive` ou ficar como backlog Winning Sales | marcar como parked na Wave 2 |
| Central de IA - Winning Sales | Thiago confirmou que foi criada e finalizada; URL: https://central-de-ia.vercel.app | arquivo unico de referencia / candidato a arquivo | produto entregue; se nao houver backlog vivo, nao precisa Project OS | medio | incerta | util se houver iteracao futura | nao agora | confirmar se existe manutencao/backlog ou se e apenas entrega final | registrar resultado e decidir destino na Wave 2 |
| Thiago Marketing OS / LinkedIn | Thiago confirmou que a interface virou overengineering; uso real acontece escrevendo ideias em `06-Personal-Brand\Linkedin\Ideias-Brutas`; repo externo em `D:\1AWinningSales-Projetos\thiagomarketingos` tem squads, dashboard, Supabase e scripts | pipeline simples de conteudo, nao Project OS pesado | problema atual nao e app; e fluxo rapido de capturar, visualizar, criar, publicar/agendar e preservar voz | medio | recorrente | sim, para metricas de posts | talvez, mas poucas | identificar qual MCP/script de postar/agendar vale reaproveitar sem trazer a complexidade do app | tratar na Wave 7 ou em uma wave dedicada de LinkedIn |

## Decisoes confirmadas por Thiago

- Social Selling Automation - Samuel ficou parado por mudanca de prioridade.
- Rafael, socio da Winning Sales, direcionou a prioridade para Playbook de Vendas.
- Squad Playbook de Vendas esta em construcao no repo externo `D:\1AWinningSales-Projetos\squadfactory\squads\playbook-comercial-squad`.
- O arquivo atual do Second Brain sobre Playbook esta desatualizado.
- Todos os skills e squads do Playbook existem, mas ainda nao estao finalizados.
- Falta revisar modelos ruins e fazer validacao geral.
- Prompts de melhoria do Playbook estao em `C:\Users\thiag\Downloads\Melhorar Playbook de vendas Templates.txt`.
- Central de IA - Winning Sales ja foi criada e finalizada em https://central-de-ia.vercel.app.
- Thiago Marketing OS ficou overengineered para o uso real.
- Para LinkedIn, o fluxo real mais rapido hoje e escrever ideias direto em `06-Personal-Brand\Linkedin\Ideias-Brutas`.

## Recomendacao sobre onde deixar o squad do Playbook

Nao trazer o repo inteiro do squad para dentro do Second Brain.

Motivo mecanico:

- o repo externo e a fonte operacional do squad;
- ele tem agentes, wrappers, scripts, outputs, previews e possiveis arquivos temporarios;
- copiar isso para o vault criaria duplicacao, ruido e risco de editar a fonte errada.

O melhor desenho:

- manter `D:\1AWinningSales-Projetos\squadfactory\squads\playbook-comercial-squad` como fonte canonica de execucao;
- criar no Second Brain um Project OS do Playbook com cockpit, brief, logs, decisoes, inputs importantes e links para o repo real;
- mover ou copiar o prompt de Downloads para `01-Inputs/` do Project OS quando a conversao acontecer;
- guardar no Second Brain apenas material que melhora decisao, execucao e memoria do projeto.

## Recomendacao sobre Thiago Marketing OS

Nao continuar tentando fazer o app/interface ser o centro do fluxo de LinkedIn.

O uso real mostrou que o caminho simples venceu:

- ideia nasce rapido no Second Brain;
- rascunho evolui em Markdown;
- versao sugerida preserva original;
- post final fica facil de achar;
- publicacao/agendamento pode ser um comando ou script acoplado, nao um produto inteiro.

Na wave de LinkedIn, importar apenas:

- prompts/squads que realmente melhoram escrita ou visual;
- criterio de qualidade;
- scripts ou MCP de publicar/agendar, se estiverem funcionando;
- exemplos bons;
- estrutura de status dos posts.

Nao importar:

- `node_modules`;
- dashboard inteiro como operacao principal;
- Supabase como dependencia obrigatoria;
- backlog tecnico do app;
- outputs gerados sem uso claro.

## Ordem recomendada para a Wave 2

1. Converter `Squad-Playbook-de-Vendas.md` em Project OS, sem copiar o repo inteiro.
2. Capturar o arquivo `C:\Users\thiag\Downloads\Melhorar Playbook de vendas Templates.txt` como input bruto do Project OS do Playbook.
3. Atualizar o cockpit do Playbook com estado real: analise tecnica, skills/squads feitos mas nao finalizados, revisao de modelos ruins e validacao geral.
4. Marcar Social Selling Automation - Samuel como `parked` ou mover para arquivo/backlog, sem pesquisa de ferramentas agora.
5. Registrar Central de IA como entregue, com URL e resultado; arquivar se nao houver backlog vivo.
6. Deixar Thiago Marketing OS como insumo para Wave 7 ou uma wave dedicada de LinkedIn simples.

## Perguntas para Thiago

- No Playbook, a proxima entrega que Rafael precisa ver e uma validacao geral do squad, modelos revisados ou um piloto com cliente ficticio/real?
- A Central de IA tem backlog vivo ou podemos tratar como entrega concluida e mover para referencia/arquivo?
- Social Selling deve ir para arquivo mesmo ou voce quer manter como backlog da Winning Sales?
- No Thiago Marketing OS, o mecanismo de postar/agendar ja funciona de ponta a ponta ou ainda e experimento?
