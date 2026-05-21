---
created_at: 2026-05-19
status: consolidada
artifact: F1 master-funnel-diagram-winning
base_doc: ..\..\Wave-5A-F1-Master-Funnel-Diagram-Winning.md
runtime_modified: false
drive_modified: false
feeds:
  - 02-consolidacao-pre-wave5b.md
  - 03-plano-de-acao-tecnico.md
---

# 01 - Auditoria 1 / Wave 5A Consolidada

## Decisao sobre a Wave 5A existente

A Wave 5A do F1 ja foi executada e continua valida. Este documento nao apaga nem substitui o original; ele reorganiza a execucao em formato mais facil para o SM/dev consumir.

Fonte base:

- `02-Process/Wave-5A-F1-Master-Funnel-Diagram-Winning.md`

Status:

- `Wave 5A`: concluida.
- `Wave 5B`: nao executada.
- Alteracao em Drive: nao feita.
- Alteracao em runtime/templates/tasks/agents/skills/checklists: nao feita.

## Fontes e artefatos relacionados

| Fonte | Uso |
|---|---|
| `AGENTS.md` | Regras locais do cockpit e cuidado com runtime. |
| `07-Runtime-Squad/AGENTS.md` | Regras canonicas do runtime markdown-first. |
| `02-Process/Mapa-do-Squad-e-Repo-Externo.md` | Metodo das waves. |
| `02-Process/Wave-2-Auditoria-Design-System-e-Google-Workspace-MCP.md` | Base de Design System e Google Workspace. |
| `07-Runtime-Squad/templates/TEMPLATE_REGISTRY.md` | Registry do F1 e ID do master. |
| `07-Runtime-Squad/tasks/generate-funnel-kpis.md` | Task dona do F1/F2. |
| `07-Runtime-Squad/agents/foundation-agent.md` | Agent responsavel provavel. |
| `07-Runtime-Squad/skills/find-replace-placeholders.md` | Contrato de placeholders. |
| `07-Runtime-Squad/skills/identidade-visual-dupla.md` | Regra visual do squad. |
| `07-Runtime-Squad/checklists/camada-a-estruturais.md` | QA universal. |
| `07-Runtime-Squad/checklists/camada-b-01-funil-kpis.md` | QA especifico do #01. |
| `07-Runtime-Squad/checklists/camada-c-cross-deliverable.md` | Dependencias cross-deliverable. |
| `D:\1AWinningSales-Projetos\squadfactory\Design System` | Fonte de verdade visual Winning. |
| `.codex/skills/frontend-design/SKILL.md` | Lente auxiliar de design, nao fonte de verdade. |
| `.codex/skills/refactoring-ui/SKILL.md` | Lente auxiliar de hierarquia/espacamento, nao fonte de verdade. |

## Estado confirmado do F1

| Item | Valor |
|---|---|
| Artefato | `master-funnel-diagram-winning` |
| Tipo | Google Slides nativo |
| Entregavel | `#01 Funil` |
| Master ID do registry | `1MLhe3oKxK5hvwF6wQG-djjsTZsiOGHckpeGAV99tEMc` |
| Slide count | 5 slides |
| Rota recomendada | Google Slides nativo |
| Template runtime alterado? | Nao |
| Google Slides alterado? | Nao |

## Fatos confirmados

- O F1 esta registrado como Slides nativo.
- O template atual tem 5 slides, dentro do limite previsto de 3-5 slides.
- A task dona e `generate-funnel-kpis.md`, com responsabilidade do `foundation-agent`.
- Skills diretamente relacionadas: `find-replace-placeholders.md` e `identidade-visual-dupla.md`.
- Checklists relacionados: Camada A universal, Camada B `#01 Funil + KPIs`, Camada C cross-deliverable.
- O Design System Winning define navy/crimson, fundo branco/bone, Jost para display, Inter para corpo, Fraunces editorial, ritmo de 8pt, whitespace generoso, cards brancos com borda sutil e uso contido de gradiente.
- O deck atual usa cores proximas da marca, fundo bone e cards brancos.
- O deck atual usa Arial nos textos observaveis.
- A numeracao de etapas quebra nos slides 2, 3 e 4.
- O slide 4 tem texto/rodape/criterio de leitura invertido.
- Falta logo/wordmark asset oficial; aparece `WINNING SALES` como texto.

## Inferencias assumidas

