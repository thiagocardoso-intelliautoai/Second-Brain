---
created_at: 2026-05-23
status: draft-for-validation
classification: alteration-plan
project: Treinamento-Corporativo-IA-Marketing-e-Vendas
inputs:
  - rafinha-scope: 01-Inputs/Escopo-em-Producao-Google-Sheets.md
  - thiago-scope: 01-Inputs/Aprimoria do Treinamento.md
  - market-research: 02-Process/2026-05-23-Pesquisa-Mercado-Treinamento-IA-Corporativo.md
strategic-decisions:
  - replicable-product: true
  - winning-ai: demonstration-only
  - follow-up: premium-addon
  - track-model: hybrid (S1+S4 mixed, S2 marketing, S3 sales)
  - pricing-model: opcao-c-brasileira (per-engagement + biblioteca async + premium opcional)
---

# Plano de Alteração do Escopo — Versão para Validação

## Arquitetura Final Consolidada

**SKU CORE (per-engagement)** — R$ 30-80k por cliente
- 4 sessões de 1h ao vivo, cadência semanal
- Trilha híbrida: S1 e S4 mistas (toda turma), S2 marketing, S3 vendas
- Pre-work obrigatório (formulário + diagnóstico + maturity score)
- 1 exercício obrigatório por sessão com revisão na sessão seguinte
- Biblioteca async inclusa: 18 SKILL.md + vídeos curtos + templates + rubrica
- Plano de adoção 30 dias produzido em workshop S4
- Cohort fechado: 8-20 pessoas
- Sponsor formalmente engajado no fim de S4

**SKU PREMIUM (add-on opcional)** — +30-40% do CORE
- 4 semanas de acompanhamento pós-treinamento (semanas 5-8)
- 2 checkpoints quinzenais + 1 review executivo
- Relatório de impacto 30 dias com métricas antes/depois

---

## Item-a-Item por Área

### Área 1 — Formato e estrutura geral

#### ✅ MANTER
- **4 sessões** *(Rafinha)* — Pesquisa: é o mínimo viável e alinha com objetivo de replicabilidade.
- **1h por sessão** *(Rafinha)* — Conservar; está dentro da faixa de mercado (60-120 min).
- **Cadência semanal** *(Rafinha)* — Pesquisa: padrão dominante, melhor retenção que formato intensivo.
- **Estrutura conteúdo + workshop + combinados** *(Rafinha)* — Alinhado com cognitive apprenticeship.

#### 🔧 MODIFICAR
- **Balança de tempo por sessão**
  - *De:* 20-25 min conteúdo / 20-25 min workshop / 10-15 min combinados
  - *Para:* **15 min conteúdo / 30 min workshop + revisão / 10 min combinados + tarefa**
  - *Por quê:* Pesquisa contraintuição #1 — "Acima de 30% em conteúdo de aula, retorno marginal cai. Fator crítico é número de loops 'tentar + receber feedback'."

---

### Área 2 — S1: "Fundamentos" vs "Como criar skill"

#### ❌ REMOVER
- **Sessão 1: "Fundamentos + Diagnóstico"** *(Rafinha)*
- *Por quê:* Pesquisa contraintuição #2 — "Fundamentos de IA é over-engineered. Profissionais de marketing/vendas em 2025-2026 já usam ChatGPT casualmente; ROI desse módulo é baixo."

#### ➕ ADICIONAR (substituindo)
- **Sessão 1: "Como criar skill por ROI + Diagnóstico"** *(Módulo 1 do Thiago, validado pela pesquisa)*
- *Estrutura:*
  1. Introdução curta (5 min)
  2. Mapeamento dos processos da função (workshop)
  3. Escolher processo por ROI (matriz de priorização)
  4. Identificar se IA é o melhor caminho (fit check)
  5. Pesquisar soluções existentes (skills open-source, GPTs, prompts)
  6. Criar 1 skill genérica de marketing OU vendas ao vivo — aprendem o conceito de skill na prática
- *Por quê:* Pesquisa contraintuição: "Skill design como nível terminal de capability gera retenção maior que prompt engineering training." Esse vira o **metaframework** que ancora S2 e S3.

