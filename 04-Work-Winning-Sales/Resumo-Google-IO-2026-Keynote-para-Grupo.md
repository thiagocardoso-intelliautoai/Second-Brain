---
source: "YouTube transcript via tactiq.io"
source_url: "https://www.youtube.com/watch/wYSncx9zLIU"
created_at: 2026-05-19
status: shareable-summary
audience: grupo de trabalho
---

# Google I/O 2026 - O que mudou e o que vale testar

> Resumo feito a partir da transcricao do keynote. Nao e uma checagem oficial de disponibilidade, preco ou rollout por pais.

## TL;DR

O Google tentou mostrar que IA esta saindo do modo "chat que responde" e indo para o modo "agent que trabalha".

Na pratica, a pergunta nao e "qual modelo e mais inteligente?". A pergunta melhor e:

```text
O que agora a IA consegue executar sozinha, com ferramenta real, contexto, estado, aprovacao e verificacao?
```

Se nao tiver isso, provavelmente e so uma versao mais bonita do que Claude Code, Codex, ChatGPT ou Gemini ja fazem.

## O que vale olhar primeiro

| Prioridade | Coisa nova | Por que olhar | O que testar na mao |
|---|---|---|---|
| Alta | Gemini 3.5 Flash | Promessa de mais velocidade e menor custo para agentic workflows | Mesma tarefa em Gemini, Claude e Codex. Comparar tempo, qualidade e iteracoes |
| Alta | Antigravity 2.0 | Plataforma agent-first para desenvolvimento com subagents e tarefas async | Dar uma tarefa grande em repo real e ver se decompõe, implementa, testa e explica |
| Alta | Gemini Spark | Agent em background conectado a Google apps | Pedir para criar e-mail, planilha, doc ou deck usando Gmail/Drive/Calendar |
| Alta | Search gerando UI | Search pode criar widgets, simuladores e mini-apps customizados | Fazer pergunta que exige simulador, comparador, planner ou dashboard |
| Media | Search agents | Monitoramento 24/7 de temas, produtos, vagas, empresas, mercado | Pedir para acompanhar algo e avisar quando houver mudanca relevante |
| Media | Docs Live / voz | Criar e editar Docs por voz com contexto | Fazer brain dump falado e pedir documento estruturado |
| Media | Gemini Omni | Edicao multimodal, principalmente video | Editar video/imagem mantendo contexto, movimento e estilo |
| Media | Pics / Stitch / Flow | Criacao de imagem, UI, video e musica mais operacional | Gerar landing, flyer, prototipo, video ou asset de campanha |
| Baixa por enquanto | UCP / AP2 / Universal Cart | Infra para compra por agents | Testar quando houver produto real disponivel |
| Baixa por enquanto | Glasses / Android XR | Gemini no mundo fisico/celular | Testar quando houver hardware/produto acessivel |

## Por que runtime, estado, ferramenta, checkpoint e feedback importam?

Porque isso separa um agent operacional de um chat com nome bonito.

### Sem runtime

A IA so funciona enquanto voce esta conduzindo.

Exemplo:

```text
Voce pede -> ela responde -> voce copia -> voce cola -> voce pede de novo.
```

Isso e assistido. Ajuda, mas voce ainda e o motor.

### Sem estado

Ela nao sabe bem onde parou, o que ja tentou, quais decisoes tomou e o que falta.

Em tarefa longa, isso vira perda de contexto, repeticao ou erro.

### Sem ferramenta

Ela recomenda, mas nao executa.

Exemplo:

```text
"Voce deveria atualizar o CRM."
```

Com ferramenta, ela pode abrir o CRM, atualizar o campo certo, registrar nota e mostrar o que mudou.

### Sem checkpoint

Ou ela fica perigosa, ou fica travada.

Agent bom precisa saber quando pedir aprovacao:

- enviar e-mail;
- comprar algo;
- alterar CRM;
- publicar conteudo;
- mexer em arquivo importante;
- deletar ou sobrescrever informacao.

### Sem feedback verificavel

Ela pode errar com confianca.

Feedback verificavel e algo como:

- teste passou;
- planilha foi atualizada;
- e-mail ficou como draft;
- evento apareceu no calendario;
- CRM recebeu nota;
- arquivo foi criado;
- fonte foi citada;
- humano aprovou.

Sem isso, nao da para saber se o agent trabalhou ou so gerou texto convincente.

## Regra simples

```text
Assistida = humano dirige, IA ajuda.
Workflow = sistema dirige um caminho fixo.
Agent operacional = IA dirige em runtime, usa ferramentas, mantem estado, pede aprovacao e valida resultado.
```

## Comparado com Claude Code e Codex: o que e diferente?

### No coding puro, talvez nao tenha tanta novidade conceitual

Claude Code e Codex ja fazem muita coisa parecida:

- ler e editar arquivos;
- rodar comandos;
- usar ferramentas;
- trabalhar em repos;
- criar plano;
- implementar;
- rodar testes;
- usar MCP/conectores;
- ter subagents ou formas de delegacao;
- operar com aprovacao humana;
- fazer tarefas longas.

Entao, se a pergunta for:

```text
Antigravity inventou uma categoria nova de coding agent?
```

Minha leitura: provavelmente nao.

O que ele pode trazer de melhor e:

- velocidade;
- custo;
- UX;
- integracao com Google;
- qualidade da orquestracao;
- subagents mais naturais;
- melhor trabalho async;
- melhor integracao com Android/Firebase/AI Studio/Workspace.

Isso so da para saber testando lado a lado.

## Onde pode ter inovacao real

### 1. Search criando interface, nao so resposta

Isso parece mais diferente.

Exemplo mostrado:

- pergunta sobre buracos negros;
- Search cria visual interativo;
- usuario altera parametros;
- Search gera nova simulacao.

