---
created_at: 2026-05-23
updated_at: 2026-05-23
status: draft-for-validation
classification: execution-plan
project: Treinamento-Corporativo-IA-Marketing-e-Vendas
source: 02-Process/2026-05-23-Escopo-Final-Consolidado.md
target: Google Sheet "Treinamento Corporativo IA Marketing e Vendas v2" (copia, nao a original do Rafinha)
target-url: https://docs.google.com/spreadsheets/d/1s0mkYOf9ztp_6mwrEnIRhOh_HTdWn_tGO0KKyFs2qs0/edit
approach: in-place-edit (Opcao 2) — preserva trabalho original do Rafinha, edita estrutura existente, adiciona apenas 2 abas claramente marcadas [NOVO]
scope-boundary: Thiago = Head de Automacao e IA. Decisoes de pricing, vendas, posicionamento comercial e diferenciadores ficam FORA do escopo deste plano.
---

# Plano de Adaptacao do Sheets (Opcao 2 — Editar in-place)

## Decisao estrategica

**Editar o Sheets do Rafinha in-place, NAO substituir por arquivo novo.**

O .xlsx v3 produzido em sessao anterior vira **referencia tecnica interna** (arquivada em `02-Process/`), nao apresentacao para o Rafinha.

O Sheets em producao (URL acima) e uma copia confirmada pelo Thiago — editar diretamente nao destroi a versao original.

## Boundary de escopo (Head de Automacao e IA)

Este plano restringe-se ao que esta no **dominio operacional de Thiago como Head de Automacao e IA**:

- Estrutura pedagogica do treinamento (sessoes, formato, cadencia, ritual)
- Design e arquitetura das skills (biblioteca, tiers, governanca)
- Metodologia de diagnostico e maturidade
- Criterios de qualidade de output
- Workflows e quality gates
- Mensuracao tecnica (uso, qualidade, tempo, impacto operacional)

**Fora deste plano** (lideranca comercial / marketing / vendas decide):

- Valores especificos de pricing
- Estrategia de venda
- Pre-requisitos comerciais de fechamento
- Diferenciadores competitivos / posicionamento
- Naming comercial dos SKUs

Quando o conteudo a editar resvalar nessas areas, fica marcado como **"aguardando lideranca comercial"** ou removido.

---

## Estrutura proposta: 8 abas editadas in-place + 2 abas novas

| # | Aba | Acao | Origem |
|---|---|---|---|
| 1 | Resumo Executivo | Editar in-place | Rafinha |
| 2 | Cronograma Projeto | Editar in-place | Rafinha |
| 3 | Sessoes Detalhadas | Editar in-place (mudanca grande mas dentro da estrutura) | Rafinha |
| 4 | Exercicios e Revisao | Editar in-place | Rafinha |
| 5 | Casos de Uso | Editar in-place (expande para biblioteca tieradas) | Rafinha |
| 6 | Matriz de Priorizacao | Editar in-place (refinamento leve) | Rafinha (alinhado com Thiago) |
| 7 | Acompanhamento | Editar in-place | Rafinha |
| 8 | Fontes e Insumos | Editar in-place (adicionar fontes da pesquisa + Thiago) | Rafinha |
| 9 | **[NOVO] Maturity Score & Diagnostico** | Criar | Pesquisa + experiencia Thiago |
| 10 | **[NOVO] Criterios de Qualidade & Rubrica** | Criar | Pesquisa + experiencia Thiago |

**Total: 10 abas** (vs 8 originais). As 2 novas sao claramente marcadas `[NOVO]` no titulo, sinalizando que sao **expansoes propostas por Thiago**, nao reescritas.

---

## Edicao aba por aba

### Aba 1 — Resumo Executivo (editar in-place)

**MANTER** (sem mexer):
- Promessa central do Rafinha ("sair de uso pontual de IA para rotinas implantadas")
- Principio pedagogico ("menos aula inspiracional, mais execucao aplicada")
- Foco em outputs reais revisados
- Lista de entregaveis-base

**AJUSTAR** (texto):
- **Publico-alvo**: incluir as 3 personas por area (Gestor / Estrategista de Conteudo / Demanda em Marketing; Gestor Comercial / Pipeline / AE em Vendas). Antes estava generico ("times de marketing, SDR/BDR..."), agora fica explicito por persona — refinamento pedagogico.
- **Entregaveis previstos**: adicionar 3 itens: maturity score, rubrica de qualidade, doc de governanca das skills.

