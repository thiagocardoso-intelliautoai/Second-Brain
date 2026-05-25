---
source: Google Sheet em producao + workflow de validacao 2026-05-23
created_at: 2026-05-21
status: active
stage: sheets-edited-pending-thiago-visual-review
classification: project-os
last_reviewed: 2026-05-25
source_spreadsheet_title: "Treinamento Corporativo IA Marketing e Vendas v2"
source_spreadsheet_id: "1s0mkYOf9ztp_6mwrEnIRhOh_HTdWn_tGO0KKyFs2qs0"
source_spreadsheet_url: "https://docs.google.com/spreadsheets/d/1s0mkYOf9ztp_6mwrEnIRhOh_HTdWn_tGO0KKyFs2qs0/edit"
current_output_record: "03-Outputs/Google-Sheets-v2-editado.md"
execution_log: "06-Logs/2026-05-25-Log-Execucao-Sheets.md"
pre_edit_snapshot: "06-Logs/2026-05-25-Snapshot-pre-edicao-Sheets.md"
handoff_session: "02-Process/2026-05-23-Handoff-para-Codex.md"
---

# Treinamento Corporativo IA Marketing e Vendas - Cockpit

## Estado atual confirmado

Projeto passou por **ciclo completo de validacao de escopo em 2026-05-23** em Claude Code (Cursor IDE). Workflow seguido em 6 fases:

1. Pesquisa profunda de mercado (sem WebSearch ativo na sessao, baseada em conhecimento ate jan/2026)
2. Revelacao simultanea (escopo do Thiago + pesquisa)
3. Cross-analise das 3 fontes (Rafinha + Thiago + pesquisa)
4. Plano de alteracao MANTER/REMOVER/MODIFICAR/ADICIONAR
5. Validacao item-a-item do Thiago
6. Producao de Escopo Final Consolidado + prototipo tecnico .xlsx v3

Resultado historico: a sessao gerou um escopo consolidado amplo e um caminho .xlsx v3. Esse caminho foi descartado como entregavel porque misturava escopo tecnico/pedagogico com decisoes comerciais fora do papel do Thiago.

### Boundary de escopo (CRITICO)

Thiago e **Head de Automacao e IA**, NAO decisor comercial. Decisoes de pricing, estrategia de venda, pre-requisitos comerciais, posicionamento de mercado e diferenciadores competitivos sao de **lideranca comercial / marketing**, fora deste projeto.

A sessao 2026-05-23 inicialmente entrou nessas areas (no .xlsx v3), erro de boundary que foi corrigido na versao Opcao 2 do plano de adaptacao.

### Decisoes estrategicas LOCKED em dominio de Thiago

- **Formato**: 4 sessoes x 1h x semanal (pedagogico)
- **Trilha hibrida**: S1 e S4 mistas, S2 marketing, S3 vendas (pedagogico)
- **Cohort tamanho maximo**: 20 pessoas (pedagogico — acima disso revisao individual degrada)
- **Tema da S1**: "Como criar skill por ROI + Diagnostico" (substituiu "Fundamentos")
- **Eixo de S2 e S3**: organizado por persona (3 personas por area)
- **Balança de tempo**: 15 min conteudo / 30 min workshop + revisao / 10 min combinados
- **Volume de skills**: 18 total, em tiers (6 Tier 1 ao vivo + 12 Tier 2 async)
- **S4**: 80% workshop + sponsor approval nos ultimos 15 min
- **Maturity score**: metodologia de diagnostico em 8 dimensoes
- **Rubrica de qualidade**: 4 perguntas obrigatorias por output
- **Governanca de skills**: quem mantem / aprova / armazena / distribui
- **4 categorias de metricas tecnicas**: uso, qualidade, tempo, impacto operacional

### Decisoes confirmadas pela lideranca comercial (input externo)

- Produto replicavel (vs cliente especifico)
- Winning AI = demonstracao / opcional (vs obrigatoria)
- Acompanhamento pos-treinamento = opcional / premium

### Decisoes comerciais PENDENTES (lideranca comercial decide, fora deste cockpit)

- Pricing CORE (valores)
- Pricing Premium (percentuais)
- Cohort tamanho minimo (economics)
- Pre-requisitos comerciais de fechamento
- Estrategia de venda
- Diferenciadores competitivos / posicionamento
- Naming comercial dos SKUs

### Feedback critico — resolvido nesta atualizacao

Thiago sinalizou apos receber o .xlsx v3: a versao consolidada estava **visualmente mais feia e estruturalmente muito diferente** do que o Rafinha entregou.

