---
name: criar-post-linkedin-thiago
description: Captura ideias, transforma ideias brutas em posts de LinkedIn na voz de Thiago, revisa rascunhos existentes e cria briefs visuais leves. Use quando o pedido envolver "capturar ideia", "transforma essa ideia em post", "promover ideia para post", "revisar post", "criar brief visual", "LinkedIn na minha voz", hooks, CTA, PREVIEW.md, POST.md, IDEIA.md ou visual/brief.md dentro do Content OS de LinkedIn de Thiago.
---

# Criar Post LinkedIn Thiago

## Funcao

Operar o fluxo leve de conteudo LinkedIn de Thiago sem recriar squad, calendario, CCC ou automacao pesada.

A skill transforma material bruto em artefatos pequenos e verificaveis dentro de `06-Personal-Brand/Linkedin/`, preservando a voz original e criando versoes sugeridas separadas.

## Regra Central

Preservar o original sempre.

Nunca substituir texto cru, frase viva, storytelling pessoal, hook imperfeito ou tese em construcao por uma versao polida. Melhorias entram em secoes separadas, especialmente `Diagnostico`, `Versao sugerida` e `O que mudou`.

## Roteamento Rapido

Escolher o modo pelo pedido e pelo artefato de entrada:

| Sinal de entrada | Modo |
|---|---|
| Ideia solta, texto colado, anotacao rapida | `capturar-ideia` |
| `Ideias-Brutas/<slug>/IDEIA.md` ou ideia ja organizada | `promover-ideia-para-post` |
| `Posts/<slug>/POST.md` ou rascunho de post existente | `revisar-post` |
| Pedido de capa, carrossel, infografico ou visual | `criar-brief-visual` |

Se o pedido combinar modos, executar o menor proximo passo que gera valor. Exemplo: ideia solta + "vira post" pode capturar primeiro e, se a tese estiver clara, promover na mesma execucao.

## Fluxo Obrigatorio

1. Ler as fontes do projeto conforme `references/fontes.md`.
2. Escolher o modo e carregar apenas a referencia necessaria em `references/modos.md`.
3. Usar os templates de `references/templates.md` para criar ou atualizar arquivos.
4. Aplicar `references/quality-gate.md` antes de chamar um post de pronto.
5. Usar `references/story-check.md` apenas quando a ideia pedir historia pessoal real.

## Baixo Atrito

Perguntar a Thiago apenas quando faltar uma decisao real:

- qual ideia deve virar post agora;
- se uma frase forte pode ou deve ser suavizada;
- se um claim externo deve ser pesquisado;
- se o formato deve ser texto, capa ou carrossel;
- se uma historia pessoal esta sensivel demais para publicar.

Quando a decisao puder ser inferida com seguranca, seguir e registrar a escolha em `Decisoes Pendentes` ou `Status`.

## Nao Fazer

- Nao criar squad.
- Nao criar calendario editorial ou planejamento mensal.
- Nao criar `Posts-Publicados` por padrao.
- Nao registrar publicacao/agendamento se Thiago nao pedir.
- Nao depender de Supabase, CCC, UI, rotina agendada ou automacao externa.
- Nao gerar HTML, PNG, PDF ou carrossel final nesta V1.
- Nao usar `linkedin-writer.skill` cru.
- Nao gerar 10 outcomes ou 10 hooks por padrao.
- Nao pesquisar claims externos sem necessidade.
- Nao transformar voz de Thiago em copy de consultoria generica.

## Saidas Padrao

- Ideia capturada: `06-Personal-Brand/Linkedin/Ideias-Brutas/<slug>/IDEIA.md` ou `00-Captura-Rapida.md`.
- Post promovido: `06-Personal-Brand/Linkedin/Posts/<slug>/POST.md` e `PREVIEW.md`.
- Brief visual: `06-Personal-Brand/Linkedin/Posts/<slug>/visual/brief.md`.

## Quando Evoluir Para Squad

Manter esta skill como fonte operacional enquanto o trabalho for Thiago + IA em fluxo editorial leve.

Considerar squad apenas quando 2 ou 3 sinais aparecerem com frequencia: processamento em lote, pesquisa externa recorrente, papeis separados, producao visual real, publicacao/comentarios/metricas no mesmo fluxo, varias pessoas usando o sistema ou muitos modos independentes dentro da skill.
