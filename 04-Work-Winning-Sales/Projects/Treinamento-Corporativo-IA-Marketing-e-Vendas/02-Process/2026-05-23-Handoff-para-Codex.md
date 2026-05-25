---
created_at: 2026-05-23
updated_at: 2026-05-23 (Opcao 2 + boundary de escopo)
status: handoff-ready
classification: session-handoff
project: Treinamento-Corporativo-IA-Marketing-e-Vendas
from_session: Claude Code (Cursor IDE)
to_session: Codex CLI
session_owner: Thiago
approach: Opcao 2 (editar Sheets in-place via plugin de Sheets do Codex)
---

# Handoff: Continuacao do Projeto em Codex CLI

> **Para o Codex (ou agente que pegar este projeto):** leia este arquivo PRIMEIRO. Em seguida, leia o `PROJECT.md` da raiz do projeto. So entao decida o que ler a seguir.

---

## 1. Estado da arte em uma frase

Escopo do Rafinha foi validado, refinado com pesquisa + experiencia do Thiago, e esta pronto para ser **editado in-place no Google Sheets em producao via plugin de Sheets do Codex**. O .xlsx v3 produzido em sessao anterior foi **arquivado como referencia tecnica**, NAO sera apresentado ao Rafinha.

---

## 2. Boundary critico de escopo (LER ANTES DE FAZER QUALQUER COISA)

**Thiago e Head de Automacao e IA. NAO e decisor comercial.**

Isso significa que o escopo deste projeto **NAO inclui**:

- Valores especificos de pricing (R$ X mil, percentuais de premium, etc.)
- Estrategia de venda (direto vs parcerias vs inbound)
- Pre-requisitos comerciais de fechamento de venda
- Diferenciadores competitivos / posicionamento de mercado
- Naming comercial dos SKUs

**O escopo de Thiago INCLUI:**

- Estrutura pedagogica do treinamento (sessoes, formato, cadencia, ritual)
- Design e arquitetura das skills (biblioteca, tiers, governanca)
- Metodologia de diagnostico e maturidade (formulario pre-work, scoring)
- Criterios de qualidade de output (rubrica, quality gates)
- Workflows e governanca de skills
- Mensuracao tecnica (uso, qualidade, tempo, impacto operacional — sem definir metas comerciais)

**Implicacao para o Codex:**

Se o Thiago perguntar sobre pricing, estrategia comercial, posicionamento ou diferenciadores, **NAO entrar nessa decisao**. Resposta correta: "isso e dominio da lideranca comercial / marketing, fora do nosso escopo aqui. Posso documentar como pendencia pra quem decide."

A sessao anterior gerou um .xlsx v3 que entrou em algumas dessas areas (pricing, diferenciadores) — esse foi um erro de boundary. A nova versao do plano (proximo arquivo abaixo) ja corrige.

---

## 3. Decisao estrategica da migracao: Opcao 2 (in-place edit)

Apos receber o .xlsx v3 em sessao anterior, Thiago sinalizou:

> "Como que eu vou apresentar uma parada que ta muito mais feia visualmente e totalmente diferente do que ele tinha trago para mim? Era so para eu validar e fazer umas alteracoes, parece que eu criei do zero algo 100% novo."

Tres opcoes foram avaliadas:
- **Opcao 1**: adaptar o .xlsx v3 (curativo)
- **Opcao 2**: ignorar o .xlsx e editar o Sheets do Rafinha in-place via MCP **← Thiago aprovou esta**

### Por que Opcao 2 foi escolhida

1. Bate exatamente com o objetivo original ("validar + melhorar com experiencia", nao "reconstruir")
2. Resolve o "parece que criamos do zero" na raiz (nao com curativo)
3. Rafinha ve SEU trabalho refinado, nao um arquivo estrangeiro
4. Sheets tem mecanismos nativos para isso (comentarios, modo sugestao, historico de versoes)
5. Conteudo novo (Maturity, Criterios) cabe como 2 abas explicitamente marcadas `[NOVO]`
6. Trabalho da v3 nao se perde — vira referencia tecnica interna

---

## 4. O plano de edicao do Sheets (Opcao 2)

Resumo executivo (detalhamento completo em `02-Process/2026-05-23-Plano-Adaptacao-Sheets.md`):

### Estrutura final: 10 abas (8 do Rafinha editadas in-place + 2 novas)

| # | Aba | Acao | Origem |
|---|---|---|---|
| 1 | Resumo Executivo | Editar in-place | Rafinha |
| 2 | Cronograma Projeto | Editar in-place | Rafinha |
| 3 | Sessoes Detalhadas | Editar in-place (mudanca grande dentro da estrutura) | Rafinha |
| 4 | Exercicios e Revisao | Editar in-place | Rafinha |
| 5 | Casos de Uso | Editar in-place (expande para biblioteca tieradas) | Rafinha |
| 6 | Matriz de Priorizacao | Editar in-place (refinamento leve) | Rafinha |
| 7 | Acompanhamento | Editar in-place | Rafinha |
| 8 | Fontes e Insumos | Editar in-place (adicionar fontes da pesquisa + Thiago) | Rafinha |
| 9 | **[NOVO] Maturity Score & Diagnostico** | Criar | Pesquisa + experiencia Thiago |
| 10 | **[NOVO] Criterios de Qualidade & Rubrica** | Criar | Pesquisa + experiencia Thiago |