**ADICIONAR** (linha nova):
- Bloco curto: "Estrutura pedagogica de cada sessao: ~15 min conteudo, ~30 min workshop com revisao de output ao vivo, ~10 min combinados + tarefa". Esse e refinamento da balança de tempo do Rafinha (era 20-25/20-25/10-15), justificado pedagogicamente (mais loops de tentar + receber feedback).

**NAO MEXER** (fora do escopo de Thiago):
- Qualquer mencao a pricing, posicionamento competitivo, diferenciadores comerciais

---

### Aba 2 — Cronograma Projeto (editar in-place)

**MANTER:**
- Estrutura de tabela (Macro entregavel | Semana | Duracao | Tipo | Entregavel | Responsavel cliente | Observacao)
- Semana 0 = preparacao com formulario pre-work
- Semanas 1-4 = sessoes de treinamento
- Semanas 5-8 = acompanhamento (Rafinha ja tinha)

**AJUSTAR:**
- **Sessao 1**: tema antes era "Fundamentos, mapa de ferramentas e diagnostico de workflows"; agora vira **"Como criar skill por ROI + diagnostico"**. Justificativa pedagogica: pesquisa mostra que fundamentos genericos sao over-engineered para profissionais que ja usam ChatGPT.
- **Sessao 2 (Marketing)**: especificar no campo Entregavel que serao **3 skills ancora rodadas ao vivo (1 por persona: Gestor / Estrategista / Demanda)**.
- **Sessao 3 (Vendas)**: especificar no campo Entregavel que serao **3 skills ancora rodadas ao vivo (1 por persona: Gestor / Pipeline / AE)**.
- **Sessao 4**: titulo permanece "Padronizacao em Skills e agentes". Ajustar Entregavel para incluir "plano de adocao 30 dias + sponsor approval formal nos ultimos 15 min".
- **Acompanhamento (semanas 5-8)**: atualizar Entregavel para incluir relatorio de impacto 30 dias com metricas em 4 categorias.

**NAO MEXER:**
- Se acompanhamento e "padrao" ou "opcional" — decisao comercial. Manter como Rafinha deixou ou marcar "definicao comercial".

---

### Aba 3 — Sessoes Detalhadas (editar in-place, mudanca grande)

**MANTER:**
- Estrutura de tabela (Sessao | Tema | Objetivo | Workshop em aula | Resultado esperado)
- 4 linhas (uma por sessao)

**AJUSTAR cada linha:**

**Sessao 1:**
- Tema: "Fundamentos + Diagnostico" → **"Como criar skill por ROI + Diagnostico"**
- Objetivo: ajustar para "Ensinar metaframework: identificar onde IA gera retorno real e transformar em skill operacional"
- Workshop: substituir "Matriz de tarefa repetitiva..." por "Mapeamento de processos + matriz de priorizacao por ROI + criar 1 skill generica ao vivo"
- Resultado: manter "Top 5 casos de uso priorizados"

**Sessao 2:**
- Tema: manter "Marketing AI-first"
- Objetivo: refinar para "Rodar 1 skill ancora por persona com ativo real do cliente"
- Workshop: ajustar para "Cada participante roda skill da sua persona em ativo real; consultor revisa 2-3 outputs ao vivo aplicando rubrica de qualidade"
- Resultado: manter

**Sessao 3:**
- Tema: manter "Vendas AI-first"
- Objetivo: refinar para "Rodar 1 skill ancora por persona com caso real do pipeline (deal/lead/conta)"
- Workshop: ajustar para "Cada participante usa um deal/lead/conta real do CRM; consultor revisa 2-3 ao vivo + antes/depois de tempo gasto"
- Resultado: manter

**Sessao 4:**
- Tema: manter "Skills, Governanca e Adocao"
- Objetivo: refinar para "Transformar aprendizado em rotina operacional permanente, com sponsor approval formal"
- Workshop: ajustar para "80% workshop: pilot review + plano de adocao 30 dias por pessoa + governanca + rubrica + sponsor approval (ultimos 15 min, sponsor presente)"
- Resultado: ajustar para "Plano de adocao 30 dias por pessoa + sponsor approval documentado"

---

### Aba 4 — Exercicios e Revisao (editar in-place)

**MANTER (sem mexer):**
- Mapa de workflows (apos S1)
- Contexto minimo (apos S1)
- Ativo de marketing com IA (apos S2)
- Fluxo de vendas com IA (apos S3)
- Relatorio de ganho (30 dias)

