---
source: distilled from thiagomarketingos/aiox-squads/squads/comentarios-linkedin
created_at: 2026-05-17
status: draft-workflow
---

# Workflow - Gerar Comentarios LinkedIn

## Status

Draft. A automacao original ainda esta em construcao e dependia do Thiago Marketing OS, Supabase, CCC e rotina agendada.

Nesta versao, o uso e manual.

## Quando Usar

Quando Thiago colar um post de LinkedIn e pedir sugestoes de comentario.

## Entrada

- URL do post, se houver;
- texto do post;
- autor;
- contexto do que Thiago quer gerar: conversa, complemento, discordancia ou experiencia.

## Processo

1. Avaliar se vale comentar.
2. Identificar o ponto especifico do post.
3. Gerar 3 variacoes:
   - questionamento construtivo;
   - experiencia pessoal;
   - elogio especifico com perspectiva.
4. Recomendar uma variacao e justificar.

## Regras

- maximo 1 a 3 frases;
- sem "Excelente post";
- sem "Concordo plenamente";
- sem auto-promocao;
- sem convite para DM;
- sem hashtag;
- pergunta precisa sair do conteudo especifico do post;
- se o autor provavelmente responderia apenas "obrigado", o comentario esta fraco.

## Saida

```markdown
## Variacao A - Questionamento construtivo

## Variacao B - Experiencia pessoal

## Variacao C - Elogio especifico com perspectiva

## Recomendado
```