**Decisao tomada:** Opcao 2 — ignorar o .xlsx v3 e editar o Sheets do Rafinha in-place via plugin de Sheets do Codex. O .xlsx v3 vira referencia tecnica arquivada, nao sera apresentado ao Rafinha.

Observacao de organizacao: o `.xlsx v3` nao existe como artefato atual no Project OS. O que ficou preservado foi o script `02-Process/build_xlsx_2026-05-23.py` como referencia tecnica historica do caminho descartado.

### Atualizacao 2026-05-25 - Sheets editado in-place

Codex aplicou a Opcao 2 diretamente no Google Sheets em producao/copia, preservando a estrutura visual do Rafinha.

Resultado final no Sheets:

- 8 abas originais refinadas in-place;
- 2 abas novas marcadas `[NOVO]`;
- notes explicativas em mudancas principais com o padrao `Alterado porque: ...`;
- nenhuma aba de pricing, pre-requisitos comerciais, posicionamento competitivo ou naming de SKU foi criada;
- snapshot pre-edicao registrado em `06-Logs/2026-05-25-Snapshot-pre-edicao-Sheets.md`;
- output atual registrado em `03-Outputs/Google-Sheets-v2-editado.md`.

## Proxima acao real

**Thiago revisar visualmente o Google Sheets editado** antes de apresentar ao Rafinha.

A apresentacao final ao Rafinha deve continuar sendo o Sheets editado, NAO o .xlsx v3.

**Status da execucao em Codex:**

1. Auth/acesso do plugin de Sheets confirmado.
2. Teste de escrita em aba sandbox concluido e aba temporaria removida.
3. Edicoes aplicadas aba a aba conforme `02-Process/2026-05-23-Plano-Adaptacao-Sheets.md`.
4. Validacao tecnica por ranges concluida.
5. Pendente: revisao visual de Thiago.

## Decisores e aprovadores

- **Thiago**: owner operacional do registro no Second Brain e do escopo final
- **Rafinha**: autor da versao original (precisa ser apresentado ao Sheets editado com sensibilidade)
- **Decisor/aprovador comercial Winning**: nao confirmado
- **Sponsor/cliente piloto**: nao confirmado

## Criterio de pronto

### Concluido em 2026-05-23

- [x] Pesquisa de mercado documentada (sem citacoes verificadas em web por restricao da sessao)
- [x] Cross-analise das 3 fontes (Rafinha + Thiago + pesquisa)
- [x] Escopo Final Consolidado em markdown
- [x] Plano de adaptacao do Sheets
- [x] Prototipo tecnico .xlsx v3/script gerado como referencia historica, nao como entregavel atual
- [x] Decisoes pedagogicas/operacionais fechadas no dominio do Thiago (formato, trilha, cohort maximo, tiers de skills, rubrica, governanca)

### Concluido em 2026-05-25

- [x] Teste de escrita no Google Sheets via Codex
- [x] Snapshot pre-edicao registrado
- [x] 8 abas originais editadas in-place
- [x] 2 abas novas criadas com prefixo `[NOVO]`
- [x] Validacao tecnica final por ranges

### Pendente

- [ ] Thiago validar visualmente o Google Sheet editado
- [ ] Ajustar problemas visuais/conteudo que aparecerem na revisao de Thiago
- [ ] Apresentar ao Rafinha
- [ ] Buildar os 18 SKILL.md a partir das specs ja escritas
- [ ] Produzir templates (plano adocao, rubrica, scorecard, canvas, cheat sheet)
- [ ] Definir plataforma da biblioteca async (Notion / GitHub / Drive)
- [ ] Identificar cliente piloto disposto a publicar case com numeros
- [ ] Se lideranca comercial aprovar, apoiar com insumos tecnicos para sales kit (proposta + deck + 1-pager)
- [ ] Identidade visual aplicada (slides + templates)

## Links principais

### Cockpit e contexto

- [[04-Work-Winning-Sales/Projects/Treinamento-Corporativo-IA-Marketing-e-Vendas/00-Project-Brief|00 - Project Brief]]
- [[04-Work-Winning-Sales/Projects/Treinamento-Corporativo-IA-Marketing-e-Vendas/02-Process/2026-05-23-Handoff-para-Codex|** HANDOFF PARA CODEX (entrada principal) **]]

### Inputs

- [[04-Work-Winning-Sales/Projects/Treinamento-Corporativo-IA-Marketing-e-Vendas/01-Inputs/Escopo-em-Producao-Google-Sheets|01 - Snapshot do Sheets do Rafinha (2026-05-21)]]
- [[04-Work-Winning-Sales/Projects/Treinamento-Corporativo-IA-Marketing-e-Vendas/01-Inputs/Aprimoria do Treinamento|Aprimoria do Treinamento (escopo do Thiago com 18 skills)]]

