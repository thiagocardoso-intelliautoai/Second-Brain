# AGENTS.md - Mentoria IA

Use estas instrucoes ao trabalhar em pastas de mentorados dentro de `Mentoria-IA`, especialmente para criar ou revisar contexto do cliente, sintese de diagnostico, diagnostico estruturado, oportunidades/backlog, plano da mentoria, roteiro da proxima reuniao, decisoes e proximos passos.

Este arquivo deve orientar. O fluxo principal usa duas skills:

- `criar-arquivos-de-mentoria-a-partir-da-transcricao`: transforma uma transcricao bruta de diagnostico em documentos intermediarios curados.
- `criar-plano-de-mentoria-a-partir-do-diagnostico`: transforma documentos intermediarios curados em `Plano-da-Mentoria` e ajustes da jornada.

Nao pular direto da transcricao bruta para o `Plano-da-Mentoria` quando os documentos intermediarios ainda nao existem.

## Principios Obrigatorios

- Basear conclusoes nos arquivos reais da pasta.
- Inferir a funcao dos documentos pelo conteudo, nao pelo nome.
- Priorizar documentos estruturados antes de transcricoes brutas.
- Quando o primeiro input for uma transcricao bruta, criar primeiro sintese, contexto, diagnostico, backlog, decisoes e roteiro antes do plano.
- Separar fatos, inferencias, hipoteses e lacunas.
- Nao inventar informacao ausente.
- Criar planos praticos, priorizados e orientados a autonomia.
- Evitar plano generico, teoria demais ou lista solta de temas.
- Definir uma frente principal de aplicacao, mas permitir casos praticos progressivos.
- Nao forcar um piloto fixo do comeco ao fim quando outro caso ensinar melhor a proxima etapa.

## Hierarquia de Fontes

Use esta ordem de confianca:

1. **Arquivos estruturados e curados:** sintese da reuniao, contexto do cliente, diagnostico estruturado, oportunidades/backlog, decisoes, proximos passos, roteiros, plano da mentoria e resumos organizados.
2. **Anotacoes intermediarias:** notas de reuniao, bullets soltos, mapas de ideias, rascunhos e documentos parciais.
3. **Transcricao bruta:** usar apenas para complementar, recuperar linguagem original, validar hipoteses e identificar nuances.

A transcricao nunca deve ser tratada como mais confiavel ou mais organizada do que documentos derivados dela.

## Auditoria Inicial

Antes de concluir, editar qualquer plano ou atualizar arquivos de mentorado:

- listar arquivos e subpastas relevantes;
- identificar materiais estruturados, anotacoes, transcricoes, apresentacoes e documentos auxiliares;
- abrir primeiro os documentos curados;
- abrir transcricoes depois de entender o material organizado;
- classificar cada arquivo por funcao provavel;
- notar decisoes ja tomadas, lacunas e contradicoes.
- se houver apenas transcricao bruta ou diagnostico muito incompleto, usar primeiro `criar-arquivos-de-mentoria-a-partir-da-transcricao`.

Perguntas internas obrigatorias:

- Quais fontes sao mais confiaveis aqui?
- O que aparece de forma consistente em mais de uma fonte?
- O que ja foi decidido?
- O que ainda e hipotese?
- O que esta confuso, ausente ou contraditorio?
- Qual transformacao esta mentoria precisa gerar?
- Qual frente principal deve orientar a jornada?
- Quais processos podem servir como casos praticos?

## Diagnostico, Handoff e Transformacao

Ao diagnosticar, extrair: contexto atual, objetivos declarados, dores, sintomas, causas provaveis, restricoes, oportunidades, maturidade, riscos, linguagem do mentorado e perguntas em aberto.

Classificar pontos importantes como:

- **Fato:** aparece explicitamente em uma fonte.
- **Inferencia:** conclusao razoavel a partir de varios sinais.
- **Hipotese:** possibilidade util ainda nao validada.
- **Lacuna:** informacao necessaria que nao aparece nos arquivos.

Separar tambem:

- **Sintoma:** dor ou problema descrito pelo mentorado.
- **Causa provavel:** explicacao possivel para o sintoma, ainda sujeita a validacao.
- **Decisao:** combinacao ou escolha explicitamente assumida.
- **Sugestao:** ideia mencionada que ainda nao virou compromisso.

Para criar o `Plano-da-Mentoria`, usar como insumo preferencial:

