---
created_at: 2026-05-19
status: anexo-detalhado
wave: 5A
artifact: F1 master-funnel-diagram-winning
runtime_modified: false
drive_modified: false
parent_doc: Wave-5A-F1-Master-Funnel-Diagram-Winning.md
---

# Wave 5A - F1 Auditoria Detalhada

Este documento preserva o detalhe da auditoria para nao deixar o documento principal da Wave 5A com mais de 300 linhas.

## Fontes lidas

| Fonte | Uso |
|---|---|
| `AGENTS.md` | Regras locais do cockpit |
| `07-Runtime-Squad/AGENTS.md` | Regras do runtime canonico |
| `02-Process/Mapa-do-Squad-e-Repo-Externo.md` | Metodo das waves e escopo da Wave 5A |
| `02-Process/Wave-2-Auditoria-Design-System-e-Google-Workspace-MCP.md` | Precondicao de Design System e rota Google Workspace |
| `07-Runtime-Squad/templates/TEMPLATE_REGISTRY.md` | Registry F1 |
| `07-Runtime-Squad/tasks/generate-funnel-kpis.md` | Task dona do F1/F2 |
| `07-Runtime-Squad/agents/foundation-agent.md` | Agent dono provavel |
| `07-Runtime-Squad/skills/find-replace-placeholders.md` | Contrato de placeholders |
| `07-Runtime-Squad/skills/identidade-visual-dupla.md` | Regra visual operacional do squad |
| `07-Runtime-Squad/checklists/camada-a-estruturais.md` | QA universal |
| `07-Runtime-Squad/checklists/camada-b-01-funil-kpis.md` | QA especifico do #01 |
| `07-Runtime-Squad/checklists/camada-c-cross-deliverable.md` | Dependencias cross-deliverable |
| `D:\1AWinningSales-Projetos\squadfactory\Design System` | Fonte visual Winning |
| `.codex/skills/frontend-design/SKILL.md` | Lente auxiliar |
| `.codex/skills/refactoring-ui/SKILL.md` | Lente auxiliar |

## Evidencias do deck

| Evidencia | Resultado |
|---|---|
| Google Slides ID | `1MLhe3oKxK5hvwF6wQG-djjsTZsiOGHckpeGAV99tEMc` |
| Titulo | `master-funnel-diagram-winning` |
| Slide count | 5 slides |
| Comentarios | 0 comentarios |
| Texto exportado | Confirmado por export `text/plain` |
| Thumbnails | Geradas para slides 1-5 em `.tmp-wave5a-f1/` na execucao original |

## Fato confirmado vs inferencia

Fatos confirmados:

- F1 esta no registry como Slides nativo do entregavel `#01 Funil`.
- O deck tem 5 slides.
- A task dona e `generate-funnel-kpis.md`, com `@foundation-agent`.
- As skills relacionadas sao `find-replace-placeholders.md` e `identidade-visual-dupla.md`.
- O Design System Winning define navy/crimson, fundo branco/bone, Jost, Inter, Fraunces, 8pt rhythm, generous whitespace, cards brancos com borda sutil, gradiente contido, sem emoji e sem exclamacao.
- O deck atual usa cores proximas da marca, fundo bone e cards brancos.
- O deck atual usa Arial nos textos observaveis.
- Ha numeracao quebrada em slides 2, 3 e 4.
- Ha texto invertido no slide 4.

Inferencias:

- Google Slides nativo e a melhor rota de producao.
- HTML/CSS pode ser prototipo visual auxiliar, nao entrega final.
- Sem referencias Wave 7, nao e seguro aplicar polimento pesado.

## Recorte minimo Wave 3 para F1

Como nao havia recorte Wave 3 especifico para o F1, a analise adotou este contrato minimo.

### Contrato de variaveis