**REMOVER:**
- "Canvas de Skill" como exercicio separado apos S4. Justificativa: redundante com plano de adocao; canvas ja e trabalho pratico do Modulo 1 em S1.

**ADICIONAR (linhas novas):**
- **Plano de Adocao 30 dias (por pessoa)** — exercicio dentro da S4, obrigatorio. Output: template preenchido (skill + frequencia + workflow + metrica + checkpoint).
- **Antes/depois — baseline vs S4** — exercicio dentro da S4. Output: registro de tempo gasto e qualidade percebida por workflow piloto. Justificativa: mensuracao tecnica do impacto (dominio de automacao).

**AJUSTAR:**
- **Relatorio de ganho** — antes "opcional premium"; agora marcar como "obrigatorio quando houver acompanhamento pos-treinamento". A decisao "se acompanhamento e premium ou padrao" e comercial, mas a obrigatoriedade do relatorio quando acontece e tecnica.

---

### Aba 5 — Casos de Uso (editar in-place, expande para biblioteca tieradas)

**MANTER:**
- Estrutura de tabela existente (com colunas Caso de uso | Usuario principal | Input | Output | Skill/agente possivel | Ganho esperado | Prioridade)
- O conceito de "casos de uso" como linguagem do Rafinha
- Os casos de uso que ele ja listou (mantem se ainda fazem sentido)

**EXPANDIR (refinamento estrutural):**
- Adicionar **coluna "Persona"** entre "Caso de uso" e "Usuario principal"
- Adicionar **coluna "Tier"** (Tier 1 = ao vivo na sessao / Tier 2 = somente biblioteca async)
- Adicionar **coluna "Status do SKILL.md"** (A produzir / Em build / Pronto / Revisar)

**ADICIONAR (linhas):**
- Expandir para os 18 casos de uso/skills detalhados, organizados por area e persona:
  - **Marketing** (9 skills, 3 personas): Gestor Marketing, Estrategista de Conteudo, Demanda/Growth
  - **Vendas** (9 skills, 3 personas): Gestor Comercial, Pipeline Specialist, AE/Closer
- Marcar 6 como **Tier 1** (1 por persona, rodadas ao vivo nas sessoes 2 e 3)
- Marcar 12 como **Tier 2** (somente biblioteca async)

**Justificativa de manter linguagem "casos de uso":** o Rafinha usou esse termo. Skills sao a forma TECNICA de operacionalizar os casos de uso. Manter o framing dele preserva continuidade.

---

### Aba 6 — Matriz de Priorizacao (editar in-place, refinamento leve)

**MANTER:**
- Estrutura geral da matriz como Rafinha desenhou
- Os criterios que ele ja tinha

**AJUSTAR (refinamento):**
- Tornar os criterios explicitos com pesos: Frequencia (alto), Tempo gasto por execucao (alto), Dados disponiveis (medio), Clareza do output esperado (medio), Risco se errar (baixo)
- Pergunta-chave por criterio (ex: "Quantas vezes por semana esse workflow roda?" para Frequencia)

**Justificativa:** essa aba ja esta alinhada com o que Thiago propos no Modulo 1 (priorizacao por ROI). Refinamento leve de explicitar pesos e perguntas-chave melhora usabilidade pedagogica.

---

### Aba 7 — Acompanhamento (editar in-place)

**MANTER:**
- Estrutura da aba
- Conteudo principal sobre semanas 5-8
- Mencao a 2 checkpoints quinzenais ou 1 review executivo

**AJUSTAR:**
- Detalhar **conteudo de cada checkpoint** (semana 5: pilot review + desbloqueio; semana 7: metricas parciais + expansao; semana 8: review executivo com sponsor)
- Adicionar **relatorio de impacto 30 dias** como entregavel central
- Adicionar **4 categorias de metricas** documentadas:
  - Uso: % participantes ativos em 30d, frequencia por workflow
  - Qualidade: % outputs que passam a rubrica
  - Tempo: horas economizadas por workflow
  - Impacto comercial: reply rate, win rate, CPL, conversao (a definir com cliente)

**NAO MEXER:**
- "Opcional vs padrao" — decisao comercial. Manter como Rafinha deixou ou marcar para definicao comercial.

---

### Aba 8 — Fontes e Insumos (editar in-place)

