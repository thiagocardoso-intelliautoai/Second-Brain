---
source: Wave 5 execution
created_at: 2026-05-17
status: active-skill
scope: Mentoria de IA
---

# Processar Transcricao e Diagnostico de Mentoria

## Funcao

Transformar transcricoes, notas de sessao e diagnosticos brutos de mentoria em artefatos uteis para conduzir a proxima conversa.

Esta skill serve para todas as mentorias de IA, nao apenas Marcelo.

## Quando usar

Use depois de:

- sessao de diagnostico;
- reuniao de mentoria;
- call de acompanhamento;
- bloco de notas enviado pelo mentorado;
- transcricao nova salva em `01-Transcricoes/`.

## Quando nao usar

Nao use para:

- criar consultoria done-for-you;
- prometer automacao pronta;
- inventar criterio de sucesso;
- substituir validacao com o mentorado;
- transformar material confidencial em conteudo publico.

## Inputs obrigatorios

- pasta da mentoria ou cliente;
- transcricao ou notas brutas;
- README da mentoria;
- contexto atual do cliente;
- plano ou roteiro existente, se houver;
- objetivo da proxima interacao.

## Processo

1. Preservar o raw.
   - Nao editar a transcricao original.
   - Se a origem ainda nao estiver registrada, adicionar fonte e data no arquivo processado.

2. Separar fatos, inferencias e perguntas.
   - Fato: dito explicitamente.
   - Inferencia: leitura da IA baseada em padrao.
   - Pergunta: contexto que falta.

3. Extrair material de mentoria.
   - objetivo declarado;
   - dores e bloqueios;
   - nivel atual de autonomia com IA;
   - processos reais mencionados;
   - ferramentas usadas;
   - riscos ou restricoes;
   - oportunidades de aprendizado;
   - ativos que podem ser criados durante a mentoria.

4. Decidir o tipo de output.
   - diagnostico estruturado;
   - plano da mentoria;
   - roteiro da proxima sessao;
   - decisoes e proximos passos;
   - perguntas para o mentorado;
   - skill ou framework candidato.

5. Atualizar somente o necessario.
   - Nao reescrever todo o projeto se a mudanca for pequena.
   - Nao preencher campos desconhecidos com placeholder morto.
   - Criar `Perguntas para Thiago` quando faltar contexto real.

6. Preservar o foco de mentoria.
   - Thiago orienta, ensina e cria contexto.
   - O mentorado aplica, valida e traz processo real.
   - Consultoria operacional so entra se for decisao explicita.

## Output esperado

Um processamento bom deve gerar pelo menos um destes artefatos:

- diagnostico estruturado;
- plano ou ajuste da trilha;
- roteiro da proxima sessao;
- lista de decisoes e proximos passos;
- perguntas para Thiago ou para o mentorado;
- candidato a framework anonimo.

## Template curto

```text
## Fonte

- Transcricao:
- Data:
- Sessao:

## Fatos confirmados

- 

## Inferencias da IA

- 

## Dores, objetivos e contexto

- 

## Oportunidades de mentoria

- 

## Decisoes e proximos passos

- 

## Perguntas para Thiago

- 

## Impacto nos arquivos

- Atualizar:
- Criar:
- Nao mexer:
```

## Quality gate

Antes de concluir:

- raw material foi preservado;
- fatos e inferencias estao separados;
- nenhuma promessa de consultoria foi inventada;
- a proxima sessao ficou mais clara;
- perguntas reais foram agrupadas;
- links internos foram atualizados;
- o output ajuda Thiago a conduzir melhor a mentoria.