| Grupo | Tokens | Dono/origem provavel | Limite recomendado |
|---|---|---|---|
| Metadados | `{{NOME_CLIENTE}}`, `{{NOME_PRODUTO}}`, `{{VERSAO}}`, `{{DATA_GERACAO}}` | Perfil/onboarding/squad | Produto ate 36 caracteres; cliente ate 34 |
| Funis | `{{01_FUNIL_1_NOME}}`, `{{01_FUNIL_1_PROPOSITO}}`, `{{01_FUNIL_2_NOME}}`, `{{01_FUNIL_2_PROPOSITO}}` | `decisoes/01-funil-kpis.json` | Nome ate 28 caracteres; proposito ate 110 |
| Estagios - nomes | `{{01_FUNIL_1_ESTAGIO_1_NOME}}` ate `{{01_FUNIL_2_ESTAGIO_5_NOME}}` | Foundation Agent | Ate 24 caracteres |
| Estagios - descricao | `{{01_FUNIL_1_ESTAGIO_1_DESCRICAO}}` ate `{{01_FUNIL_2_ESTAGIO_5_DESCRICAO}}` | Foundation Agent | Ate 95 caracteres |
| Estagios - criterio | `{{01_FUNIL_1_ESTAGIO_1_CRITERIO_SAIDA}}` ate `{{01_FUNIL_2_ESTAGIO_5_CRITERIO_SAIDA}}` | Foundation Agent | Ate 95 caracteres |
| Handoff | `{{01_HANDOFF_PRINCIPAL}}` | Foundation Agent / decisoes #01 | Ate 140 caracteres |
| Gestao | `{{01_METAS_NUMERICAS}}`, `{{01_RITUAIS}}`, `{{01_DECISOES_PENDENTES}}` | `decisoes/01-funil-kpis.json` | 3-5 bullets, ate 70 caracteres por bullet |

Riscos:

- O template presume 2 funis x 5 estagios.
- Se houver menos etapas, precisa limpar/remover cards e linhas.
- Se houver mais etapas, precisa dividir em slide adicional aprovado.
- `{{01_RITUAIS}}` no F1 e agregado, enquanto F2 usa rituais granulares.
- Nao ha limite formal de caracteres no registry/task para variaveis de slide.

## Diagnostico por slide

### Slide 1 - Capa / arquitetura de funil

| Criterio | Diagnostico |
|---|---|
| Hierarquia | Titulo domina corretamente, mas a capa ainda parece slide interno. |
| Grid | Estrutura clara com titulo, dois cards de funil, handoff e leitura executiva. |
| Densidade | Baixa a media; suporta texto real se for curto. |
| Tipografia | Arial; diverge de Jost/Inter. |
| Cor | Paleta proxima, mas sem uso qualificado de logo/gradiente. |
| Visuais | Diagrama basico de dois cards e seta. |
| Consistencia | Coerente com o restante do deck. |
| Numeracao | Sem problema critico neste slide. |
| Narrativa | Boa abertura para mapa de gestao. |
| Identidade Winning | Parcial: paleta sim, tipografia/logo/acabamento nao. |

### Slide 2 - Mapa dos funis e handoffs

| Criterio | Diagnostico |
|---|---|
| Hierarquia | Titulo claro; nomes dos funis poderiam orientar mais a leitura. |
| Grid | Duas linhas de 5 cards funcionam, mas parecem inventario mais que fluxo. |
| Densidade | Media-alta: 10 cards, handoff e nota competem. |
| Tipografia | Arial e textos pequenos; placeholders longos ja quebram. |
| Cor | Crimson e navy presentes, mas sem criterio semantico evidente. |
| Visuais | Falta conector/fluxo entre etapas. |
| Consistencia | Cards repetidos, mas com left-border accent que conflita com regra de cards do Design System. |
| Numeracao | `01`, `02` etc quebram como `0` e `1`. |
| Narrativa | Boa visao macro; handoff deveria ter mais peso visual. |
| Identidade Winning | Parcial e generica. |

### Slide 3 - Detalhe do Funil 1