### Process (sessao 2026-05-23)

- [[04-Work-Winning-Sales/Projects/Treinamento-Corporativo-IA-Marketing-e-Vendas/02-Process/2026-05-23-Pesquisa-Mercado-Treinamento-IA-Corporativo|Pesquisa de Mercado (12 secoes)]]
- [[04-Work-Winning-Sales/Projects/Treinamento-Corporativo-IA-Marketing-e-Vendas/02-Process/2026-05-23-Plano-de-Alteracao-Escopo|Plano de Alteracao MANTER/REMOVER/MODIFICAR/ADICIONAR]]
- [[04-Work-Winning-Sales/Projects/Treinamento-Corporativo-IA-Marketing-e-Vendas/02-Process/2026-05-23-Escopo-Final-Consolidado|** ESCOPO FINAL CONSOLIDADO (15 secoes) **]]
- [[04-Work-Winning-Sales/Projects/Treinamento-Corporativo-IA-Marketing-e-Vendas/02-Process/2026-05-23-Plano-Adaptacao-Sheets|Plano de Adaptacao do Sheets (10 abas)]]

### Outputs

- [[04-Work-Winning-Sales/Projects/Treinamento-Corporativo-IA-Marketing-e-Vendas/03-Outputs/Google-Sheets-v2-editado|Google Sheets v2 editado in-place]]

### Logs e artefatos internos

- [[04-Work-Winning-Sales/Projects/Treinamento-Corporativo-IA-Marketing-e-Vendas/06-Logs/2026-05-25-Snapshot-pre-edicao-Sheets|Snapshot pre-edicao do Sheets]]
- [[04-Work-Winning-Sales/Projects/Treinamento-Corporativo-IA-Marketing-e-Vendas/06-Logs/2026-05-25-Log-Execucao-Sheets|Log de execucao da edicao in-place]]
- `02-Process/build_xlsx_2026-05-23.py` (script Python historico do caminho .xlsx v3 descartado)

### Conhecimento adjacente

- [[04-Work-Winning-Sales/Projects/Treinamento-Corporativo-IA-Marketing-e-Vendas/Skills-para-Treinamento-de-AI-mkt-vendas/README|Hub de Skills do Treinamento]]
- [[04-Work-Winning-Sales/Projects/Treinamento-Corporativo-IA-Marketing-e-Vendas/02-Process/Arquitetura-do-Treinamento|Arquitetura inicial (Rafinha + Thiago, pre-validacao)]]

## Decisoes abertas (atualizadas em 2026-05-25)

### Bloqueando apresentacao ao Rafinha

- Validacao visual de Thiago no Google Sheets editado
- Iteracao se necessario

### Bloqueando build dos assets (apos aprovacao do Rafinha)

- Engenheiro de IA disponivel para buildar os 18 SKILL.md
- Plataforma da biblioteca async (Notion vs GitHub vs Drive vs propria) — decisao tecnica
- Quem produz os videos curtos (interno vs parceiro) — decisao operacional
- Cliente piloto que aceite publicar case com numeros mensurados

### Pendencias comerciais (FORA do escopo de Thiago, escalar para lideranca comercial)

- Pricing CORE (valores)
- Pricing Premium (percentuais)
- Cohort tamanho minimo (economics)
- Pre-requisitos comerciais de fechamento
- Estrategia de venda
- Diferenciadores competitivos / posicionamento
- Naming comercial dos SKUs
- Identidade visual aplicada (designer interno vs externo) — marketing
- Verificacao de numeros de pricing internacionais citados na pesquisa, caso sejam usados em material comercial

## O que nao fazer aqui

- **Nao apresentar nem tratar o .xlsx v3 como entregavel atual** - o output atual e o Google Sheets editado in-place
- Nao tomar decisoes de pricing, vendas, marketing ou posicionamento (fora do escopo de Thiago — sao da lideranca comercial)
- Nao apresentar edicoes ao Rafinha sem ele ver Sheets editado e Thiago ter validado visualmente antes
- Nao transformar o treinamento em aula generica de IA; tese central e implantacao pratica via skills
- Nao criar skills locais antes de ter workflow, input, output e criterio de qualidade claros
- Nao usar Winning AI como hard sell — ja decidido que e demonstracao/opcional
- Nao revisitar as decisoes LOCKED em dominio de Thiago sem motivo estrategico forte
- Nao incluir blocos de pricing, diferenciadores ou pre-requisitos comerciais no Sheets de produto — esses vao para outro espaco quando a lideranca comercial decidir