**MANTER:**
- Estrutura existente
- Fontes que o Rafinha ja tinha

**ADICIONAR (referencias da pesquisa de mercado da sessao 2026-05-23):**
- Adult learning research: 70-20-10 (Lombardo & Eichinger), Cognitive Apprenticeship (Collins, Brown, Holum), Kirkpatrick four-level, Bloom's Taxonomy revisada, Andragogy (Knowles)
- Benchmarks de programas de IA corporativa: McKinsey QuantumBlack Academy, BCG AI Academy, Section.school (AI for Marketers), Reforge (AI for Growth), Wharton Exec Ed
- HubSpot State of Sales, Salesforce State of Sales (referencias usadas nas skills do Thiago)

**ADICIONAR (referencias do escopo do Thiago — GitHub e open-source):**
- gtmagents/gtm-agents
- gooseworks-ai/goose-skills
- vercel-labs/lead-agent
- brightdata/ai-lead-generator
- github/awesome-copilot (gtm-positioning-strategy)
- coreyhaines31/marketingskills
- guilhermemarketing/esc-skills
- realjaymes/marketingagentskills
- OpenClaudia/openclaudia-skills

**ADICIONAR (bloco "Modos de falha pedagogicos a mitigar no design"):**
- Demo theatre (impressionar sem implantar) — mitigado por: 50%+ tempo em workshop com output real do aluno
- ChatGPT 101 (generico demais) — mitigado por: S1 e "Como criar skill", nao fundamentos
- One-and-done (sem follow-up) — mitigado por: plano de adocao + acompanhamento
- Tool zoo — mitigado por: cada skill = 1 workflow, 1 output, 1 criterio
- No context engineering — mitigado por: cheat sheet + workshops com contexto real
- Ungated assignments — mitigado por: toda tarefa revisada na sessao seguinte
- Skill bloat — mitigado por: tier 1 (6 ao vivo) + tier 2 (12 async)
- Sponsor disconnect — mitigado por: sponsor approval formal em S4

(Essa lista e tecnica/pedagogica, dominio de Thiago. NAO confundir com "diferenciadores competitivos" — esses sao do marketing/comercial.)

---

### Aba 9 — [NOVO] Maturity Score & Diagnostico

**Justificativa para criar nova aba:** metodologia de diagnostico nao existia no escopo do Rafinha. E parte essencial do design pedagogico (diagnostico precede pedagogia). Dominio de Thiago como Head de Automacao e IA.

**Conteudo:**

**Bloco 1 — Formulario Pre-work (8 dimensoes):**
- Uso atual de IA (frequencia no time)
- Stack tecnologico (ferramentas existentes)
- CRM e dados (qualidade, integracoes)
- Processo de vendas (metodologia explicita)
- Marketing ops (attribution, scoring, automation)
- Sponsor e lideranca (engajamento)
- Apetite de mudanca (cultura)
- Capacity (bandwidth disponivel)

Cada dimensao com escala 1-5 e descricao do que e 1 vs 5.

**Bloco 2 — Classificacao do Score:**
- 1.0-2.0: Inicial
- 2.1-3.0: Em desenvolvimento
- 3.1-4.0: Definido
- 4.1-5.0: Gerenciado/Otimizado

**Bloco 3 — Output entregue 48h antes da S1:**
- Maturity score (medio + por dimensao)
- Mapa de oportunidades preliminar
- Recomendacao de priorizacao por area

---

### Aba 10 — [NOVO] Criterios de Qualidade & Rubrica

**Justificativa para criar nova aba:** rubrica de qualidade de output era apontada na pesquisa como "habilidade critica subensinada". Definir criterios de qualidade tecnica e responsabilidade direta do Head de Automacao e IA.

**Conteudo:**

**Bloco 1 — Rubrica de Qualidade de Output (4 perguntas que todo output produzido em workshop precisa passar):**
- Usa contexto real do negocio? (vs invencoes genericas)
- Tem proximo passo claro? (acionavel)
- Nao inventa dado? (separa fato, inferencia, hipotese)
- E revisavel em 2 min? (estruturado)

**Bloco 2 — Quality Gates por Skill (para o engenheiro de IA buildar):**
- Cita evidencia usada
- Separa fato/inferencia/recomendacao
- Termina com owner, proximo passo, metrica impactada
- Sinaliza lacunas em vez de inventar