### Itens REMOVIDOS do plano (vs .xlsx v3 anterior, fora do escopo de Thiago)

- Aba "Pricing & Estrutura Comercial" (valores, percentuais premium)
- Aba "Pre-requisitos de Venda" (sponsor, capacity como check comercial)
- Aba "Diferenciadores Competitivos" (7 pontos de posicionamento)
- "Modos de falha" como diferenciador competitivo (refeito como bloco tecnico-pedagogico em Fontes e Insumos)
- Naming comercial dos SKUs

---

## 5. Decisoes estrategicas (revisadas para refletir boundary)

### LOCKED em dominio de Thiago (Head de Automacao e IA)

| Dimensao | Decisao | Dominio |
|---|---|---|
| Formato | 4 sessoes x 1h x semanal | Pedagogico |
| Trilha | Hibrida: S1/S4 mistas, S2 marketing, S3 vendas | Pedagogico |
| Cohort tamanho maximo | 20 pessoas (acima disso revisao individual degrada) | Pedagogico |
| Tema da S1 | "Como criar skill por ROI + Diagnostico" (substituiu "Fundamentos") | Pedagogico |
| Eixo de S2 e S3 | Organizado por persona (3 personas por area) | Pedagogico |
| Balança de tempo | 15 min conteudo / 30 min workshop + revisao / 10 min combinados | Pedagogico |
| Volume de skills | 18 total, em tiers (6 Tier 1 ao vivo + 12 Tier 2 async) | Arquitetura |
| Estrutura da S4 | 80% workshop + sponsor approval nos ultimos 15 min | Pedagogico |
| Metodologia de diagnostico | Maturity score em 8 dimensoes com classificacao | Diagnostico |
| Rubrica de qualidade | 4 perguntas obrigatorias por output | Qualidade |
| Governanca de skills | Quem mantem / aprova / armazena / distribui | Arquitetura |
| 4 categorias de metricas tecnicas | Uso, qualidade, tempo, impacto operacional | Mensuracao |

### LOCKED em dominio comercial (fora do escopo de Thiago, **NAO** revisitar aqui)

| Dimensao | Status |
|---|---|
| Tipo de produto (replicavel vs cliente especifico) | Lideranca comercial confirmou: replicavel |
| Winning AI obrigatoria vs opcional | Lideranca comercial confirmou: demonstracao/opcional |
| Acompanhamento padrao vs premium | Lideranca comercial confirmou: opcional/premium |
| Pricing CORE | **Pendente, lideranca comercial decide** |
| Pricing Premium | **Pendente, lideranca comercial decide** |
| Cohort tamanho minimo | **Pendente, depende de economics — lideranca comercial decide** |
| Pre-requisitos de venda | **Pendente, lideranca comercial / vendas decide** |
| Naming dos SKUs | **Pendente, lideranca comercial / marketing decide** |

---

## 6. Status atual (snapshot 2026-05-23)

### O que foi entregue nesta sessao Claude Code

| Artefato | Local | Status |
|---|---|---|
| Pesquisa de mercado | `02-Process/2026-05-23-Pesquisa-Mercado-Treinamento-IA-Corporativo.md` | Pronta (sem WebSearch ativo na sessao, conhecimento ate jan/2026) |
| Escopo Final Consolidado | `02-Process/2026-05-23-Escopo-Final-Consolidado.md` | Pronto (referencia tecnica interna) |
| Plano de Alteracao (cross-analise) | `02-Process/2026-05-23-Plano-de-Alteracao-Escopo.md` | Pronto |
| **Plano de Adaptacao do Sheets (Opcao 2)** | `02-Process/2026-05-23-Plano-Adaptacao-Sheets.md` | **Pronto — use como entrada para edicao no Codex** |
| .xlsx v3 (descartado) | `02-Process/build_xlsx_2026-05-23.py` | O script fica como referencia historica; o .xlsx nao e artefato atual e NAO deve ser apresentado ao Rafinha |
| Script gerador do .xlsx (regeravel) | `02-Process/build_xlsx_2026-05-23.py` | Pronto |

### O que NAO foi feito (proximo passo em Codex)

- Aplicar as edicoes in-place no Google Sheets em producao
- Validar visualmente o resultado
- Apresentar ao Rafinha

---

## 7. Pendencias operacionais em Codex

### P0 — Imediato

- [ ] Auth do plugin de Sheets do Codex
- [ ] Teste de escrita em aba sandbox (verificar permissoes)
- [ ] Aplicar edicoes aba a aba conforme plano `02-Process/2026-05-23-Plano-Adaptacao-Sheets.md`
- [ ] Thiago revisa visualmente
- [ ] Iterar se necessario