- A rota final deve continuar sendo Google Slides nativo, porque o master ja e nativo, o fluxo usa duplicacao e find-replace, e o resultado precisa ser editavel.
- HTML/CSS pode ajudar como prototipo visual auxiliar, mas nao deve virar entrega final do F1.
- Slides 3 e 4 funcionam melhor como consulta operacional/appendix do que como storytelling principal.
- Sem limites formais de caracteres, o find-replace tende a quebrar layout em clientes reais.
- A referencia visual deve elevar acabamento, mas sem transformar o F1 em aula, workbook ou treinamento.

## Rota tecnica recomendada

**Decisao:** Google Slides nativo.

Justificativa:

- Ja e a rota registrada no registry.
- Preserva editabilidade e operacao via Google Workspace.
- Mantem compatibilidade com placeholders e find-replace em batch.
- Permite QA por thumbnails e leitura nativa.

Rotas descartadas:

- PPTX nativo: util apenas como intercambio/backup, nao como fonte principal.
- HTML/CSS: util como prototipo auxiliar, nao como template final.

## Contrato minimo de variaveis

| Grupo | Tokens | Dono/origem provavel | Limite recomendado |
|---|---|---|---|
| Metadados | `{{NOME_CLIENTE}}`, `{{NOME_PRODUTO}}`, `{{VERSAO}}`, `{{DATA_GERACAO}}` | Perfil/onboarding/squad | Produto ate 36 caracteres; cliente ate 34. |
| Funis | `{{01_FUNIL_1_NOME}}`, `{{01_FUNIL_1_PROPOSITO}}`, `{{01_FUNIL_2_NOME}}`, `{{01_FUNIL_2_PROPOSITO}}` | `decisoes/01-funil-kpis.json` | Nome ate 28 caracteres; proposito ate 110. |
| Estagios - nomes | `{{01_FUNIL_1_ESTAGIO_1_NOME}}` ate `{{01_FUNIL_2_ESTAGIO_5_NOME}}` | Foundation Agent | Ate 24 caracteres por card. |
| Estagios - descricao | `{{01_FUNIL_1_ESTAGIO_1_DESCRICAO}}` ate `{{01_FUNIL_2_ESTAGIO_5_DESCRICAO}}` | Foundation Agent | Ate 95 caracteres. |
| Estagios - criterio de saida | `{{01_FUNIL_1_ESTAGIO_1_CRITERIO_SAIDA}}` ate `{{01_FUNIL_2_ESTAGIO_5_CRITERIO_SAIDA}}` | Foundation Agent | Ate 95 caracteres. |
| Handoff | `{{01_HANDOFF_PRINCIPAL}}` | Foundation Agent / decisoes #01 | Ate 140 caracteres. |
| Gestao | `{{01_METAS_NUMERICAS}}`, `{{01_RITUAIS}}`, `{{01_DECISOES_PENDENTES}}` | `decisoes/01-funil-kpis.json` | 3-5 bullets, ate 70 caracteres por bullet. |

Riscos do contrato atual:

- Template presume 2 funis x 5 estagios.
- Se houver menos etapas, o runtime precisa limpar/remover cards ou linhas vazias.
- Se houver mais etapas, precisa dividir/duplicar layout com regra aprovada.
- `{{01_RITUAIS}}` no F1 e agregado, enquanto F2 usa rituais granulares.
- Os limites acima ainda nao estao formalizados no registry/task/checklists.

## Diagnostico por slide

| Slide | Diagnostico consolidado | Gaps principais |
|---|---|---|
| 1 - Capa / arquitetura de funil | Estrutura clara com titulo, dois cards de funil, handoff e leitura executiva. Parece mais slide interno do que capa premium. | Arial, wordmark como texto, visual pouco distintivo, barra crimson plana. |
| 2 - Mapa dos funis e handoffs | Boa visao macro em duas linhas de 5 cards, mas parece inventario, nao jornada. Handoff deveria ter mais peso visual. | Numeracao quebrada, densidade media-alta, falta conectores/fluxo, cards com left-border accent generico. |
| 3 - Detalhe do Funil 1 | Tabela util para consulta operacional, com foco em etapa, descricao e criterio. Alta densidade para apresentacao em sala. | Numeracao quebrada, header comprimido, texto pequeno, pouco storytelling. |
| 4 - Detalhe do Funil 2 | Deve espelhar slide 3 e reutilizar layout de detalhe. | Numeracao quebrada, texto/rodape invertido, corpo pequeno, defeito visual bloqueador. |
| 5 - Metas e rituais | Fecha conectando arquitetura com gestao comercial; tres blocos claros. | Pode virar lista longa, falta iconografia sutil, grandes vazios internos, ainda usa Arial/left-border accents. |

## Mapa Universal / Variavel / Hardcoded

### Universal

