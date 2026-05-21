---
source: Notion
derived_from: Notion > Marketing > Linkedin > Armazem de Ideias > Os 3 tipos de Automacao com IA
created_at: 2026-05-16
status: distilled
---

# Assistida, Workflow e Agent

## Tese

Existem tres modos principais de trabalho com IA:

1. Assistida.
2. Workflow.
3. Agent.

A decisao correta nao e "usar IA ou nao". E decompor o processo e decidir qual modo serve para cada parte.

## 1. Assistida

Voce dirige. A IA executa pedacos.

Loop:

```text
voce pede -> IA responde -> voce avalia -> IA refina -> voce decide
```

Quando vale:

- alto valor por execucao;
- contexto complexo;
- baixa repeticao;
- julgamento humano agrega;
- tarefa unica ou pouco padronizada.

Escala com:

- tempo humano.

Exemplos:

- analise de proposta estrategica;
- diagnostico de processo complexo;
- criar uma tese de conteudo com muito contexto.

## 2. Workflow

Codigo ou ferramenta dirige. O caminho e predefinido.

Loop:

```text
trigger -> passos fixos -> output
```

Quando vale:

- alta repeticao;
- caminho previsivel;
- regras claras;
- saida precisa ser consistente;
- baixa necessidade de julgamento.

Escala com:

- infraestrutura.

Exemplos:

- classificacao inicial de leads;
- follow-up por regra;
- atualizacao de CRM;
- relatorio semanal.

## 3. Agent

LLM dirige em runtime. Recebe objetivo, usa ferramentas e decide os proximos passos.

Loop:

```text
objetivo -> escolhe tool -> le resultado -> decide proxima tool -> repete ate concluir
```

Quando vale:

- caminho imprevisivel;
- feedback verificavel;
- valor alto;
- variancia toleravel;
- custo/latencia aceitos.

Escala com:

- infraestrutura, mas com custo e latencia maiores que workflow.

Exemplos:

- pesquisa de prospect;
- debug de codigo;
- investigacao multi-fonte;
- analise que muda conforme achados.

## Segundo eixo: supervisao humana

Supervisao e decisao separada do modo.

Tipos:

- HITL: human-in-the-loop, humano aprova cada passo.
- HOTL: human-on-the-loop, humano monitora e intervem em excecoes.
- HOOTL: human-out-of-the-loop, humano so consome resultado.

## Fluxo de decisao

1. Quanto custa uma execucao do meu tempo em escala?
2. O caminho e previsivel?
3. Existe feedback verificavel?
4. As acoes sao reversiveis?

## Regras praticas

- Processo previsivel tende a workflow.
- Processo imprevisivel com feedback verificavel pode ser agent.
- Processo de alto julgamento e baixo volume tende a assistido.
- Acao irreversivel exige checkpoint humano.
- Agent sem feedback verificavel tende a produzir erro com confianca.

## Anti-padroes

- usar agent porque e cool;
- usar workflow puro em tarefa imprevisivel;
- manter assistido por inercia quando volume ja justifica automacao;
- workflow sem checkpoint para acao critica;
- agent sem condicao de parada.

## Status operacional

Este framework continua como referencia de decisao, nao como skill pronta.

Use para classificar partes de um processo antes de escolher ferramenta ou arquitetura. So transformar em prompt, template ou skill quando a classificacao se repetir em projetos reais.

Backlog relacionado:

- [[07-Frameworks-and-Processes/AI-Skills-and-Mentors/Frameworks-to-Skills-Backlog|Frameworks to Skills Backlog]]

## Links relacionados

- [[07-Frameworks-and-Processes/04-Work-Winning-Sales/Technology-Mapping-and-Process-Diagnosis|Technology Mapping and Process Diagnosis]]
- [[07-Frameworks-and-Processes/04-Work-Winning-Sales/Processo-de-Automatizar-Processos-PDCA|Processo de Automatizar Processos - PDCA]]
- [[04-Work-Winning-Sales/Projects/Social-Selling-Automation-Samuel|Social Selling Automation - Samuel]]
- [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas|Squad Playbook de Vendas]]
- [[06-Personal-Brand/Linkedin/Ideias-Brutas/skill-agent-workflow/IDEIA|Ideia - Skill, Agent e Workflow]]
