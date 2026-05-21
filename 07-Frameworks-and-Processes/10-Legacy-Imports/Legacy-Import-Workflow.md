---
source: user_request
derived_from: User instructions for legacy import ingestion
created_at: 2026-05-16
status: distilled
---

# Legacy Import Workflow

## Objetivo

Transformar exports legados em conhecimento local, rastreavel e usavel por IA.

No caso atual, o export legado principal veio do Notion em maio/2026. Ele deve ser tratado como fonte historica, nao como sistema ativo.

## Processo

### 1. Ler a pagina

Capturar:

- titulo;
- URL ou caminho de origem;
- pagina/pasta pai, se existir;
- filhos/subpaginas, se existirem;
- conteudo;
- anexos importantes;
- data de importacao.

### 2. Classificar conteudo

Tipos:

- raw idea;
- framework;
- project note;
- LinkedIn content;
- positioning;
- reference;
- decision;
- draft;
- reusable process;
- technical documentation.

### 3. Salvar raw import

Salvar em:

`10-Legacy-Imports/<nome-do-export>/`

Preservar origem e significado.

### 4. Destilar seletivamente

Criar versao limpa somente quando houver uso.

Exemplos:

- projeto ativo;
- framework reutilizavel;
- sistema de marca pessoal;
- arquivo que IA vai ler frequentemente.

### 5. Preservar voz

Se for conteudo de LinkedIn ou posicionamento:

- original intacto;
- sugestao separada;
- sem polimento corporativo automatico.

### 6. Registrar proveniencia

Toda nota destilada deve ter:

- source;
- derived_from;
- created_at;
- status.
