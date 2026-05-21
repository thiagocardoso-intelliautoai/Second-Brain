---
source: user request
created_at: 2026-05-17
status: executed
related_plan: 00-Start-Here/Plano-de-Aprimoramento-Second-Brain.md
---

# Plano de Acao - Wave 6 - Feedback Loops e Quality Gates

## Objetivo da Wave 6

Fazer outputs importantes voltarem para o Second Brain como aprendizado pratico, criterio melhor e proxima iteracao.

A Wave 6 nao deve criar uma camada burocratica nova. Ela deve responder uma pergunta simples:

> Depois que algo saiu para o mundo, para um cliente, para um decisor ou para um sistema, o que aprendemos e o que muda?

## Por que esta wave e sensivel

Feedback loop mexe na memoria viva do vault. Se for mal aplicado, ele pode causar tres danos:

- poluir o Strategy OS com microfeedback que nao muda estrategia;
- transformar cada output em formulario e reduzir uso real;
- criar quality gates genericos que ninguem usa antes de entregar.

O risco principal nao e faltar estrutura. O risco e criar estrutura que parece inteligente, mas nao muda decisao, output ou comportamento.

## Estado atual do vault

O vault ja tem pecas suficientes para uma Wave 6 enxuta:

- `Strategy OS` ja registra a regra de que automacao deve preservar ou aumentar qualidade do output.
- `Project OS Template` ja tem `04-Feedback/`, mas ainda sem um padrao minimo de captura.
- `Squad Playbook de Vendas` ja tem um feedback real em `04-Feedback/2026-05-14-QA-Templates.md`.
- `Politica de Skills e Mentores` ja exige quality gate para skills.
- `Processar Transcricao e Diagnostico de Mentoria` ja tem quality gate local.
- `Assistida, Workflow e Agent` ja traz uma lente boa para decidir quando automatizar, manter humano ou usar agent.
- `Processo de Automatizar Processos - PDCA` ja traz a ideia de sustentacao depois da execucao via SDCA.

Portanto, a Wave 6 deve conectar o que existe. Nao precisa inventar um "Feedback OS" separado.

## Decisao de desenho

Criar uma camada global minima em Markdown, provavelmente:

```text
07-Frameworks-and-Processes/Second-Brain-System/Feedback-Loops-and-Quality-Gates.md
```

Esse arquivo deve conter:

- definicao curta de feedback util;
- template minimo de feedback;
- quality gate geral de output;
- quality gate especifico de automacao;
- regra de propagacao para Strategy OS, Project OS, frameworks e skills;
- criterios de quando nao registrar feedback.

Nao criar varias pastas globais, dashboards, bases, Dataview ou sistema de metricas agora.

## Definicao operacional

Feedback util e qualquer evidencia que muda pelo menos uma destas coisas:

- proxima acao;
- criterio de qualidade;
- criterio de pronto;
- decisao de prioridade;
- processo de trabalho;
- skill, prompt ou checklist;
- oferta, promessa, posicionamento ou tese;
- regra de automacao.

Se nao muda nada, pode ficar como comentario solto ou nao entrar no vault.

## Tipos de feedback

Usar apenas quatro tipos inicialmente:

| Tipo | Quando usar | Exemplo |
|---|---|---|
| `quality-review` | revisao antes de entregar ou publicar | QA de template, revisao de deck, revisao de post |
| `external-feedback` | comentario de cliente, decisor, mentorado, usuario ou leitor | Rafael pediu ajuste, Marcelo travou em um conceito |
| `metric-result` | resultado observavel depois do output | post performou, automacao economizou tempo, template reduziu retrabalho |
| `failure-learning` | algo quebrou, confundiu, gerou erro ou piorou output | automacao alucinou, prompt criou genericidade, processo ficou pesado |

Nao criar tipos demais ate esses quatro ficarem insuficientes.

## Template minimo de feedback

Template recomendado para notas dentro de `04-Feedback/` de projetos, clientes ou pipelines:

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

Regra: a secao `Deve atualizar` e um roteador, nao uma checklist obrigatoria. Marcar somente o que realmente muda.

## Quality gate geral de output

Antes de considerar um output importante como pronto, verificar:

1. O output serve a um usuario, decisor ou contexto real?
2. O output ajuda alguem a decidir, executar, ensinar, vender, escrever ou aprender melhor?
3. A fonte e a proveniencia estao claras quando importam?
4. Fatos, inferencias e decisoes nao foram misturados?
5. O output nao inventa estado operacional, prazo, owner, criterio de pronto ou bloqueio?
6. Pendencias, riscos ou limites importantes estao explicitos?
7. A proxima acao esta clara quando o output exige continuidade?
8. Existe caminho para capturar feedback se o output for usado, publicado, apresentado ou automatizado?

Se o output for pequeno, nao precisa preencher nada. A IA usa isso como checklist mental.

## Quality gate especifico de automacao

Antes de automatizar, perguntar:

1. Qual parte do output nao pode perder qualidade?
2. Onde o julgamento humano realmente agrega?
3. O input e o output sao estaveis o suficiente?
4. O erro e detectavel?
5. A acao e reversivel?
6. Existe checkpoint humano para decisao sensivel?
7. Existe fallback manual?
8. Existe uma metrica ou evidencia simples para saber se piorou?
9. Alguem vai manter isso quando quebrar ou mudar?

Regra de decisao:

- manter humano/assistido quando ha alto julgamento, baixo volume, criterio ambiguo ou risco alto;
- usar workflow quando o caminho e previsivel, repetitivo e verificavel;
- usar agent quando o caminho e imprevisivel, mas ha feedback verificavel, condicao de parada e custo de erro aceitavel;
- nao automatizar quando nao houver forma clara de perceber queda de qualidade.

