# System Maintenance Rules

## Principio

O sistema deve continuar simples.

Criar pasta nova so quando uma pasta existente nao resolver.

Manutencao deve acontecer por gatilho real, nao por ritual mensal obrigatorio.

## Regras

1. Raw import nunca substitui nota destilada.
2. Nota destilada sempre aponta fonte.
3. Projeto ativo deve ter um README ou nota principal.
4. Conteudo de cliente deve ficar na pasta do cliente.
5. Framework reutilizavel deve sair de projeto e ir para `07-Frameworks-and-Processes/`.
6. Preferencia nova de Thiago deve atualizar `02-AI-Operating-System/`.
7. Conteudo antigo que nao esta ativo deve ir para `99-Archive/`.
8. Nao apagar material original sem confirmacao.
9. Instrucoes locais para IA devem usar `AGENTS.md`, nao `AGENT.md` singular.
10. `AGENTS.md` local so deve mudar quando houver decisao explicita, padrao repetido ou falha concreta da instrucao atual.

## Quando fazer manutencao

Faca manutencao somente quando uma tarefa real revelar:

- Inbox acumulado que Thiago pediu para organizar;
- projeto que mudou de estado, prioridade, criterio de pronto ou proxima acao;
- nota que virou output recorrente e merece promocao;
- conteudo antigo, encerrado ou sem acao relevante;
- duplicacao que confunde a IA ou Thiago;
- instrucao local quebrada, vaga ou pesada demais;
- feedback que muda processo, quality gate, skill, framework ou Strategy OS.

Nao faca manutencao apenas porque passou um mes.

## Como decidir onde vai

Pergunta principal:

```text
Este arquivo sera usado para qual decisao ou output?
```

Se a resposta for:

- "ainda nao sei" -> `01-Inbox/`
- "entender origem de export legado" -> `10-Legacy-Imports/`
- "executar projeto da Winning Sales" -> `04-Work-Winning-Sales/Projects/`
- "executar projeto de cliente ou mentoria" -> `05-Clients-and-Mentoring/`
- "reaproveitar metodo" -> `07-Frameworks-and-Processes/`
- "produzir conteudo" -> `06-Personal-Brand/`
- "atender cliente" -> `05-Clients-and-Mentoring/`
- "estudar" -> `08-Learning/`
- "consultar fonte" -> `09-Sources-and-References/`

## Quando arquivar

Arquive ou proponha arquivar quando:

- a frente foi encerrada;
- o projeto nao esta ativo no ciclo atual;
- a nota nao orienta decisao, execucao, ensino, venda, escrita ou aprendizado;
- existe versao melhor destilada e o original ja esta preservado;
- a estrutura cria custo de manutencao maior que o ganho.

Nao arquive material original, transcricao, fonte ou rascunho de voz pessoal sem confirmacao.

## Quando promover uma nota

Promova uma nota apenas quando o destino estiver claro:

| Destino | Sinal minimo |
|---|---|
| Projeto | existe acao, output, decisor, cliente, entrega ou recorrencia |
| Framework | existe metodo reutilizavel alem de um caso isolado |
| Skill | existe input recorrente, output esperado e criterio de qualidade |
| Post | existe tese, experiencia ou frase com energia publica |
| Mentor | existe lente recorrente com fontes, limites e uso pratico |
| Fonte | o valor principal e consulta, evidencia ou repertorio |

Se o destino nao estiver claro, mantenha no Inbox ou na pasta atual e crie pergunta curta para Thiago.

## Controle de complexidade

Antes de criar pasta, template, dashboard, checklist, skill ou `AGENTS.md`, pergunte:

```text
Isso reduz retrabalho ou melhora output agora?
```

Se a resposta for "talvez", prefira arquivo simples, checklist mental ou deixar como backlog.