| Criterio | Diagnostico |
|---|---|
| Hierarquia | Foco claro em tabela, mas header `ETAPA` esta comprimido. |
| Grid | Tabela de 5 linhas e 4 colunas e util para consulta. |
| Densidade | Alta para apresentacao; aceitavel como consulta. |
| Tipografia | Corpo pequeno e Arial. |
| Cor | Navy/crimson criam estrutura, mas excesso de caixas reduz tom editorial. |
| Visuais | Sem visual alem da tabela. |
| Consistencia | Espelha slide 4. |
| Numeracao | Numeros quebram em duas linhas. |
| Narrativa | Forte para detalhe operacional; fraca para storytelling. |
| Identidade Winning | Funcional, mas pouco premium. |

### Slide 4 - Detalhe do Funil 2

| Criterio | Diagnostico |
|---|---|
| Hierarquia | Mesma estrutura do slide 3. |
| Grid | Mesmo layout reutilizavel. |
| Densidade | Alta. |
| Tipografia | Arial e corpo pequeno. |
| Cor | Consistente com slide 3. |
| Visuais | Sem visual alem da tabela. |
| Consistencia | Deveria espelhar slide 3, mas tem defeito visual unico. |
| Numeracao | Numeros quebram em duas linhas. |
| Narrativa | Detalha segundo funil. |
| Identidade Winning | Parcial; texto/rodape aparece invertido na thumbnail. |

### Slide 5 - Metas e rituais comerciais

| Criterio | Diagnostico |
|---|---|
| Hierarquia | Tres blocos claros: metas, rituais, decisoes. |
| Grid | Dois cards superiores e um inferior; ha grandes vazios. |
| Densidade | Baixa no master, mas pode subir com listas reais. |
| Tipografia | Arial e placeholders pequenos. |
| Cor | Boa alternancia crimson/navy, mas left-border accent se repete. |
| Visuais | Falta iconografia sutil para metas, rituais e decisoes. |
| Consistencia | Coerente com o deck. |
| Numeracao | Sem numeracao de etapa. |
| Narrativa | Fecha bem conectando arquitetura e gestao. |
| Identidade Winning | Tem sobriedade, mas falta acabamento editorial. |

## Mapa Universal / Variavel / Hardcoded

### Universal

| Elemento | Status |
|---|---|
| Formato 16:9 | Confirmado |
| Background bone/off-white | Confirmado |
| Paleta navy/crimson | Confirmado |
| Top bar crimson | Confirmado |
| Wordmark/assinatura Winning | Parcial; hoje e texto |
| Metadata cliente/versao/data | Confirmado |
| Grid de cards/tabela | Confirmado |
| Footer/slide number | Parcial |

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
| 2 | 10 nomes de estagios, funis, handoff |
| 3 | Nome do funil 1, 5 nomes, 5 descricoes, 5 criterios |
| 4 | Nome do funil 2, 5 nomes, 5 descricoes, 5 criterios |
| 5 | `{{01_METAS_NUMERICAS}}`, `{{01_RITUAIS}}`, `{{01_DECISOES_PENDENTES}}` |

### Hardcoded ruim

| Elemento | Risco |
|---|---|
| Fonte Arial | Diverge do Design System |
| `WINNING SALES` como texto | Nao usa asset oficial |
| Top bar/faixas como shapes repetidos | Dificulta manutencao |
| Numeros `01..05` estreitos | Quebram em duas linhas |
| Rodape/texto invertido no slide 4 | Bloqueador |
| `Detalhe do Funil 1/2` fixo | Menos contextual que nome real do funil |
| 5 estagios sempre visiveis | Pode gerar vazios/placeholders |

## Mudancas necessarias - somente plano

| Area | Plano |
|---|---|
| Template F1 | Criar slide master com logo asset, Jost/Inter, numeracao robusta e layouts-base |
| Template F1 | Corrigir slide 4 invertido |
| Template F1 | Substituir left-border accent por componente de etapa/secao mais aderente ao Design System |
| Template F1 | Definir caixas e limites reais para 1-5 estagios |
| Registry F1 | Documentar limites de caracteres, stage count e layouts-base |
| Task `generate-funnel-kpis.md` | Explicitar QA visual por thumbnail e limpeza de cards/linhas nao usados |
| Checklist B #01 | Adicionar checks: sem texto invertido, sem numeracao quebrada, sem overflow, identidade Winning/dupla |

