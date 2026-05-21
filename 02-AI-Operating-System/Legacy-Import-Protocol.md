# Legacy Import Protocol

## Objetivo

Processar exports legados sem transformar tudo em uma gaveta nova.

No contexto atual, Notion e apenas uma fonte historica exportada. Nao e mais sistema ativo de organizacao, captura ou conversa com IA.

O processo correto e:

1. importar bruto;
2. preservar fonte;
3. classificar;
4. destilar apenas o que tem uso;
5. manter raw e distilled separados.

## Onde salvar

Raw imports:

`10-Legacy-Imports/<nome-do-export>/`

Export historico atual:

`10-Legacy-Imports/Notion-Export-2026-05/`

Notas destiladas:

- Winning Sales: `04-Work-Winning-Sales/`
- projetos da Winning Sales: `04-Work-Winning-Sales/Projects/`
- marca pessoal: `06-Personal-Brand/`
- processos: `07-Frameworks-and-Processes/`
- aprendizado: `08-Learning/`
- clientes: `05-Clients-and-Mentoring/`

## Metadados minimos

Cada raw import de Notion deve ter:

```markdown
---
source: Notion
notion_page:
notion_url:
imported_at:
status: raw
---
```

Cada nota destilada deve ter:

```markdown
---
source:
derived_from:
created_at:
status: distilled
---
```

## Classificacao

Classifique cada pagina como uma ou mais categorias:

- raw idea;
- framework;
- project note;
- LinkedIn content;
- positioning;
- reference;
- decision;
- draft;
- reusable process;
- technical documentation;
- active project;
- learning plan.

## Preservacao de voz

Se o conteudo for pessoal, LinkedIn, posicionamento ou ideia bruta:

- preservar original;
- nao corrigir estilo automaticamente;
- criar versao sugerida separada se necessario.

## Proveniencia

Toda nota destilada deve apontar para a fonte original.

Exemplo:

```markdown
Fonte: Notion > Marketing > Minha Estrategia > Fundacao
```

## Quando nao destilar

Nao destile se:

- o conteudo ainda e so link solto;
- nao existe uso claro;
- e tarefa pontual antiga;
- e muito incompleto;
- seria taxonomia por vaidade.

Melhor manter raw e esperar uso real.
