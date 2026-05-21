---
source: Wave 6 execution
created_at: 2026-05-17
status: active-framework
---

# Feedback Loops and Quality Gates

## Funcao

Este framework define como feedback, metricas, falhas e revisoes de qualidade voltam para o Second Brain sem virar burocracia.

Ele responde:

> Depois que um output foi usado, entregue, publicado, apresentado ou automatizado, o que aprendemos e o que muda?

## Regra central

Feedback so merece registro estruturado quando muda pelo menos uma destas coisas:

- proxima acao;
- criterio de qualidade;
- criterio de pronto;
- decisao de prioridade;
- processo de trabalho;
- skill, prompt ou checklist;
- framework;
- oferta, promessa, posicionamento ou tese;
- regra de automacao.

Se o comentario nao muda nada, ele pode ficar fora do vault ou aparecer como observacao simples no arquivo local. Nao crie nota de feedback para cada microajuste.

## Onde registrar

Use o menor local que preserva contexto:

| Tipo de output | Local preferido |
|---|---|
| Projeto grande da Winning Sales | `04-Work-Winning-Sales/Projects/<Projeto>/04-Feedback/` |
| Mentoria ou cliente | pasta do cliente ou da mentoria |
| Post ou conteudo | pipeline de LinkedIn, quando a Wave 7 definir o fluxo |
| Framework ou skill | arquivo do framework/skill, se o padrao for reutilizavel |
| Estrategia | `00-Start-Here/Strategy-OS.md`, somente se mudar prioridade ou trade-off real |

Nao misture feedback de projeto, post, estudo e cliente em uma lista global central.

## Tipos de feedback

| Tipo | Quando usar | Exemplo |
|---|---|---|
| `quality-review` | revisao antes de entregar ou publicar | QA de template, revisao de deck, revisao de post |
| `external-feedback` | comentario de cliente, decisor, mentorado, usuario ou leitor | Rafael pediu ajuste, Marcelo travou em um conceito |
| `metric-result` | resultado observavel depois do output | post performou, automacao economizou tempo, template reduziu retrabalho |
| `failure-learning` | algo quebrou, confundiu, gerou erro ou piorou output | automacao alucinou, prompt criou genericidade, processo ficou pesado |

Nao crie novos tipos antes desses ficarem insuficientes.

## Template minimo

Use este template apenas quando houver feedback importante. Ele e um ponto de partida, nao um formulario obrigatorio.

```text
---
source:
created_at: YYYY-MM-DD
status: feedback
feedback_type: quality-review | external-feedback | metric-result | failure-learning
related_output:
---

# Feedback - YYYY-MM-DD - Nome curto do output

## Fonte

- Quem ou o que gerou o feedback:
- Data:
- Link, arquivo ou contexto:

## Output avaliado

- Output:
- Onde vive:
- Estado no momento do feedback:

## O que aconteceu

- 

## Evidencias

- 

## Leitura

Fatos confirmados:

- 

Inferencias da IA:

- 

## Decisao ou proxima iteracao

- 

## Deve atualizar

- [ ] Project OS / cockpit
- [ ] Strategy OS
- [ ] Framework ou skill
- [ ] Output original
- [ ] Nada alem deste registro
```

A secao `Deve atualizar` funciona como roteador. Marque somente o que realmente muda.

## Quality gate geral de output

Antes de considerar um output importante como pronto, cheque mentalmente:

1. O output serve a um usuario, decisor ou contexto real?
2. O output ajuda alguem a decidir, executar, ensinar, vender, escrever ou aprender melhor?
3. Fonte e proveniencia estao claras quando importam?
4. Fatos, inferencias e decisoes estao separados?
5. O output nao inventa estado operacional, prazo, owner, criterio de pronto ou bloqueio?
6. Pendencias, riscos ou limites relevantes estao explicitos?
7. A proxima acao esta clara quando o output exige continuidade?
8. Existe caminho para capturar feedback se o output for usado, publicado, apresentado ou automatizado?

Para output pequeno, nao preencha nada. Use como checklist mental.

## Quality gate de automacao

Antes de automatizar ou aumentar autonomia de IA, responda:

1. Qual parte do output nao pode perder qualidade?
2. Onde julgamento humano realmente agrega?
3. O input e o output sao estaveis o suficiente?
4. O erro e detectavel?
5. A acao e reversivel?
6. Existe checkpoint humano para decisao sensivel?
7. Existe fallback manual?
8. Existe uma metrica ou evidencia simples para saber se piorou?
9. Alguem vai manter isso quando quebrar ou mudar?

## Regra de automacao

- Mantenha humano ou assistido quando houver alto julgamento, baixo volume, criterio ambiguo ou risco alto.
- Use workflow quando o caminho for previsivel, repetitivo e verificavel.
- Use agent quando o caminho for imprevisivel, mas existir feedback verificavel, condicao de parada e custo de erro aceitavel.
- Nao automatize quando nao houver forma clara de perceber queda de qualidade.

## Regra de propagacao

Feedback nao deve atualizar tudo por reflexo.

### Atualize Strategy OS somente se

- mudar prioridade real;
- mudar fonte de renda, oferta, tese ou trade-off;
- revelar risco estrategico relevante;
- alterar criterio de foco dos proximos 30-90 dias;
- mostrar que uma frente ativa deve subir, descer, pausar ou arquivar.

Nao atualize Strategy OS por comentario isolado, metrica pequena de post, melhoria pontual de template ou feedback que muda apenas um projeto.

### Atualize Project OS quando

- mudar estado atual;
- mudar proxima acao;
- mudar criterio de pronto;
- surgir bloqueio real;
- houver feedback de decisor, cliente, usuario ou QA;
- uma iteracao nova for decidida.

### Atualize framework ou skill quando

- o mesmo padrao aparecer em 2 ou 3 casos;
- uma falha mostrar que o checklist estava incompleto;
- uma regra nova melhorar output de forma reutilizavel;
- uma skill local provar valor fora do projeto original.

### Mantenha so no feedback quando

- o aprendizado e local;
- a evidencia ainda e fraca;
- nao existe decisao nova;
- o comentario e util como historico, mas nao muda processo.

## O que evitar

- criar pasta global de feedback;
- criar dashboard antes de uso real;
- preencher metricas sem decisao associada;
- backfillar historico antigo;
- transformar quality gate em formulario longo;
- atualizar Strategy OS com feedback local;
- criar skill global de revisao antes do checklist provar uso real.

## Links relacionados

- [[07-Frameworks-and-Processes/Second-Brain-System/Project-OS-Template|Project OS Template]]
- [[07-Frameworks-and-Processes/04-Work-Winning-Sales/Assistida-Workflow-Agent|Assistida, Workflow e Agent]]
- [[07-Frameworks-and-Processes/04-Work-Winning-Sales/Processo-de-Automatizar-Processos-PDCA|Processo de Automatizar Processos - PDCA]]
- [[07-Frameworks-and-Processes/AI-Skills-and-Mentors/Politica-de-Skills-e-Mentores|Politica de Skills e Mentores]]
