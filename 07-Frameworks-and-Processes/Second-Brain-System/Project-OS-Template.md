---
source: Second Brain improvement wave 1
created_at: 2026-05-16
status: template
---

# Project OS Template

Use este template quando um projeto deixar de caber bem em um arquivo unico.

O Project OS existe para responder:

> Como este projeto gera output real?

## Quando usar

Use Project OS quando o projeto tiver pelo menos alguns destes sinais:

- muitos inputs ou fontes externas;
- multiplos outputs;
- recorrencia;
- cliente interno ou externo;
- automacao relevante;
- necessidade de feedback e log;
- skills, agentes ou prompts locais;
- risco de perder decisoes importantes no chat.

Nao use Project OS quando um arquivo unico ou cockpit simples resolver.

## Estrutura recomendada

```text
Nome-do-Projeto/
|-- PROJECT.md
|-- 00-Project-Brief.md
|-- 01-Inputs/
|-- 02-Process/
|-- 03-Outputs/
|-- 04-Feedback/
|-- 05-Skills/
`-- 06-Logs/
```

## PROJECT.md

Cockpit operacional do projeto.

Deve conter:

- estado atual confirmado;
- proxima acao real;
- decisores ou aprovadores confirmados;
- decisoes abertas;
- criterio de pronto;
- links para inputs, outputs, feedback e logs;
- links para repositorios, sistemas ou pastas externas.

Evite transformar o cockpit em dumping ground. Ele aponta para o resto do projeto.

## 00-Project-Brief.md

Brief vivo do projeto.

Campos recomendados:

- objetivo;
- por que importa agora;
- contexto;
- escopo;
- fora de escopo;
- criterios de qualidade;
- criterio de pronto;
- riscos;
- links principais.

Se algum campo operacional nao estiver confirmado, registre em `Perguntas para Thiago`.

## 01-Inputs/

Fontes e material bruto do projeto.

Exemplos:

- transcricoes;
- prompts recebidos;
- briefing de decisor;
- materiais de referencia;
- links externos;
- anexos;
- exports;
- prints;
- arquivos vindos de Downloads, Drive ou Notion.

Regra: preserve fonte e data. Nao misture input bruto com decisao final.

## 02-Process/

Como o projeto roda.

Exemplos:

- fluxo de trabalho;
- etapas;
- checkpoints humanos;
- criterios de qualidade;
- regras de validacao;
- arquitetura de agentes;
- automacoes;
- fallback manual.

## 03-Outputs/

Entregaveis do projeto.

Exemplos:

- docs finais;
- decks;
- planilhas;
- prompts aprovados;
- templates;
- links publicados;
- artefatos entregues ao cliente ou time.

## 04-Feedback/

Feedback e aprendizado que mudam proxima iteracao, criterio de qualidade, processo ou decisao.

Exemplos:

- feedback de aprovador;
- problemas encontrados;
- ajustes pedidos;
- metricas;
- resultados observados;
- aprendizados que mudam o processo.

Regra:

- use [[07-Frameworks-and-Processes/Second-Brain-System/Feedback-Loops-and-Quality-Gates|Feedback Loops and Quality Gates]] como referencia;
- nao crie nota de feedback para cada microajuste;
- nao backfille historico antigo sem motivo;
- registre feedback no menor local que preserva contexto;
- atualize Strategy OS somente se o feedback mudar prioridade, trade-off ou risco estrategico.

## 05-Skills/

Skills locais do projeto.

Uma skill local so deve existir quando tiver:

- caso de uso claro;
- input definido;
- output esperado;
- criterio de qualidade;
- quando usar;
- quando nao usar;
- exemplo minimo.

## 06-Logs/

Registro leve de decisoes e mudancas.

Exemplos:

- decisoes de escopo;
- mudancas de prioridade;
- reunioes relevantes;
- validacoes;
- handoffs;
- problemas resolvidos.

## Regra de link com repositorios externos

Quando o projeto tambem existir como repo, app ou pasta operacional fora do Second Brain, nao copie tudo para dentro do vault.

Use o Second Brain para:

- contexto;
- decisao;
- brief;
- log;
- fonte importante;
- criterio de qualidade;
- proximas acoes.

Mantenha fora do vault:

- codigo executavel;
- node_modules;
- builds;
- outputs pesados;
- wrappers de plataforma;
- arquivos temporarios.

## Perguntas para Thiago

Use esta secao quando faltar contexto real.

Pergunta padrao:

```text
Me da um contexto geral sobre [projeto]:
- onde isso esta hoje;
- o que aconteceu desde a ultima nota;
- o que esta travando;
- o que voce quer que exista como entrega;
- quem precisa aprovar ou decidir;
- como voce saberia que ficou pronto.
```
