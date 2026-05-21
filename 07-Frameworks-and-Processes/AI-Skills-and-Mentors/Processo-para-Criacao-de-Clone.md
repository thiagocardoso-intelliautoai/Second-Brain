---
source: Notion
derived_from: Notion > Meus processos > Processo para criacao de clone
created_at: 2026-05-16
status: distilled
---

# Processo para Criacao de Clone

## Objetivo

Criar um clone cognitivo ou mentor operacional a partir de uma pessoa/fonte de referencia.

## Processo base

1. Pesquisar quem e o melhor do mundo ou melhor referencia naquele assunto.
2. Coletar fontes confiaveis.
3. Usar pipeline de clone mind.
4. Validar identidade, modelos mentais e linguagem.
5. Criar system prompt ou skill utilizavel.

## Camadas do metodo citado

- viabilidade;
- fontes;
- padroes comportamentais;
- transicoes de estado;
- modelos mentais;
- arquitetura cognitiva;
- valores;
- obsessões;
- contradicoes produtivas;
- sintese;
- implementacao;
- validacao.

## Checkpoint humano obrigatorio

Validar:

- valores;
- obsessões;
- contradicoes produtivas.

Sem isso, o clone pode ficar tecnicamente detalhado, mas psicologicamente falso.

## Uso pratico

Aplicar quando Thiago quiser:

- estudar um especialista;
- criar mentor para uma area;
- capturar metodo de alguem;
- transformar repertorio em agente ou skill.
## PROMPT
```
---
name: clone-mind
description: |
  Orquestracao multi-agente para clonagem cognitiva usando metodologia DNA Mental™ de 9 camadas.
  Cria clones de alta fidelidade que pensam, comunicam e decidem como o especialista original.
  Triggers: "clone mind", "clonar mente", "/clone-mind", "map mind", "criar clone"

model: opus

arguments:
  - name: slug
    description: Identificador único do mind em snake_case (ex: daniel_kahneman, naval_ravikant)
    required: true
  - name: mode
    description: "Modo de execução: auto (detecta), public (figuras públicas), no-public-interviews, no-public-materials"
    required: false
  - name: resume
    description: Retomar de checkpoint anterior (true/false)
    required: false

allowed-tools:
  - Read
  - Grep
  - Glob
  - Task
  - Write
  - Edit
  - Bash
  - WebSearch
  - WebFetch
  - AskUserQuestion

permissionMode: acceptEdits

memory: project
---
```