1. `01-Sintese-da-Reuniao-de-Diagnostico.md`
2. `00-Contexto-do-Cliente.md`
3. `02-Diagnostico-Estruturado.md`
4. `03-Oportunidades-e-Backlog-da-Mentoria.md`
5. `04-Decisoes-e-Proximos-Passos.md`
6. `05-Roteiro-Proxima-Reuniao.md`, se existir

Todo plano deve explicitar a transformacao central:

```text
A mentoria deve levar [mentorado] de [estado atual] para [estado desejado], por meio de [jornada/praticas], gerando [entregaveis] e aumentando [autonomia/capacidade].
```

## Frente Principal e Casos Praticos

Definir:

- **frente principal:** area, problema ou familia de processos que orienta a mentoria;
- **processos candidatos:** casos reais que podem ser usados nas sessoes;
- **primeiro caso pratico:** caso adequado para a primeira pratica;
- **regra de continuidade:** quando manter o mesmo caso e quando trocar.

Regra de decisao:

- manter o mesmo caso quando ele permitir evoluir naturalmente a complexidade;
- trocar de caso quando o atual for simples demais, complexo demais, pouco representativo ou inadequado para o proximo tipo de automacao;
- registrar a razao da troca para preservar continuidade pedagogica.

Em mentorias de IA, processos e automacao, a progressao comum e:

- caso simples para automacao assistida, skill ou prompt operacional;
- mesmo caso evoluido para squad/copiloto se houver varias responsabilidades ou criterios;
- outro caso para workflow se o primeiro nao tiver fluxo previsivel;
- agent apenas se houver variabilidade, decisao e condicao de parada claras.

## Priorizacao

Priorizar por:

1. impacto esperado;
2. urgencia;
3. dependencias;
4. facilidade de execucao;
5. clareza do diagnostico;
6. risco de sobrecarga;
7. potencial de autonomia;
8. relevancia para a transformacao desejada.

Quando houver muitas oportunidades, escolher uma frente principal para a primeira jornada e mover o restante para backlog ou ciclos futuros.

## Documentos Essenciais

| Documento | Deve conter |
|---|---|
| Sintese da Reuniao de Diagnostico | resumo, temas, fatos explicitos, linguagem do mentorado, inferencias, hipoteses, ambiguidades, perguntas abertas |
| Contexto do Cliente | contexto estavel, objetivos declarados, rotina, ferramentas, restricoes, linguagem do mentorado, lacunas |
| Diagnostico Estruturado | sintomas, causas provaveis, riscos, maturidade, gargalos, hipoteses, pontos a validar |
| Oportunidades e Backlog da Mentoria | processos candidatos, oportunidades de IA, ativos possiveis, ganhos rapidos, oportunidades futuras, fora de foco |
| Decisoes e Proximos Passos | decisoes, sugestoes, pendencias, prioridades, responsaveis, riscos, checkpoints |
| Roteiro da Proxima Reuniao | objetivo, pauta, perguntas, decisoes a validar, exercicios, materiais, proximos passos |
| Plano da Mentoria | transformacao, frente principal, casos praticos, fases, entregaveis, metricas, accountability |

Cada sessao do plano deve ter objetivo, pratica principal, entregavel, dever de casa e criterio de avancao.

Use rubrica simples quando fizer sentido: `1 - Inicial`, `3 - Funcional`, `5 - Autonomo`.

## Accountability

Toda sessao deve comecar revisando:

- o que foi executado desde a ultima conversa;
- qual evidencia foi trazida;
- o que funcionou;
- o que travou;
- qual decisao precisa ser tomada agora.

Toda sessao deve terminar com:

- uma acao principal;
- um criterio de conclusao;
- um ativo a testar ou atualizar;
- uma duvida ou risco a observar;
- decisao sobre manter ou trocar o caso pratico, quando aplicavel.

## Anti-padroes

Evitar:

- depender apenas da transcricao;
- pular a etapa de arquivos intermediarios quando so existe transcricao bruta;
- assumir nomes padronizados de arquivos;
- inventar informacao;
- tratar hipotese como fato;
- tratar sugestao como decisao;
- ignorar decisoes registradas;
- confundir diagnostico com plano;
- confundir plano com roteiro da proxima reuniao;
- criar jornada bonita, mas impossivel de executar;
- escolher varias prioridades principais;
- responder tudo com "depende";
- criar entregaveis sem acompanhamento;
- forcar um piloto fixo sem necessidade;
- evoluir skill para squad, workflow ou agent quando o processo nao justificar.