| Elemento | Status |
|---|---|
| Formato 16:9 | Confirmado. |
| Background bone/off-white | Confirmado; deve virar token visual. |
| Paleta navy/crimson | Confirmada, mas precisa refinamento Winning. |
| Top accent | Confirmado; hoje duplicado como shape, deveria virar master/layout. |
| Wordmark Winning | Parcial; hoje e texto, precisa asset oficial. |
| Metadados cliente/versao/data | Confirmados; devem ficar consistentes no master. |
| Grid de cards/tabela | Confirmado; pode virar layout-base. |
| Footer/slide number | Parcial; precisa sistema robusto. |

### Variavel de apresentacao

| Elemento | Tokens |
|---|---|
| Produto | `{{NOME_PRODUTO}}` |
| Cliente | `{{NOME_CLIENTE}}` |
| Versao | `{{VERSAO}}` |
| Data | `{{DATA_GERACAO}}` |
| Funis | `{{01_FUNIL_1_NOME}}`, `{{01_FUNIL_2_NOME}}` |
| Propositos | `{{01_FUNIL_1_PROPOSITO}}`, `{{01_FUNIL_2_PROPOSITO}}` |
| Handoff | `{{01_HANDOFF_PRINCIPAL}}` |

### Variavel de slide

| Slide | Variaveis |
|---|---|
| 2 | 10 nomes de estagios, nomes dos funis e handoff. |
| 3 | Nome do funil 1, 5 nomes de estagio, 5 descricoes, 5 criterios de saida. |
| 4 | Nome do funil 2, 5 nomes de estagio, 5 descricoes, 5 criterios de saida. |
| 5 | `{{01_METAS_NUMERICAS}}`, `{{01_RITUAIS}}`, `{{01_DECISOES_PENDENTES}}`. |

### Hardcoded ruim

| Elemento | Risco |
|---|---|
| Fonte Arial | Diverge do Design System Winning. |
| `WINNING SALES` como texto | Nao usa asset oficial e reduz percepcao de marca. |
| Top bar e faixas como shapes repetidos | Dificulta manutencao e consistencia. |
| Numeros `01..05` em caixa estreita | Quebram em duas linhas. |
| Texto/rodape invertido no slide 4 | Defeito visual bloqueador. |
| `Detalhe do Funil 1/2` fixo | Menos contextual que usar nome real do funil. |
| 5 estagios sempre visiveis | Pode gerar vazio, placeholder remanescente ou layout quebrado. |
| Texto de apoio fixo | Pode virar instrucao interna se nao for revisado. |

## Base visual reutilizavel recomendada

| Padrao | Regra |
|---|---|
| Master | Canvas 16:9, safe margin 48-64px, grid consistente e ritmo 8pt. |
| Fundo | Bone/paper como base; dark apenas para contraste pontual. |
| Logo | Usar asset oficial `logo-gradient.png` no claro e `logo-white.png` no escuro, se disponiveis. |
| Tipografia | Jost para titulos/eyebrows; Inter para corpo; mono para numeracao. |
| Eyebrow | ALL CAPS com tracking controlado; sem exagerar em texto pequeno. |
| Cards | Fundo branco, borda sutil, raio moderado, sombra discreta; evitar left-border accent como padrao. |
| Numeracao | Componente fixo de dois digitos, com largura suficiente para `01` sem quebra. |
| Footer | Cliente, versao, data e opcional slide number em master/layout. |

Layouts-base:

| Layout | Uso |
|---|---|
| `cover_executive_map` | Slide 1. |
| `funnel_overview_2x5` | Slide 2. |
| `funnel_detail_table` | Slides 3 e 4. |
| `management_cards` | Slide 5. |

## Bloqueios antes da Wave 5B

| Bloqueio | Severidade | Motivo |
|---|---:|---|
| Corrigir texto/rodape invertido do slide 4 | Alta | Defeito visual confirmado. |
| Corrigir numeracao quebrada | Alta | Afeta leitura de etapas nos slides 2, 3 e 4. |
| Definir escala tipografica nativa em pontos | Alta | Design System esta em tokens web; Slides precisa contrato proprio. |
| Aprovar limites de texto por placeholder | Alta | Sem limite, find-replace quebra layout. |
| Adaptar referencias Do it yourself | Alta | REF-01/03/04 sao Do it yourself; nao podem virar aula no F1. |
| Incorporar aprendizados da REF-03 sem inflar escopo | Media | REF-03 enriquece conteudo/variaveis, mas nao deve transformar o F1 em roteiro DBA. |
| Regra para menos/mais de 5 estagios | Media | Template atual e rigido. |
