---
source: Hub de Skills do Treinamento
created_at: 2026-05-22
status: context-populated
project: Treinamento Corporativo IA Marketing e Vendas
skill_name: Inteligência de Conta + Outreach Brief
skill_audience: Especialista de Demanda e Growth (Demand Gen, Performance, ABM, Campaigns, Events, Partnerships)
source_repo: https://github.com/KarlRaf/gtm-starter-kit
source_license: MIT
research_origin: chat 2026-05-22 (deep research B2B marketing skills)
---

# Skill: Inteligência de Conta + Outreach Brief

## O que faz

Pesquisa profunda de uma conta-alvo + brief de abordagem pronto pra SDR agir em minutos, ancorado num buying signal real.

## Valor gerado (dados)

- **5,2x reply rate** quando a mensagem e ancorada num buying signal especifico vs template generico (18% vs 3,43%) — *(Growthspree, ABM Execution Report, 2026)*
- **70% da jornada de compra B2B e dark funnel**: quando o lead chega sozinho, ja tem 2-3 vendors no shortlist — *(ZoomInfo, B2B Buying Signals Guide, 2026)*
- **15-20 min → 2 min por conta**: pesquisa manual vira automatica, libera 50-70h em campanhas de 200 contas — *(MarketBetter, 2026 ABM Playbook, 2026)*
- **116% ROI documentado**: caso Madison Logic + AgentSync usando inteligencia de conta pra ativar campanhas coordenadas — *(Madison Logic case study, via G2 AI in B2B Marketing, 2026)*
- **31% lift em qualification accuracy** com AI scoring sobre dados enriquecidos vs scoring basico — *(SyncGTM, B2B Sales-Marketing Alignment Playbook, 2026)*
- **Resposta em <1h converte 53%** vs 17% em 24h — speed-to-lead com inteligencia e cobertura dupla — *(Lead Response Management Study, MIT/Oldroyd, 2007 — citado em Geisheker 2026)*

## Source base (escolhida na pesquisa)

**`KarlRaf/gtm-starter-kit`** (MIT) — kit completo com 5 skills:

| Skill recomendada na pesquisa | Skill no kit | Match |
|---|---|---|
| `account-fit-filter` | `icp-scoring` | OK |
| `account-research` | `account-research` | OK |
| `hook-pitch-generator` + `brief-assembler` | `signal-to-sequence` | OK (combinadas) |
| `committee-mapper` | — | gap, virá de runner-up |
| (bonus) | `weekly-update` | extra |
| (bonus) | `setup` | extra (auto-popula context) |

Repo: <https://github.com/KarlRaf/gtm-starter-kit>

## Runners-up para buff

Skills complementares open-source identificadas pra cobrir o gap e adicionar valor:

| Runner-up | Repo | Adiciona o que |
|---|---|---|
| `committee-mapper` (abm) | [octavehq/lfgtm/abm](https://github.com/octavehq/lfgtm/tree/main/skills/abm) | Mapeamento de stakeholders 6-8 por conta com classificacao DM/Champion/Influencer/Blocker |
| `call-prep` (oficial Anthropic) | [anthropics/knowledge-work-plugins](https://github.com/anthropics/knowledge-work-plugins/tree/main/partner-built/common-room/skills/call-prep) | Brief de meeting prep com graceful degradation (parceria Anthropic + Common Room) |
| `lead-dossier` (cascade enrichment) | [ericosiu/ai-marketing-skills](https://github.com/ericosiu/ai-marketing-skills/tree/main/lead-dossier) | Waterfall de enriquecimento + cache 7d + lead pipeline completa |

## Status

`source-downloaded` — repo clonado em `D:\1A-Projetos-Pessoais\gtm-starter-kit\` (fora do vault porque o vault e git repo proprio — nested `.git` causaria conflito).

**5 SKILL.md confirmadas no clone:**
- `skills/account-research/SKILL.md`
- `skills/icp-scoring/SKILL.md`
- `skills/setup/SKILL.md`
- `skills/signal-to-sequence/SKILL.md`
- `skills/weekly-update/SKILL.md`

**Estrutura adicional do kit:**
- `context/` — context files (profile, icp-definition, signal-library, positioning, competitor-radar, personas)
- `examples/` — sample-company da Relay como referencia
- `playbooks/` — process docs human-readable
- `workflows/` — workflows human-readable
- `sync/` — scripts Python para pull de dados
- `outputs/` — onde skills produzem outputs
- `CLAUDE.md` proprio do kit
- `ARTICLE.md` — provavelmente artigo de apresentacao do kit

## Plano de execucao (Tarefa 2 — registrada)

Conforme acordado no chat 2026-05-22:

- [x] **1. Baixar a skill oficial no Claude Code** ✓ *2026-05-22*
  - Source: `KarlRaf/gtm-starter-kit` (MIT)
  - Comando executado: `git clone https://github.com/KarlRaf/gtm-starter-kit.git`
  - Localizacao: `D:\1A-Projetos-Pessoais\gtm-starter-kit\` (fora do vault)
  - 5 SKILL.md confirmadas no clone (ver secao Status acima)

- [x] **1.5 Rodar setup skill do kit para winningsales.com.br** ✓ *2026-05-22*
  - Pesquisa publica: site, LinkedIn (founders), buscas (Sales B2B, DNA, Growth Machine, cases)
  - 9 arquivos populados em `D:\1A-Projetos-Pessoais\gtm-starter-kit\`:
    - `CLAUDE.md` (context layer principal)
    - `context/profile.md`
    - `context/icp-definition.md`
    - `context/signal-library.md`
    - `context/positioning.md`
    - `context/competitor-radar.md`
    - `context/personas/founder-ceo.md`
    - `context/personas/cro-vp-sales.md`
    - `context/personas/head-of-revops.md`
  - Campos marcados `[inferred]` aguardam refinement pass (5 perguntas — pendente)

- [ ] **2. Criar plano de acao com `@architect`** (`/AIOX:agents:architect`)
  - Objetivo: buffar a skill base com os 3 runners-up listados acima
  - Especificar: onde cada runner-up encaixa, interfaces (JSON input/output), adaptacoes ao contexto Winning Sales
  - Output esperado: `PLAN.md` nesta pasta

- [ ] **3. Quebrar plano em stories com `@sm`** (`/AIOX:agents:sm`)
  - Uma story por skill atomica do GTM-starter-kit + cada runner-up integrado
  - Acceptance criteria por story
  - Output esperado: pasta `stories/` com arquivos numerados

- [ ] **4. Validar plano e stories com `@sm`** (`/AIOX:agents:sm` `*validate-story-draft`)
  - Checklist de 10 pontos (ver `.claude/rules/story-lifecycle.md`)
  - Decisao: GO (>=7) ou NO-GO com lista de fixes

- [ ] **5. `@dev` executa** (`/AIOX:agents:dev`)
  - Story-driven development
  - Update File List e checkboxes a cada conclusao
  - QA gate final por `@qa` (PASS / CONCERNS / FAIL)

- [ ] **6. Atualizar status no hub**
  - Status para `validated` em [[../README|hub README]]
  - Confirmar/ajustar valor por dados em [[../../Aprimoria do Treinamento|Aprimoria do Treinamento]]

## Decisoes tomadas

- **2026-05-22**: Clonar `gtm-starter-kit` em `D:\1A-Projetos-Pessoais\gtm-starter-kit\` (fora do vault) — motivo: vault e repo git proprio, nested `.git` causa conflito.
- **2026-05-22**: Usar kit completo (opcao A) em vez de copiar apenas `account-research/SKILL.md` — motivo: as skills compartilham context files, e `setup` auto-popula context da Winning em 15-30min.

## Decisoes abertas

- Quais context files do gtm-starter-kit precisam ser populados primeiro com dados reais da Winning Sales (`profile.md`, `icp-definition.md`, `signal-library.md`, `positioning.md`, `competitor-radar.md`, `personas/`)?
- Os 3 runners-up entram no MVP da skill ou ficam para v2 (depois de validar v1 com 1 conta real)?
- A skill final fica disponivel global (`~/.claude/skills/`) ou local ao repo clonado?
- Rodar `setup` do kit agora para auto-popular context da Winning, ou primeiro validar o plano com `@architect`?

## Links

- Hub de Skills: [[../README|Hub de Skills]]
- Project cockpit: [[../../PROJECT|PROJECT]]
- Apresentacao no treinamento: [[../../Aprimoria do Treinamento|Aprimoria do Treinamento]] (secao "AI para Marketing → Especialista de Demanda e Growth → Skill 1")
- Pesquisa profunda fundadora: chat 2026-05-22 (deep research em B2B marketing skills e decomposicao em skills atomicas)

## Convencoes

Segue [[../AGENTS|AGENTS.md]] do hub. Cumprir loop AIOX (analyst → architect → sm → dev → qa) antes de promover status para `validated`.