### P1 — Apos validacao do Sheets

- [ ] Thiago apresenta ao Rafinha
- [ ] Colher feedback do Rafinha
- [ ] Aplicar ajustes que vierem do feedback

### P2 — Apos validacao do Rafinha

- [ ] Buildar os 18 SKILL.md (especificacao em `01-Inputs/Aprimoria do Treinamento.md`)
- [ ] Produzir templates (plano adocao, rubrica, scorecard, canvas, cheat sheet)
- [ ] Definir plataforma da biblioteca async (Notion / GitHub / Drive)
- [ ] Verificar numeros internacionais da pesquisa antes de virar material comercial

### Fora do escopo (NAO fazer, escalar para lideranca comercial)

- Definir pricing
- Definir pre-requisitos comerciais
- Definir estrategia de venda
- Definir diferenciadores competitivos

---

## 8. Caveats e gotchas

### Sobre o Sheets em producao

- URL: https://docs.google.com/spreadsheets/d/1s0mkYOf9ztp_6mwrEnIRhOh_HTdWn_tGO0KKyFs2qs0/edit
- Thiago confirmou: ja e uma copia, nao a original do Rafinha. Editar diretamente nao destroi a versao original.
- Captura local em `01-Inputs/Escopo-em-Producao-Google-Sheets.md` reflete o estado do trabalho do Rafinha em 2026-05-21 (sem edicoes).

### Sobre o .xlsx v3 arquivado

- Foi gerado nesta sessao mas NAO sera apresentado ao Rafinha (decisao Opcao 2)
- Permanece como referencia tecnica interna
- O script `build_xlsx_2026-05-23.py` permite regerar se necessario
- A v3 entrou em areas fora do escopo de Thiago (pricing, diferenciadores) — o plano de edicao do Sheets ja corrige isso

### Sobre a pesquisa

- A pesquisa NAO teve acesso ao WebSearch/WebFetch (negados na sessao)
- Numeros e citacoes baseados em conhecimento ate jan/2026
- URLs marcadas com `[verificar]`
- Antes de virar material comercial, ha 5 itens documentados na secao 11 da pesquisa que precisam de validacao primaria

### Sobre o feedback do Rafinha (a virar realidade futura)

- Quando Thiago apresentar, possivel que o Rafinha discorde de alguma mudanca pedagogica (ex: S1 deixar de ser "Fundamentos")
- A discussao acontece SOBRE o trabalho dele com refinamentos, nao sobre um arquivo novo
- Aprovacao item a item e mais provavel nesse formato

### Sobre boundary de papel (CRITICO)

- Thiago NAO decide pricing, vendas, marketing
- Se a discussao com Rafinha derivar para esses topicos, escalar para lideranca comercial
- O Sheets de produto/escopo NAO contem decisoes comerciais nesta versao

---

## 9. Pergunta de abertura sugerida para o Codex

> "Estou retomando o projeto Treinamento Corporativo IA Marketing e Vendas. Voce ja leu o handoff `02-Process/2026-05-23-Handoff-para-Codex.md` e o `PROJECT.md`?
>
> O plano e Opcao 2: editar o Sheets do Rafinha in-place via plugin de Sheets do Codex. O plano detalhado esta em `02-Process/2026-05-23-Plano-Adaptacao-Sheets.md`.
>
> Primeiro passo: autenticar o plugin de Sheets e testar escrita. Depois aplicamos as edicoes aba a aba. Pode comecar?"

---

## 10. Sequencia ideal de leitura para quem pega o projeto cego

1. **Este handoff** (voce esta aqui)
2. **`PROJECT.md`** (cockpit, 5 min)
3. **`02-Process/2026-05-23-Plano-Adaptacao-Sheets.md`** (o plano de execucao detalhado)
4. **`01-Inputs/Escopo-em-Producao-Google-Sheets.md`** (o que o Rafinha tem hoje no Sheets)
5. **`01-Inputs/Aprimoria do Treinamento.md`** (o que o Thiago trouxe com 18 skills detalhadas)

Se precisar de profundidade adicional para tomar decisoes:

6. **`02-Process/2026-05-23-Escopo-Final-Consolidado.md`** (referencia tecnica completa, mas contem itens fora do escopo de Thiago — desconsiderar pricing/diferenciadores)
7. **`02-Process/2026-05-23-Plano-de-Alteracao-Escopo.md`** (cross-analise tecnica)
8. **`02-Process/2026-05-23-Pesquisa-Mercado-Treinamento-IA-Corporativo.md`** (pesquisa de mercado)

---

## 11. Resumo em uma linha

> Opcao 2 aprovada: editar Sheets do Rafinha in-place via plugin de Sheets do Codex, 8 abas refinadas + 2 abas novas marcadas [NOVO] (Maturity + Criterios). Pricing, vendas e diferenciadores ficam FORA — sao lideranca comercial.
