# Marcelo - Roteiro da Proxima Reuniao

Status: roteiro atualizado em 2026-05-20 depois da reuniao de validacao do plano.

Fonte principal: [[05-Clients-and-Mentoring/Mentoria-IA/Marcelo/00-Diagnostico/06-Analise-Reuniao-Validacao-Plano-2026-05-20|Analise da Reuniao de Validacao do Plano - 2026-05-20]]

## Objetivo da reuniao

Criar a primeira skill de automacao assistida aplicada ao processo de proposta do Marcelo, usando uma primeira reuniao com cliente como input.

A sessao deve transformar o conceito em ativo pratico:

```text
primeira reuniao com cliente -> transcricao/resumo -> ata/diagnostico -> base de proposta
```

## Resultado esperado

Ao final da reuniao, Marcelo deve sair com:

- uma skill ou prompt operacional em rascunho para processar uma primeira reuniao com cliente;
- clareza sobre quais inputs precisa capturar antes de gerar proposta;
- um modelo minimo de saida para ata, diagnostico e base de proposta;
- criterios para revisar o output antes de enviar qualquer coisa ao cliente;
- dever de casa para testar a skill em outro caso.

## Preparacao antes da reuniao

### Thiago

- Preparar uma estrutura inicial da skill, sem fechar tudo antes da sessao.
- Criar mapa simples de diferenca entre automacao assistida, squad/copiloto e automacao recorrente.
- Preparar perguntas para mapear o processo atual de proposta do Marcelo.
- Separar uma explicacao curta sobre por que a automacao do LinkedIn fica em backlog.

### Marcelo

- Trazer uma transcricao, resumo, notas ou exemplo anonimo de primeira reuniao com cliente.
- Trazer ou descrever a estrutura de proposta que gostaria de gerar.
- Indicar quais dados de cliente nao devem entrar em IA.
- Pensar no que torna uma proposta "boa" para ele.

## Abertura sugerida

Texto-base para Thiago:

```text
Marcelo, na ultima conversa ficou claro que o valor para voce nao e aprender ferramenta solta. E pegar algo real do seu trabalho e transformar em um ativo reutilizavel.

Hoje vamos fazer isso com o processo de proposta: pegar uma primeira reuniao com cliente, extrair o que importa e transformar em uma base que voce consiga revisar e usar.
```

## Agenda sugerida

| Bloco | Tempo | Conteudo |
|---|---:|---|
| Abertura e objetivo | 5 min | Relembrar decisao da ultima reuniao e alinhar o resultado esperado |
| Mapa do processo atual | 10 min | Como Marcelo faz primeira reuniao, diagnostico e proposta hoje |
| Definicao do output | 10 min | O que precisa sair: ata, diagnostico, perguntas pendentes, base de proposta |
| Criacao da skill | 25 min | Montar contexto, inputs, etapas, formato de saida e checklist |
| Teste rapido | 10 min | Rodar com material real, anonimo ou simulado |
| Fechamento | 5 min | Definir dever de casa e criterio de pronto |

Se faltar tempo, cortar explicacao conceitual e manter a construcao da skill.

## Perguntas para mapear o processo

- Quando uma primeira reuniao com cliente termina, o que voce precisa entender para conseguir montar a proposta?
- Que informacoes sempre precisam aparecer?
- Que informacoes costumam ficar implicitas e depois viram retrabalho?
- Quais perguntas voce gostaria que a IA lembrasse de fazer ou sinalizar?
- O que separa uma proposta boa de uma proposta generica?
- Existe algum modelo de proposta que voce ja usa ou gostaria de usar?
- Quais informacoes nao podem entrar em uma IA sem anonimizar?
- O output deve virar proposta direta ou primeiro uma base para revisao humana?

## Estrutura minima da skill

A skill deve receber:

- transcricao, resumo ou notas da primeira reuniao;
- contexto breve do cliente;
- objetivo da proposta;
- restricoes e dados sensiveis;
- modelo ou criterios de proposta.

A skill deve entregar:

- resumo executivo da conversa;
- objetivos declarados pelo cliente;
- dores e sintomas;
- hipoteses de causa;
- perguntas pendentes;
- escopo preliminar;
- oportunidades de melhoria;
- riscos e pontos de validacao;
- base de proposta em formato revisavel;
- checklist do que Marcelo precisa validar antes de enviar.

## Criterios de qualidade do output

O output sera bom se:

- nao inventar informacoes que nao apareceram na reuniao;
- separar fato, inferencia, hipotese e lacuna;
- preservar linguagem importante do cliente;
- deixar claro o que ainda precisa ser confirmado;
- ajudar Marcelo a economizar tempo real;
- gerar uma base que Marcelo conseguiria transformar em proposta com pouca friccao.

## O que nao fazer nesta sessao

- Nao tentar criar uma automacao recorrente completa.
- Nao abrir o tema de agent nesta sessao.
- Nao resolver a automacao do grupo de LinkedIn.
- Nao construir analise estrategica/corporativa ainda.
- Nao prometer proposta pronta sem revisao humana.

## Fechamento da reuniao

Proximos passos sugeridos:

- Marcelo testar a skill em outro caso real ou simulado.
- Marcelo registrar o que ficou bom, generico, perigoso ou incompleto.
- Thiago revisar o output na sessao seguinte.
- Decidir se o mesmo caso deve evoluir para Squad ou se a analise estrategica/corporativa sera melhor para a proxima etapa.