---

### Área 3 — S2 (Marketing) e S3 (Vendas)

#### ✅ MANTER
- **Trilhas separadas em S2 e S3** *(Rafinha + decisão híbrida da Fase 0)*
- **Workshop com tarefa aplicada a ativo real** *(Rafinha)*
- **Output revisado entre sessões** *(Rafinha)*

#### 🔧 MODIFICAR
- **Eixo de organização interna**
  - *De:* organização por tema (Rafinha)
  - *Para:* **organização por persona** (estrutura Thiago)
    - S2 Marketing: 1 skill âncora por persona (Gestor Marketing / Estrategista Conteúdo / Demanda-Growth)
    - S3 Vendas: 1 skill âncora por persona (Gestor Comercial / Pipeline Specialist / AE/Closer)
  - *Por quê:* Pesquisa: "Programas top operam por persona". Thiago já validou essa estrutura.
  - *Implementação:* Em 1h não cabem 3 skills por persona. Escolhe **1 skill âncora por persona, demonstra/aplica ao vivo, deixa as outras 2 da persona como exercício + biblioteca async**.

#### ➕ ADICIONAR
- **18 SKILL.md prontos na biblioteca async** *(Thiago)* — 9 vendas + 9 marketing
- *Por quê:* Pesquisa contraintuição #10 — "Skills/agentes pré-prontos são a maior alavanca de adoção pós-treinamento."
- *Implementação:* 9 skills por área = limite superior do sweet spot (5-10). Aceitável **se entregues organizados em tiers**, não tentando ensinar todas ao vivo.

---

### Área 4 — S4: "Skills, Governança e Adoção"

#### ✅ MANTER
- **Sessão 4 como posicionamento na arquitetura** *(Rafinha)*

#### 🔧 MODIFICAR
- **Estrutura interna: 80% workshop, 20% conteúdo**
  - *Bloco 1 (15 min):* Pilot review — o que funcionou, o que travou nas semanas anteriores
  - *Bloco 2 (25 min):* Plano de adoção 30 dias por pessoa — template padronizado
  - *Bloco 3 (10 min):* Governança das skills criadas — quem mantém, quem aprova, onde ficam
  - *Bloco 4 (10 min):* Rubrica de qualidade de output — critério explícito de "bom vs genérico"
  - *Bloco 5 (5 min, com sponsor presente):* Sponsor approval do plano + definição de checkpoints

#### ➕ ADICIONAR
- **Presença obrigatória do sponsor nos últimos 15 min**
- *Por quê:* Failure mode #11 (sponsor-disconnect). Sem sponsor visível aprovando, time abandona em 30-60 dias.

---

### Área 5 — Pre-work e diagnóstico

#### ✅ MANTER
- **Formulário pre-work** *(Rafinha)*
- **Output: diagnóstico de oportunidades** *(Rafinha)*

#### ➕ ADICIONAR
- **Maturity score automático (1-5)** em 5 dimensões: uso atual, stack, dados/CRM, processo de vendas, sponsor
- *Por quê:* Padrão de mercado. Cria autoridade ("método Winning") e prepara argumento comercial pra premium.

---

### Área 6 — Exercícios de campo

#### ✅ MANTER
- Mapa de workflows após S1
- Contexto mínimo após S1
- Ativo de marketing com IA após S2
- Fluxo de vendas com IA após S3

#### ❌ REMOVER
- **Canvas de Skill após S4** *(Rafinha — marcado como "recomendado")*
- *Por quê:* Redundante com plano de adoção. Canvas de Skill já é trabalho prático do Módulo 1 (S1).

#### 🔧 MODIFICAR
- **Relatório de ganho**
  - *De:* "opcional premium"
  - *Para:* **OBRIGATÓRIO no Premium** (simplificado)
- *Por quê:* Pesquisa: "Relatório de impacto é a alavanca comercial para venda de próximas fases."

---

### Área 7 — Entregáveis ao cliente