**Bloco 3 — Governanca das Skills criadas:**
- Quem mantem (papel responsavel)
- Quem aprova mudancas (vendedor pode editar ou so gestor?)
- Onde ficam armazenadas
- Como time descobre que skill nova foi criada

**Bloco 4 — Templates relacionados (a produzir):**
- Plano de Adocao 30 dias
- Maturity Scorecard (formulario pre-work)
- Rubrica de Qualidade
- Canvas de Skill
- Cheat sheet de Context Engineering

---

## Itens REMOVIDOS deste plano (vs versao anterior do .xlsx)

Os seguintes blocos estavam no .xlsx v3 mas saem desta versao porque sao **fora do escopo de Thiago como Head de Automacao e IA**:

| Item removido | Por quê |
|---|---|
| Aba "Pricing & Estrutura Comercial" (valores R$ 30-80k, +30-40%, etc.) | Decisao de lideranca comercial |
| Aba "Pre-requisitos de Venda" (sponsor, capacity, etc. como check comercial) | Decisao de lideranca comercial / vendas |
| Aba "Diferenciadores Competitivos" (7 pontos de posicionamento) | Decisao de marketing / posicionamento |
| "Modos de falha mitigados" como tabela de diferenciadores | Reformulado: parte tecnica/pedagogica entra na Aba 8 como "modos de falha pedagogicos a mitigar no design"; parte comercial fica fora |
| Naming comercial dos SKUs ("SKU CORE", "SKU PREMIUM" com valores) | Naming comercial e decisao de lideranca |

**O que esses itens viram:**
- Saem do Sheets de produto/escopo
- Documentados em `02-Process/2026-05-23-Escopo-Final-Consolidado.md` como referencia interna
- Quando lideranca comercial decidir, podem ser adicionados ao Sheets em aba marcada `[COMERCIAL]` ou em planilha comercial separada

---

## Plano de execucao em Codex

### Passo 1 — Auth do plugin de Sheets do Codex
Autenticar via interface do Codex e validar acesso de escrita ao Sheets.

### Passo 2 — Teste de escrita
Escrever 1 celula de teste em aba sandbox. Confirmar permissoes.

### Passo 3 — Backup pre-edicao
Garantir que existe backup do estado atual (Google Sheets ja tem historico de versao automatico, mas vale confirmar).

### Passo 4 — Execucao das edicoes
Aplicar na ordem:
1. Aba 1 Resumo Executivo (edicoes inline)
2. Aba 2 Cronograma (edicoes inline)
3. Aba 3 Sessoes Detalhadas (edicoes maiores mas dentro da estrutura)
4. Aba 4 Exercicios (remover linha + adicionar 2)
5. Aba 5 Casos de Uso (expansao com colunas novas + 18 linhas)
6. Aba 6 Matriz de Priorizacao (refinamento de pesos)
7. Aba 7 Acompanhamento (detalhamento)
8. Aba 8 Fontes e Insumos (adicionar referencias + bloco de modos de falha pedagogicos)
9. Criar Aba 9 [NOVO] Maturity Score & Diagnostico
10. Criar Aba 10 [NOVO] Criterios de Qualidade & Rubrica

### Passo 5 — Revisao visual
Thiago abre o Sheets, confere visualmente, reporta ajustes.

### Passo 6 — Apresentacao ao Rafinha
Thiago apresenta o Sheets editado, NAO o .xlsx v3. Linguagem da apresentacao: "validei seu trabalho, mantive estrutura, refinei conteudo onde experiencia mostrou que vale, adicionei 2 abas com metodologia de diagnostico e qualidade que sao da minha area".

---

## O que mudou em relacao a versao anterior deste plano

| Antes (Opcao 1 / .xlsx v3) | Agora (Opcao 2 / in-place) |
|---|---|
| 10 abas novas em arquivo novo | 8 abas editadas in-place + 2 abas novas marcadas [NOVO] |
| Espinha dorsal nova | Espinha dorsal do Rafinha preservada |
| Apresentacao = "aqui esta minha versao" | Apresentacao = "validei o seu, refinei aqui, adicionei essas 2 metodologias" |
| Pricing, pre-requisitos venda, diferenciadores como abas dele | Removidos (fora do escopo de Thiago) |
| Modos de falha como diferenciador competitivo | Modos de falha como bloco tecnico-pedagogico em Fontes e Insumos |
| Naming "SKU CORE/PREMIUM" + valores | Removido |
| ~25KB de .xlsx novo | Edicoes pontuais no Sheets existente via MCP |
