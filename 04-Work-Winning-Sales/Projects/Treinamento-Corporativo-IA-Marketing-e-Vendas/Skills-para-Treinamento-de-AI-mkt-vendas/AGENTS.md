---
source: Hub de Skills do Treinamento
created_at: 2026-05-22
status: active
project: Treinamento Corporativo IA Marketing e Vendas
classification: scoped-agents-instructions
---

# Agent Instructions — Hub de Skills (Treinamento IA MKT/Vendas)

Esta pasta e o hub das Skills (formato SKILL.md do Claude Code) que vao para o treinamento corporativo de IA aplicada a marketing e vendas da Winning Sales.

## Antes de qualquer trabalho aqui

Leia, nessa ordem:

1. `../00-Project-Brief.md` — escopo do treinamento
2. `../PROJECT.md` — cockpit do projeto
3. `../02-Process/Arquitetura-do-Treinamento.md` — tese pedagogica e loops por sessao
4. `../Aprimoria do Treinamento.md` — onde cada Skill e apresentada para o aluno (nome friendly + valor por dados)
5. Este `AGENTS.md` — convencoes desta pasta
6. Regras gerais do vault: root `AGENTS.md`, `00-Start-Here/AI-READ-ME-FIRST.md`, `02-AI-Operating-System/*`

## O que vive aqui

Cada Skill que entra no treinamento ganha uma subpasta propria com nome friendly em PT-BR (nao copiar nome de repo open-source).

Estrutura padrao de cada subpasta:

```text
{Nome friendly da Skill}/
├── README.md              # Cockpit da skill: nome, valor, status, source, plano
├── PLAN.md (opcional)     # Plano de acao quando a skill entra em build com @architect
├── stories/ (opcional)    # Stories criadas pelo @sm
├── source/ (opcional)     # Clone do repo open-source de base + SKILL.md originais
└── 06-Logs/ (opcional)    # Logs de evolucao da skill
```

## Principio: nao reinventar a roda

A pesquisa fundadora (chat 2026-05-22) mostrou que ja existem dezenas de Skills open-source de qualidade no formato SKILL.md. Pra cada Skill nova:

1. **Pesquisar** se ja existe versao open-source (anthropics/skills, alirezarezvani/claude-skills, KarlRaf/gtm-starter-kit, etc.)
2. **Adaptar** a melhor encontrada para o contexto Winning Sales / cliente do treinamento
3. **Adicionar runners-up** complementares quando geram valor incremental (gap coverage ou bufar funcionalidade)
4. **Validar** com workflow real antes de virar material de treinamento

Skill construida do zero so se a pesquisa confirmar que nao ha equivalente open-source aceitavel.

## Fluxo padrao de build de uma Skill (loop AIOX)

Mesmo loop para toda Skill registrada aqui:

| # | Etapa | Agente | Output |
|---|---|---|---|
| 1 | Pesquisa e selecao da fonte open-source | `@analyst` | `01-Pesquisa-Source.md` |
| 2 | Download da source oficial | `@dev` ou manual | pasta `source/` populada |
| 3 | Plano de buff com runners-up | `@architect` | `PLAN.md` |
| 4 | Quebra em stories | `@sm` | pasta `stories/` |
| 5 | Validacao do plano e das stories | `@sm` / `@po` | gate GO/NO-GO |
| 6 | Implementacao | `@dev` | SKILL.md adaptadas |
| 7 | Quality gate | `@qa` | PASS / CONCERNS / FAIL |
| 8 | Documentar no treinamento | manual | atualizar `../README.md` e `../../Aprimoria do Treinamento.md` |

Cada subpasta de Skill registra esse loop no proprio `README.md`.

## Naming convention

- Nome de pasta = nome friendly em PT-BR, identico ao que aparece em `Aprimoria do Treinamento.md`
- Caracteres permitidos: letras com acento, espacos, `+`, `-`
- Evitar nomes de repo (`gtm-starter-kit`, etc.) — esses ficam dentro de `source/` da subpasta
- Quando referenciar a Skill em outros artefatos, usar o nome friendly entre aspas ou em links wiki

## Status reconhecidos

| Status | Significado |
|---|---|
| `registered` | Skill identificada e nomeada, build ainda nao comecado |
| `in-research` | `@analyst` pesquisando fontes |
| `source-downloaded` | Repo open-source clonado para `source/` |
| `planning` | `@architect` construindo `PLAN.md` |
| `in-stories` | `@sm` quebrando em stories |
| `validated-plan` | Plano e stories validados pelo `@sm`/`@po` |
| `in-dev` | `@dev` implementando |
| `qa-gate` | `@qa` avaliando |
| `validated` | Pronta para usar no treinamento |
| `deprecated` | Removida do treinamento |

## O que nao fazer

- Nao criar Skill antes de existir workflow, input, output e criterio de qualidade claros (regra do `PROJECT.md`)
- Nao copiar nome de repo open-source como nome da subpasta
- Nao misturar Skills de areas diferentes na mesma subpasta
- Nao avancar etapa do loop sem registro no `README.md` da Skill
- Nao executar `@devops` (git push, MCP, etc.) — autoridade exclusiva conforme `.claude/rules/agent-authority.md`