#### ✅ MANTER (5 entregáveis-base do Rafinha)
- Diagnóstico de oportunidades
- Mapa de casos de uso priorizados
- Biblioteca inicial de prompts/Skills
- Outputs reais revisados
- Plano de adoção 30 dias

#### ➕ ADICIONAR (4 entregáveis novos)
- **Maturity score** — entregue após pre-work, ancora autoridade da Winning
- **Rubrica de qualidade de output** — entregue em S4, referência permanente do time
- **Doc de governança das skills** — entregue em S4, define quem mantém/aprova/distribui
- **Relatório de impacto 30 dias** — entregue no Premium, ancora upsell

---

### Área 8 — Biblioteca async (componente NOVO)

#### ➕ ADICIONAR (todo o componente é novo)
- **18 SKILL.md prontos** *(Thiago)* — 9 por área, organizados por persona, em formato padronizado
- **Vídeos curtos (5-10 min)** por skill — gravados uma vez pela Winning, reaproveitados em todos os clientes
- **Templates baixáveis:**
  - Plano de adoção 30 dias
  - Maturity scorecard
  - Rubrica de qualidade
  - Canvas de skill (template)
- **Cheat sheet de context engineering** — alinhado com pesquisa: "context engineering > prompt engineering"

*Por quê:* Pesquisa: maior driver de adoção pós-treinamento + onde a Winning maximiza replicabilidade (investimento único, reaproveitamento N).

---

### Área 9 — Acompanhamento pós-treinamento (Premium)

#### ✅ MANTER
- **Semanas 5-8** *(Rafinha)*
- **2 checkpoints quinzenais OU 1 review executivo** *(Rafinha)*

#### 🔧 MODIFICAR
- **Status comercial**
  - *De:* "recomendado, opcional"
  - *Para:* **"Premium add-on com pricing claro: +30-40% do CORE"**
- *Por quê:* Decisão estratégica Fase 0 — produto vai premium opcional. Pricing claro fundamental.

#### ➕ ADICIONAR
- **Relatório de impacto 30 dias** com métricas antes/depois — entregável central do Premium
- **Apresentação executiva final** ao sponsor — fecha o loop e abre porta para próxima fase

---

### Área 10 — Casos de uso / Skills

#### 🔧 MODIFICAR
- **Estrutura da lista**
  - *De:* lista plana por área (Rafinha)
  - *Para:* **organização em 2 tiers:**
    - **Tier 1 (presente nas sessões ao vivo):** 6 skills âncora — 1 por persona × 3 personas × 2 áreas
    - **Tier 2 (biblioteca async, prontos pra uso):** 12 skills restantes — 2 por persona × 3 personas × 2 áreas
- *Por quê:* Pesquisa: "5-10 skills funcionais é sweet spot. >12 vira skill bloat." Tier 1 + Tier 2 = 6 ensinadas ao vivo + 12 disponíveis async. **Cliente recebe 18 skills, mas estrutura pedagógica é gradual.**

---

### Área 11 — Métricas e mensuração

#### ➕ ADICIONAR (tudo novo — gap importante)
- **4 categorias de métrica claramente definidas** *(da pesquisa)*:
  - **Uso:** % adoção, frequência semanal por usuário
  - **Qualidade:** % outputs que passam rubrica
  - **Tempo:** horas economizadas por workflow
  - **Impacto comercial:** reply rate, win rate, CPL, conversão
- **Mensuração antes/depois obrigatória**
- **Cadência:** baseline no pre-work → check em S4 → follow-up 30d (Premium)

---

### Área 12 — Estrutura comercial / pricing

#### ➕ ADICIONAR (gap crítico, tudo novo)
- **Pricing CORE:** R$ 30-80k por engagement (calibrado por tamanho e cohort)
- **Pricing PREMIUM:** +30-40% do CORE
- **Tamanho mínimo cohort:** 8 pessoas (abaixo disso margem inviável)
- **Tamanho máximo cohort:** 20 pessoas (acima disso revisão individual degrada)
- **Pré-requisitos para fechar venda:**
  - Sponsor identificado
  - Uso básico de IA já existente no time
  - Capacity declarada para piloto (pelo menos 2-4 semanas de bandwidth)