O teste certo:

```text
Pedir algo que normalmente exigiria planilha, simulador, dashboard ou mapa.
```

Se vier so texto, nao mudou muita coisa.

Se vier uma ferramenta interativa util, ai tem novidade real.

### 2. Spark como agent em background

A promessa:

- voce passa uma tarefa;
- fecha laptop ou guarda celular;
- ele continua trabalhando;
- usa Gmail, Docs, Drive, Calendar, Sheets, Slides;
- pede aprovacao quando precisa;
- entrega artefatos.

O teste certo:

```text
Crie um update semanal para o time usando meus emails, documentos e calendario da ultima semana. Gere um draft de email e uma planilha com os principais itens.
```

Sinal de melhoria real:

- achou fontes certas;
- nao inventou;
- estruturou bem;
- criou arquivos;
- pediu aprovacao antes de enviar;
- economizou tempo de verdade.

### 3. Google Workspace com voz

Docs Live mostrou criacao/edicao de documento por voz.

O teste certo:

```text
Fazer um brain dump falado, pedir para puxar contexto do Drive/Gmail e transformar em documento organizado.
```

Sinal de melhoria real:

- entende correcao natural tipo "na verdade, troca quinta por sexta";
- formata;
- cria tabela;
- puxa contexto certo;
- nao exige prompt perfeito.

### 4. Agentic commerce

UCP/AP2/Universal Cart e interessante porque nao e so "agent clicando em site".

A ideia e criar protocolo para:

- pesquisar produto;
- comparar;
- respeitar limite;
- comprar com autorizacao;
- registrar mandato;
- deixar trilha para retorno/troca.

Isso ainda parece menos testavel agora, mas e importante como direcao.

### 5. Multimodal realmente editavel

Gemini Omni, Flow, Pics e Stitch tentam transformar IA criativa em ferramenta operacional.

O teste certo:

```text
Pegar um material real e pedir edicoes especificas, mantendo estilo, movimento, contexto e objetivo.
```

Sinal de melhoria real:

- nao gera coisa aleatoria;
- preserva o que voce pediu para preservar;
- aceita iteracao;
- entrega algo editavel ou usavel.

## Roteiro de teste mao na massa

### Teste A - Coding agent lado a lado

Pegar a mesma tarefa e rodar em:

- Claude Code;
- Codex;
- Antigravity/Gemini, quando disponivel.

Prompt:

```text
Analise este repo, encontre o ponto certo para implementar [X], faca a alteracao, rode a verificacao disponivel e me entregue um resumo do que mudou.
```

Comparar:

- tempo ate plano bom;
- qualidade da implementacao;
- se rodou teste;
- se pediu permissao na hora certa;
- se explicou trade-offs;
- se quebrou algo;
- numero de iteracoes;
- custo/latencia percebidos.

### Teste B - Tarefa de processo

Prompt:

```text
Mapeie este processo, separe o que deve ser humano, workflow ou agent, e proponha uma automacao com checkpoints e criterios de sucesso.
```

Comparar:

- se entende processo;
- se nao tenta automatizar tudo;
- se identifica risco;
- se coloca checkpoint humano;
- se define feedback verificavel;
- se fala de ROI.

### Teste C - Google Workspace real

Prompt:

```text
Usando meus emails, calendario e arquivos da ultima semana, crie um resumo para o time com decisoes, pendencias e proximas acoes. Deixe um draft de email pronto, mas nao envie sem minha aprovacao.
```

Comparar:

- qualidade do contexto puxado;
- se respeita permissao;
- se cria draft;
- se separa fato de inferencia;
- se deixa claro o que precisa de aprovacao.

### Teste D - Search como mini-app

Prompt:

```text
Crie um comparador interativo entre 5 ferramentas de CRM para uma consultoria B2B pequena, considerando preco, integracao, curva de aprendizado e fit para vendas consultivas.
```

Comparar:

- veio tabela estatica ou UI interativa?
- permite alterar criterio?
- cita fontes?
- ajuda a decidir?
- da para compartilhar?

## Como saber se realmente mudou alguma coisa

Use esse filtro:

```text
1. Fez algo que antes eu precisava conduzir passo a passo?
2. Usou ferramenta real sem copy/paste manual?
3. Manteve estado em tarefa longa?
4. Pediu aprovacao nos pontos certos?
5. Entregou artefato pronto ou quase pronto?
6. Deu para verificar se acertou?
7. Economizou tempo real?
8. Foi melhor que Claude Code/Codex no mesmo teste?
```

Se nao passar nisso, e mais uma demo bonita.

Se passar, ai tem mudanca operacional real.

## Ranking pessoal do que parece mais promissor

1. Search gerando mini-apps e interfaces customizadas.
2. Spark trabalhando em background com Google Workspace.
3. Gemini 3.5 Flash para reduzir custo/latencia de workflows agenticos.
4. Antigravity 2.0 se for melhor que Claude Code/Codex em repo real.
5. Docs Live para transformar voz em documento acionavel.
6. Gemini Omni/Flow/Pics/Stitch para producao criativa mais rapida.
7. Agentic commerce como aposta de medio prazo.
8. Glasses/XR como aposta de hardware/ecossistema.

## Conclusao pratica

O que eu testaria primeiro:

```text
1. Antigravity vs Claude Code vs Codex em uma tarefa real.
2. Gemini 3.5 Flash em tarefa longa para medir velocidade/custo.
3. Spark/Workspace em criacao de artefatos com Gmail, Drive e Calendar.
4. Search generative UI para ver se vira mesmo mini-app ou se e so texto bonito.
```

O criterio e simples:

```text
Se economiza tempo, executa com ferramenta real e deixa resultado verificavel, importa.
Se so responde mais bonito, nao muda tanto.
```