## Regra de propagacao

Feedback nao deve atualizar tudo por reflexo.

### Atualizar Strategy OS somente se

- mudar prioridade real;
- mudar fonte de renda, oferta, tese ou trade-off;
- revelar risco estrategico relevante;
- alterar criterio de foco dos proximos 30-90 dias;
- mostrar que uma frente ativa deve subir, descer, pausar ou arquivar.

Nao atualizar Strategy OS por:

- comentario isolado;
- metrica pequena de post;
- melhoria pontual de template;
- feedback que muda apenas um projeto.

### Atualizar Project OS quando

- mudar estado atual;
- mudar proxima acao;
- mudar criterio de pronto;
- surgir bloqueio real;
- houver feedback de decisor, cliente, usuario ou QA;
- uma iteracao nova for decidida.

### Atualizar framework ou skill quando

- o mesmo padrao aparecer em 2 ou 3 casos;
- uma falha mostrar que o checklist estava incompleto;
- uma regra nova melhorar output de forma reutilizavel;
- uma skill local provar valor fora do projeto original.

### Manter so no feedback quando

- o aprendizado e local;
- a evidencia ainda e fraca;
- nao existe decisao nova;
- o comentario e util como historico, mas nao muda processo.

## Plano de execucao recomendado

### Fase 1 - Criar a camada global minima

Criar:

- `07-Frameworks-and-Processes/Second-Brain-System/Feedback-Loops-and-Quality-Gates.md`

Atualizar links em:

- `07-Frameworks-and-Processes/README.md`
- `00-Start-Here/MOC-Frameworks.md`

Nao criar skill ainda. Primeiro testar o framework como checklist leve.

### Fase 2 - Ajustar o Project OS Template

Atualizar apenas a secao `04-Feedback/` do `Project-OS-Template.md` para apontar para o novo framework e reforcar:

- feedback so entra quando muda decisao, criterio, proxima iteracao ou aprendizado;
- nao criar nota de feedback para cada microajuste;
- nao backfillar historico antigo sem motivo.

### Fase 3 - Pilotar no Playbook

Usar o `Squad Playbook de Vendas` como piloto porque:

- e prioridade estrategica atual;
- ja tem `04-Feedback/`;
- ja tem um QA real registrado;
- tem risco real de automacao reduzir qualidade se for mal aplicada.

Aplicacao minima:

- revisar o QA existente contra o template novo;
- se necessario, criar apenas um `04-Feedback/README.md` local com regra curta;
- nao reescrever todos os arquivos do projeto;
- nao mexer no repo externo como parte desta wave.

### Fase 4 - Deixar LinkedIn e Learning para waves proprias

Nao antecipar Wave 7, 8 ou 9.

Na Wave 6, deixar claro o padrao geral. A aplicacao em:

- posts publicados;
- metricas de LinkedIn;
- raw imports;
- learning notes;

deve acontecer nas waves correspondentes.

### Fase 5 - Registrar resultado no plano principal

Ao final da execucao real, atualizar `Plano-de-Aprimoramento-Second-Brain.md` com:

- arquivos criados;
- arquivos atualizados;
- piloto realizado ou nao;
- decisoes de desenho;
- criterio de pronto atingido;
- perguntas pendentes.

## O que nao fazer na Wave 6

- Nao criar uma pasta `Feedback OS`.
- Nao criar dashboard, Dataview, Bases ou tabela global agora.
- Nao adicionar metricas a todas as notas.
- Nao exigir feedback note para todo rascunho pequeno.
- Nao backfillar todos os outputs antigos.
- Nao atualizar Strategy OS com feedback local.
- Nao transformar quality gate em formulario longo.
- Nao criar skill global de revisao antes de testar o checklist em outputs reais.
- Nao misturar feedback de projeto, post, estudo e cliente em uma unica lista central.

## Perguntas para Thiago

Nao precisa perguntar nada antes de criar a camada global minima.

Perguntar somente antes de aplicar feedback loop a uma frente especifica se faltar contexto real, por exemplo:

```text
Qual output voce quer usar como piloto do feedback loop agora: Playbook, Marcelo, LinkedIn ou outro?

Para esse output:
- quem avaliou;
- o que foi usado ou apresentado;
- que feedback veio;
- o que deve mudar na proxima iteracao;
- isso muda so o projeto ou muda estrategia/framework tambem?
```

Se Thiago nao escolher outro piloto, usar Playbook como piloto padrao.

## Criterio de pronto da Wave 6

A Wave 6 estara pronta quando:

- existir um framework global unico e leve para feedback loops e quality gates;
- o Project OS Template apontar para esse framework;
- pelo menos um projeto ativo tiver o padrao testado sem backfill pesado;
- a regra de propagacao impedir que feedback local polua Strategy OS;
- a regra de automacao deixar claro quando manter humano, workflow ou agent;
- nenhuma pasta nova pesada tiver sido criada sem uso real;
- a proxima IA souber como registrar aprendizado sem transformar o vault em formulario.

## Resultado da execucao

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
- `00-Start-Here/Plano-de-Aprimoramento-Second-Brain.md`

Decisoes aplicadas:

- criar um framework global unico e leve;
- nao criar pasta `Feedback OS`;
- nao criar dashboard, Dataview, Bases ou tabela global;
- nao criar skill global de revisao ainda;
- usar Playbook como piloto;
- nao atualizar Strategy OS porque o QA registrado muda apenas o Project OS do Playbook.

Criterio de pronto:

- atingido.

