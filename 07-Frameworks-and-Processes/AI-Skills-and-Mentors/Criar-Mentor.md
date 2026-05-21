---
source: Wave 5 execution
created_at: 2026-05-17
status: active-skill
based_on:
  - 07-Frameworks-and-Processes/AI-Skills-and-Mentors/Processo-para-Criacao-de-Clone.md
  - https://github.com/SynkraAI/aiox-core/blob/main/.claude/skills/clone-mind.md
---

# Criar Mentor

## Funcao

Criar um mentor ou clone mental como lente operacional para decisao, critica, estrategia, aprendizado ou execucao.

Mentor nao e imitacao perfeita nem autoridade final. E uma forma estruturada de usar fontes, principios e modelos mentais para pensar melhor.

## Quando usar

Use quando Thiago quiser:

- estudar uma pessoa ou escola de pensamento;
- criar uma lente para revisar estrategia, oferta, conteudo, automacao ou mentoria;
- transformar repertorio em agente, prompt ou skill;
- aplicar um especialista em um projeto sem perder criterio.

## Quando nao usar

Nao use quando:

- o objetivo for copiar voz pessoal sem fonte suficiente;
- a pessoa for privada e nao houver autorizacao ou material local;
- a tarefa pedir resposta factual simples;
- a IA estiver prestes a inventar valores, obsessao ou contradicao produtiva;
- o mentor viraria desculpa para terceirizar decisao humana.

## Inputs obrigatorios

- alvo do mentor;
- caso de uso;
- local onde o mentor vai viver;
- modo de fonte;
- nivel desejado: rascunho, mentor operacional ou system prompt;
- 1 a 3 tarefas em que o mentor sera testado.

## Modos de fonte

| Modo | Uso | Regra |
|---|---|---|
| figura publica | pessoa com livros, entrevistas, aulas e materiais publicos | pesquisar fontes antes de criar |
| materiais locais | pessoa/projeto com transcricoes, notas ou documentos internos | preservar fonte e confidencialidade |
| mentor sintetico | lente baseada em principios internos do vault | declarar que nao e pessoa real |
| atualizacao | melhorar mentor existente | preservar versao anterior ou registrar mudanca |

## Pipeline adaptado

### L0 - Viabilidade

Avaliar:

- ha fonte suficiente?
- o caso de uso e claro?
- o mentor sera global ou local?
- existe risco de criar caricatura?
- precisa de pesquisa externa?

Resultado:

- `viavel`;
- `viavel como draft`;
- `nao viavel agora`.

### L1 - Fontes

Registrar fontes usadas e separar:

- fonte primaria;
- fonte secundaria;
- material interno;
- inferencia da IA.

Para figura publica, preferir fonte primaria.

### L2 - Padroes comportamentais

Extrair como o alvo tende a agir, priorizar, decidir e comunicar.

Nao transformar gosto pessoal em regra universal.

### L3 - Gatilhos e transicoes de estado

Mapear como o mentor reage quando encontra:

- vagueza;
- baixo ROI;
- conflito de prioridade;
- falta de evidencia;
- risco operacional;
- oportunidade clara.

### L4 - Modelos mentais

Extrair modelos, perguntas e frameworks recorrentes.

Formato util:

| Modelo | Quando usar | Pergunta que ele gera | Limite |
|---|---|---|---|

### L5 - Arquitetura cognitiva

Descrever o fluxo de raciocinio:

```text
Input -> diagnostico -> criterio -> trade-off -> recomendacao -> teste
```

### L6 - Valores

Listar valores provaveis, sempre com fonte ou inferencia marcada.

### L7 - Obsessoes

Listar temas que aparecem repetidamente e parecem orientar decisao.

### L8 - Contradicoes produtivas

Mapear tensoes uteis, como:

- simples vs sofisticado;
- crescimento vs qualidade;
- velocidade vs criterio;
- liberdade vs disciplina.

### Checkpoint humano obrigatorio

Parar depois de L6-L8 e pedir validacao humana antes de gerar mentor final.

Pergunta minima:

```text
Esses valores, obsessoes e contradicoes produtivas parecem certos para esse mentor?
O que esta errado, exagerado ou faltando?
```

### L9 - Sintese e implementacao

So depois do checkpoint, criar:

- brief do mentor;
- prompt ou skill;
- perguntas tipicas;
- anti-padroes;
- quality gate;
- exemplos de uso;
- limites.

## Output esperado

Um mentor bom deve conter:

- objetivo;
- caso de uso;
- fontes;
- limites;
- modelos mentais;
- perguntas tipicas;
- anti-padroes;
- checkpoint L6-L8;
- modo de uso;
- criterio de qualidade.

## Quality gate

Antes de marcar como pronto:

- as fontes estao registradas;
- fatos e inferencias estao separados;
- valores, obsessoes e contradicoes foram validados;
- o mentor tem limites;
- existe pelo menos um caso de teste;
- o output nao virou culto a personalidade;
- o mentor ajuda a decidir ou executar melhor.

## Onde salvar

Mentor global:

```text
07-Frameworks-and-Processes/AI-Skills-and-Mentors/Mentores/
```

Mentor local:

```text
04-Work-Winning-Sales/Projects/<Projeto>/05-Skills/
05-Clients-and-Mentoring/<Area>/05-Skills/
06-Personal-Brand/<Area>/05-Skills/
```
