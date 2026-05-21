---
source: Wave 7 execution
created_at: 2026-05-17
status: decision-log
---

# Decisoes - Squads Antigos Do Thiago Marketing OS

## Contexto

Thiago tinha um sistema externo em:

`D:\1AWinningSales-Projetos\thiagomarketingos`

Ele ajudou a organizar pensamento e visual, mas ficou pesado para o uso real. A captura de ideias acontecia fora dele.

## Pesquisa E Conteudo LinkedIn

Manter:

- foco em hooks;
- estruturas de post;
- quality gate;
- sugestao de visual.

Remover:

- pesquisa semanal como default;
- benchmark de concorrentes como rotina;
- planejamento mensal;
- armazem unico;
- integracao CCC;
- persistencia em JSON/Supabase;
- checkpoints demais.

## Seed Pautas Centrais

Decisao: nao migrar.

Motivo:

Thiago ja tem ideias reais em `Ideias-Brutas`. Gerar subpauta automaticamente antes de transformar ideias reais em post e overengineering.

## Comentarios LinkedIn

Decisao: migrar como workflow manual/draft.

Manter:

- 3 variacoes;
- curadoria;
- regra de comentario especifico;
- veto a comentario generico.

Remover:

- rotina agendada;
- `pending_llm`;
- Supabase;
- CCC;
- CLI de persistencia.

## Capas E Carrosseis

Decisao: manter como workflows futuros.

Motivo:

Tem valor visual, mas a tarefa agora e deixar o pipeline de escrita leve. Migrar scripts, assets e renderizacao fica para uma wave visual especifica.

## Comparacao Com linkedin-writer.skill

Data: 2026-05-19

Decisao: nao colocar `linkedin-writer.skill` cru em producao.

Motivo:

O pacote e melhor como engenharia de skill, mas esta calibrado para Victor Baggio / Playbook Lab. Ele traz ICP, oferta, CTA, ritmo de lead magnet, uso de emojis e exemplos que nao pertencem automaticamente a voz ou estrategia de Thiago.

Manter em producao:

- `Criar-Post-a-Partir-de-Ideia.md` como workflow principal;
- preservacao do original;
- pipeline leve baseado em ideias reais;
- output dentro de `Ideias-Brutas/` e `Posts/`.

Importar como melhoria:

- outcome antes do draft;
- hooks antes da versao final;
- exemplos como bussola de ritmo;
- quality gate mais explicito.

Nao importar:

- persona de Victor;
- ICP e oferta da Playbook Lab;
- CTA padrao de comentario/conexao;
- obrigacao de 10 outcomes e 10 hooks;
- artifact fora da estrutura do Second Brain.
