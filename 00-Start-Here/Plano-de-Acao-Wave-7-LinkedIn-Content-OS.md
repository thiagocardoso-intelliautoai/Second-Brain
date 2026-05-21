---
source: user request
created_at: 2026-05-17
status: executed
related_plan: 00-Start-Here/Plano-de-Aprimoramento-Second-Brain.md
---

# Plano de Acao - Wave 7 - LinkedIn Content OS

## Objetivo

Reconstruir a operacao de LinkedIn dentro do Second Brain como um pipeline simples, rapido e navegavel.

A decisao central:

> O Thiago Marketing OS deixa de ser o centro do fluxo. O Second Brain vira a fonte de captura, pensamento, escrita e organizacao. Os squads antigos viram fonte de criterios, nao sistema obrigatorio.

## Problema corrigido

O projeto externo `D:\1AWinningSales-Projetos\thiagomarketingos` tinha boas pecas:

- visual de post e texto lado a lado;
- squads de pesquisa, texto, capas, carrosseis e comentarios;
- criterio forte de hook, estrutura e qualidade.

Mas ficou pesado para o comportamento real de Thiago:

- quando surgia uma ideia, ele nao abria o sistema;
- a captura real acontecia em Notion, agora Obsidian;
- havia dependencia de UI, CCC, Supabase e automacoes antes do fluxo manual estar natural;
- algumas squads tentavam criar pautas em vez de partir das ideias vivas de Thiago.

## Decisao de desenho

Criar um Content OS local em Markdown:

```text
06-Personal-Brand/Linkedin/
  AGENTS.md
  README.md
  Pipeline-de-Conteudo.md

  Ideias-Brutas/
    README.md
    00-Captura-Rapida.md
    <slug-da-ideia>/IDEIA.md

  Posts/
    README.md
    <slug-do-post>/
      POST.md
      PREVIEW.md
      visual/brief.md

  Workflows/
    Criar-Post-a-Partir-de-Ideia.md
    Gerar-Comentarios-LinkedIn.md
    Criar-Capa.md
    Criar-Carrossel.md
    Decisoes-Squads-Antigos.md
```

## O que entra dos squads antigos

### `pesquisa-conteudo-linkedin`

Manter:

- foco em hook;
- estruturas de post;
- regra de uma ideia por post;
- quality gate de texto;
- criterio de visual sugerido.

Remover:

- pesquisa semanal como default;
- planejamento mensal;
- armazem unico;
- integracao CCC;
- persistencia em `content-command-center/data/inbox.json`;
- dependencia de Supabase/UI;
- excesso de checkpoints.

### `seed-pautas-centrais`

Nao migrar.

Motivo:

- Thiago ja captura ideias em `Ideias-Brutas`;
- gerar pauta por sistema vira overengineering;
- a prioridade agora e transformar ideias reais em posts melhores.

### `comentarios-linkedin`

Migrar como workflow manual/draft.

Manter:

- 3 variacoes de comentario;
- curadoria de sinal;
- regra de nao soar generico;
- foco em resposta real, nao "obrigado".

Remover por enquanto:

- `comments_opportunities`;
- `pending_llm`;
- routine agendada;
- Supabase;
- CCC.

### `capas-linkedin` e `carrosseis-linkedin`

Criar stubs limpos agora.

Nao fazer nesta wave:

- migrar todos os assets;
- refatorar scripts;
- melhorar visual;
- depender de UI.

## Decisoes aplicadas

- `Swipe-File` removido como area ativa porque Thiago nao usa.
- `Posts-Publicados` removido como area ativa porque publicar/agendar nao precisa virar registro.
- `Posts-Rascunhos` foi substituido por `Posts/<slug>/`.
- `Ideias-Iniciais-Notion.md` foi quebrado em ideias por pasta.
- `Notion` saiu do nome dos arquivos ativos.
- Publicacao nao sera registrada por padrao.
- Raw imports continuam como fonte/proveniencia.

## Criterio de pronto

A Wave 7 esta pronta quando:

- abrir `06-Personal-Brand/Linkedin/` mostra o fluxo real;
- ideias brutas estao em unidades navegaveis;
- o post do Segundo Cerebro esta em `Posts/segundo-cerebro/`;
- existe um workflow claro para transformar ideia em post;
- existe orientacao local para IA via `AGENTS.md`;
- os squads antigos foram destilados em decisoes, sem trazer a UI pesada;
- nenhuma area vazia inutil ficou como compromisso de manutencao.