---

## Quadro Resumo por Ação

### ✅ MANTER (do Rafinha)
- 4 sessões de 1h, cadência semanal
- Pre-work com formulário
- Trilha híbrida (S1/S4 mistas, S2/S3 separadas)
- Estrutura conteúdo+workshop+combinados
- Exercícios obrigatórios entre sessões
- Workshop com tarefa aplicada a ativo real
- Output revisado entre sessões
- 5 entregáveis-base (diagnóstico, mapa, biblioteca, outputs, plano)
- Acompanhamento semanas 5-8 (formato)

### ❌ REMOVER (do Rafinha)
- S1 como "Fundamentos" (substituído)
- Canvas de Skill como exercício separado pós-S4 (redundante)

### 🔧 MODIFICAR (do Rafinha)
- S1: "Fundamentos" → "Como criar skill + diagnóstico" (Módulo 1 Thiago)
- Balança de tempo por sessão: menos conteúdo, mais workshop
- S2/S3 eixo: tema → persona
- Skills: lista genérica → 18 estruturadas + tier 1/2
- Acompanhamento pós: "opcional" → "Premium claro com pricing"
- Relatório de impacto: "opcional" → "obrigatório no Premium"

### ➕ ADICIONAR (novo)
- Maturity score automático no pre-work
- Rubrica de qualidade como entregável formal
- Doc de governança de skills como entregável
- Biblioteca async (18 SKILL.md + vídeos + templates + cheat sheet)
- Sponsor formal nos últimos 15 min de S4
- 4 categorias de métricas + mensuração antes/depois
- Pricing CORE (R$ 30-80k) + PREMIUM (+30-40%)
- Tamanho mínimo/máximo de cohort
- Pré-requisitos formais de venda
- Relatório de impacto 30d obrigatório no Premium
- Apresentação executiva final ao sponsor

---

## Onde a Winning Precisa Investir (produção dos assets)

| Asset | Esforço | Reaproveitamento | Prioridade |
|---|---|---|---|
| 18 SKILL.md (estrutura já no escopo Thiago, faltam aprovação + builds) | Médio | 100% | 🔴 ALTA |
| Vídeos curtos por skill | Médio-Alto | 100% | 🟡 MÉDIA |
| Templates (plano, rubrica, canvas, maturity scorecard) | Baixo | 100% | 🔴 ALTA |
| Formulário pre-work + maturity score automático | Baixo | 100% | 🔴 ALTA |
| Cheat sheet context engineering | Baixo | 100% | 🟢 MÉDIA |
| Slides core (S1-S4) | Médio | 80% (20% custom por cliente) | 🔴 ALTA |
| Sales kit comercial (proposta + deck + case studies) | Médio | 100% | 🔴 ALTA |
| Material de governança e rubrica | Baixo | 100% | 🔴 ALTA |

---

## Lacunas/decisões que ainda dependem do Thiago

Antes do escopo virar proposta comercial:

1. **Pricing exato dentro da faixa** (R$ 30-80k) — depende do ICP de cliente
2. **Quem produz os vídeos curtos** — Winning interno ou parceiro
3. **Plataforma da biblioteca async** — Notion? GitHub? Drive? Plataforma própria?
4. **Case study brasileiro piloto** — Pesquisa: "antes de vender em escala, ter pelo menos 1 case com números mensurados"
5. **Verificação dos números de pricing** — pesquisa rodou sem WebSearch, valores precisam confirmação primária antes de virar proposta
6. **Estratégia de venda** — direto Winning Sales? Parcerias? Inbound?

---

## Próximo passo

**Fase 5: Validação Thiago, item a item.**

Pode responder de várias formas:
- "Tudo aprovado" → passo direto pra Fase 6 (escopo final consolidado)
- "Ajustar item X" → me diz qual e o que ajustar
- "Rejeitar item X" → me diz qual e por quê, eu re-proponho
- "Tenho dúvida em X" → me explica e eu esclareço
