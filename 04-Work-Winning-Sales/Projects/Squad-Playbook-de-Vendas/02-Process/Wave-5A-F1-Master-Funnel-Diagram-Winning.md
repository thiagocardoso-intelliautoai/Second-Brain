---
created_at: 2026-05-18
status: concluida
wave: 5A
artifact: F1 master-funnel-diagram-winning
runtime_modified: false
drive_modified: false
---

# Wave 5A - F1 `master-funnel-diagram-winning`

## Escopo e evidencias

Esta execucao cobre somente a Wave 5A do F1. Nao houve Wave 5B, redesign final, alteracao no Google Slides, nem mudanca em runtime, agents, tasks, workflows, skills, checklists, templates ou regras.

Fontes lidas:

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
| `D:\1AWinningSales-Projetos\squadfactory\Design System` | Fonte de verdade visual Winning |
| `.codex/skills/frontend-design/SKILL.md` | Lente auxiliar: direcao visual |
| `.codex/skills/refactoring-ui/SKILL.md` | Lente auxiliar: hierarquia, espacamento, tipo, cor |

Evidencias do deck atual:

| Evidencia | Resultado |
|---|---|
| Google Slides ID | `1MLhe3oKxK5hvwF6wQG-djjsTZsiOGHckpeGAV99tEMc` |
| Titulo | `master-funnel-diagram-winning` |
| Revisao lida | `NtLp_fq3ArCqQQ` |
| Slide count | 5 slides |
| Comentarios | 0 comentarios |
| Texto exportado | Confirmado via export `text/plain` |
| Thumbnails | Geradas em `.tmp-wave5a-f1/p1.png` ate `.tmp-wave5a-f1/p5.png` |

## Fato confirmado vs inferencia

Fatos confirmados:

- O F1 esta registrado no registry como Slides nativo, entregavel `#01 Funil`, status `OK Onda 4.2 Google Slides nativo + QA integrado`.
- O template atual tem 5 slides, dentro do limite de 3-5 slides previsto no registry. Nao precisa chunking de 50+ slides.
- A task dona e `generate-funnel-kpis.md`, responsavel `@foundation-agent`.
- Skills relacionadas: `find-replace-placeholders.md` e `identidade-visual-dupla.md`.
- Checklists relacionados: Camada A universal, Camada B `#01 Funil + KPIs`, e Camada C cross-deliverable.
- O Design System Winning define: navy/crimson, fundo branco/bone, Jost para display, Inter para corpo, Fraunces editorial, 8pt rhythm, generous whitespace, cards brancos com borda sutil, uso muito contido de gradiente e ausencia de emoji/exclamacao.
- O deck atual usa cores proximas da marca, fundo bone, cards brancos e accent crimson/navy, mas usa Arial em todos os textos observaveis pelo conector.
- As thumbnails confirmam problemas visuais: numeracao de etapas quebrando em duas linhas nos slides 2, 3 e 4; texto do rodape/criterio de leitura invertido no slide 4; ausencia de logo/wordmark asset; uso predominante de texto e cards, sem icones, graficos ou imagem.

Inferencias:

- A melhor rota tecnica de producao para F1 e Google Slides nativo, porque o master ja e nativo, o conector Codex le estrutura e thumbnails, e a entrega final precisa continuar editavel com placeholders.
- HTML/CSS pode ajudar como prototipo visual isolado na Wave 5B, mas nao deve virar rota final do F1 porque quebraria editabilidade nativa e o fluxo de duplicacao/find-replace.
- As referencias do Rafael nao estao separadas para este artefato; a busca local encontrou referencias a separar para DBA/DBS/ROI, mas nenhuma referencia especifica de funil/F1 pronta para benchmark.

## Recorte minimo Wave 3 para F1

Como nao havia recorte Wave 3 especifico para `master-funnel-diagram-winning`, este bloco registra o contrato minimo antes da analise visual.

### Rota tecnica recomendada

**Decisao:** Google Slides nativo como rota de producao.

Justificativa:

- O registry ja aponta F1 como Google Slides nativo.
- O conector conseguiu ler o deck, exportar texto e gerar thumbnails.
- O artefato depende de placeholders e find-replace em batch, o que combina com Slides API.
- A Wave 5A precisa criar base reutilizavel, nao um prototipo estatico.

Rota secundaria:

- PPTX nativo: util apenas como intercambio ou backup local, nao como fonte principal.
- HTML/CSS: util para prototipar visual Winning, nao para entrega final do template.

### Contrato de variaveis

| Grupo | Tokens reais confirmados | Dono/origem provavel | Limite recomendado |
|---|---|---|---|
| Metadados globais | `{{NOME_CLIENTE}}`, `{{NOME_PRODUTO}}`, `{{VERSAO}}`, `{{DATA_GERACAO}}` | Perfil/onboarding/squad | Produto ate 36 caracteres; cliente ate 34; versao/data curtas |
| Funis | `{{01_FUNIL_1_NOME}}`, `{{01_FUNIL_1_PROPOSITO}}`, `{{01_FUNIL_2_NOME}}`, `{{01_FUNIL_2_PROPOSITO}}` | `decisoes/01-funil-kpis.json` / Foundation Agent | Nome ate 28 caracteres; proposito ate 110 caracteres |
| Estagios - nomes | `{{01_FUNIL_1_ESTAGIO_1_NOME}}` ... `{{01_FUNIL_2_ESTAGIO_5_NOME}}` | Foundation Agent | Ate 24 caracteres por card |
| Estagios - descricao | `{{01_FUNIL_1_ESTAGIO_1_DESCRICAO}}` ... `{{01_FUNIL_2_ESTAGIO_5_DESCRICAO}}` | Foundation Agent | Ate 95 caracteres |
| Estagios - criterio de saida | `{{01_FUNIL_1_ESTAGIO_1_CRITERIO_SAIDA}}` ... `{{01_FUNIL_2_ESTAGIO_5_CRITERIO_SAIDA}}` | Foundation Agent | Ate 95 caracteres |
| Handoff | `{{01_HANDOFF_PRINCIPAL}}` | Foundation Agent / decisoes #01 | Ate 140 caracteres |
| Gestao | `{{01_METAS_NUMERICAS}}`, `{{01_RITUAIS}}`, `{{01_DECISOES_PENDENTES}}` | `decisoes/01-funil-kpis.json` | Lista curta: 3-5 bullets, ate 70 caracteres por bullet |

Riscos do contrato atual:

- O template presume 2 funis x 5 estagios. Se houver menos etapas, o runtime precisa limpar/remover linhas/cards nao usados; se houver mais, precisa dividir ou duplicar layout.
- `{{01_RITUAIS}}` e uma lista agregada no F1, enquanto F2 usa rituais mais granulares (`daily`, `weekly`, `1:1`). A task precisa mapear ambos sem divergencia.
- Nao ha limite formal de caracteres no registry/task para os campos de slide; isso e risco alto de quebra visual.

## Diagnostico por slide

### Slide 1 - Capa / arquitetura de funil

| Criterio | Diagnostico |
|---|---|
| Hierarquia | Titulo domina corretamente, mas esta mais proximo de slide interno do que de capa premium. O bloco "WINNING SALES" aparece como texto, nao como wordmark asset. |
| Grid | Boa estrutura de leitura: titulo, dois cards de funil, handoff e leitura executiva. Espaco inferior grande cria respiro, mas tambem deixa a capa pouco memoravel. |
| Densidade | Baixa a media. Aguenta preenchimento real se os textos forem curtos. |
| Tipografia | Usa Arial; diverge da regra Winning de Jost para display e Inter para corpo. Eyebrows nao evidenciam tracking 0.22em. |
| Cor | Cores proximas a navy/crimson/bone, mas a barra superior crimson e plana; nao usa gradiente assinatura nem logo. |
| Visuais | Diagrama basico com dois cards e seta. Funcional, mas pouco distintivo para a marca. |
| Consistencia | Alinha com o restante do deck por cards e top bar. |
| Numeracao | Sem problema critico de numeracao de etapa neste slide. |
| Narrativa | Cumpre a abertura: mostra que o deck e mapa de gestao antes de detalhe operacional. |
| Identidade Winning | Parcial. Paleta aproxima, mas fonte, asset de logo e acabamento ainda nao refletem o Design System. |

### Slide 2 - Mapa dos funis e handoffs

| Criterio | Diagnostico |
|---|---|
| Hierarquia | Titulo e subtitulo claros. Os nomes dos funis ficam menos proeminentes que os cards de etapa, embora sejam orientadores principais. |
| Grid | Duas linhas de 5 cards funcionam para comparacao, mas falta conector/fluxo horizontal entre etapas; hoje parece inventario, nao jornada. |
| Densidade | Media-alta. Dez cards + handoff + nota de ajuste competem por atencao. |
| Tipografia | Arial e textos pequenos. Placeholders longos ja quebram linhas nos cards, sinal de risco com nomes reais. |
| Cor | Crimson marca primeira etapa do funil 1 e ultima do funil 2, mas o criterio semantico dessa escolha nao esta explicitado visualmente. |
| Visuais | Cards sao funcionais, mas sem icones ou shape de fluxo. |
| Consistencia | Repete card branco + faixa vertical. A faixa colorida dentro de cards conflita com o Design System, que evita colored left-border accents em cards. |
| Numeracao | Problema confirmado: `01`, `02` etc aparecem quebrados como `0` e `1` em linhas separadas. |
| Narrativa | Boa visao macro, mas deveria comunicar handoff com mais forca visual. |
| Identidade Winning | Parcial. Paleta correta, mas acabamento de grid e tipografia parecem genericos. |

### Slide 3 - Detalhe do Funil 1

| Criterio | Diagnostico |
|---|---|
| Hierarquia | Titulo e tabela deixam claro que o foco e detalhamento. O header da coluna `ETAPA` esta comprimido/recortado. |
| Grid | Tabela de 5 linhas e 4 colunas e boa para consulta, mas as colunas de descricao/criterio podem ficar longas demais. |
| Densidade | Alta. Como slide de apresentacao, tende a virar leitura de tabela; como material consultivo, e aceitavel se tratado como appendix/consulta. |
| Tipografia | Texto muito pequeno para apresentacao em sala. Arial diverge do Design System. |
| Cor | Navy no header e crimson na primeira etapa criam hierarquia, mas o excesso de caixas reduz o carater editorial. |
| Visuais | Nao ha visual alem da tabela. Falta um modo de marcar progressao ou criterio de passagem. |
| Consistencia | Estrutura consistente com slide 4. |
| Numeracao | Numeros de etapa quebram visualmente em duas linhas. |
| Narrativa | Forte para detalhe operacional; fraca para storytelling. |
| Identidade Winning | Parcial. O slide e funcional, mas pouco premium e pouco tipografico. |

### Slide 4 - Detalhe do Funil 2

| Criterio | Diagnostico |
|---|---|
| Hierarquia | Mesma estrutura do slide 3, com foco claro no funil 2. |
| Grid | Mesmo grid do slide 3, reaproveitavel como layout-base. |
| Densidade | Alta. Risco igual ao slide 3. |
| Tipografia | Arial e corpo pequeno. |
| Cor | Consistente com slide 3. |
| Visuais | Nao ha visual alem da tabela. |
| Consistencia | Deveria espelhar slide 3, mas ha um defeito visual unico. |
| Numeracao | Numeros de etapa quebram em duas linhas. |
| Narrativa | Detalha o segundo funil, mas depende do slide anterior para sentido. |
| Identidade Winning | Parcial. Alem dos problemas de fonte/asset, o rodape/criterio de leitura aparece invertido de cabeca para baixo na thumbnail, o que bloqueia Wave 5B sem correcao. |

### Slide 5 - Metas e rituais comerciais

| Criterio | Diagnostico |
|---|---|
| Hierarquia | Titulo e tres blocos principais sao claros: metas, rituais, decisoes. |
| Grid | Dois cards superiores + um card inferior criam leitura simples. A distribuicao deixa grandes vazios dentro dos cards. |
| Densidade | Baixa no master, mas pode virar alta se metas/rituais vierem como lista longa. |
| Tipografia | Arial e placeholders pequenos; deve migrar para Inter/Jost em escala de pontos propria para Slides. |
| Cor | Boa alternancia crimson/navy nas faixas, mas novamente como left-border accent em card. |
| Visuais | Falta iconografia sutil para metas, rituais e decisoes; a tela fica muito textual. |
| Consistencia | Consistente com a linguagem de cards do deck. |
| Numeracao | Sem numeracao de etapa. |
| Narrativa | Fecha bem ao conectar arquitetura com gestao comercial. |
| Identidade Winning | Parcial. Tem sobriedade e espaco, mas falta acabamento editorial e sistema tipografico. |

## Mapa Universal / Variavel / Hardcoded

### Universal

| Elemento | Status | Observacao |
|---|---|---|
| Formato 16:9 | Confirmado | Thumbnails 1600x900 |
| Background bone/off-white | Confirmado | Alinha com `--ws-bone`, mas deve ser tokenizado no contrato |
| Paleta navy/crimson | Confirmado | Proxima aos tokens Winning |
| Top bar crimson | Confirmado | Deve virar elemento de master/layout, nao shape duplicado manualmente |
| Wordmark/assinatura Winning | Parcial | Hoje e texto `WINNING SALES`; recomendacao e asset oficial |
| Metadata cliente/versao/data | Confirmado | Deve ficar no master ou placeholder global consistente |
| Grid de cards/tabela | Confirmado | Pode virar layout-base reutilizavel |
| Footer/slide number | Parcial | Texto exportado mostra numeros 1-5; visual nao usa um sistema robusto de numeracao |

### Variavel de apresentacao

| Elemento | Tokens |
|---|---|
| Produto | `{{NOME_PRODUTO}}` |
| Cliente | `{{NOME_CLIENTE}}` |
| Versao | `{{VERSAO}}` |
| Data | `{{DATA_GERACAO}}` |
| Funis principais | `{{01_FUNIL_1_NOME}}`, `{{01_FUNIL_2_NOME}}` |
| Propositos dos funis | `{{01_FUNIL_1_PROPOSITO}}`, `{{01_FUNIL_2_PROPOSITO}}` |
| Handoff principal | `{{01_HANDOFF_PRINCIPAL}}` |

### Variavel de slide

| Slide | Variaveis |
|---|---|
| 2 | 10 nomes de estagios, funis, handoff |
| 3 | Nome do funil 1, 5 nomes de estagio, 5 descricoes, 5 criterios de saida |
| 4 | Nome do funil 2, 5 nomes de estagio, 5 descricoes, 5 criterios de saida |
| 5 | `{{01_METAS_NUMERICAS}}`, `{{01_RITUAIS}}`, `{{01_DECISOES_PENDENTES}}` |

### Hardcoded ruim

| Elemento | Risco |
|---|---|
| Fonte Arial | Diverge do Design System Winning e reduz percepcao premium |
| `WINNING SALES` como texto | Nao usa assets oficiais; risco de desalinhamento com wordmark |
| Top bar e faixas como shapes repetidos | Dificulta manutencao e consistencia; deveria estar em master/layout |
| Numeros `01..05` em caixas estreitas | Quebra em duas linhas nas thumbnails |
| Rodape/criterio do slide 4 invertido | Defeito visual bloqueador antes de Wave 5B |
| `Detalhe do Funil 1/2` como titulo fixo | Pode ser menos claro que usar nome real do funil como titulo contextual |
| 5 estagios sempre visiveis | Risco de placeholders/linhas vazias quando a jornada real tiver menos etapas |
| Texto de apoio fixo em cards | E util, mas deve ser revisado para nao virar instrucao interna ou redundancia client-facing |

## Base visual reutilizavel recomendada

### Slide-mestre

| Elemento mestre | Regra recomendada |
|---|---|
| Canvas | 16:9, safe margin de 48px a 64px, grid 12 colunas ou 8pt equivalente |
| Fundo | `bone` ou `paper`; dark surface so para divisores ou slides especiais |
| Logo | Asset `logo-gradient.png` no claro; `logo-white.png` em dark |
| Top accent | Preferir hairline/gradient sutil ou faixa curta; evitar barra pesada em todos os slides |
| Tipografia | Jost para titulos/eyebrows; Inter para corpo; JetBrains/ui mono para numeracao |
| Eyebrow | ALL CAPS com tracking 0.22em |
| Cards | Fundo branco, borda sutil, raio 8-14px, sombra discreta; sem left-border accent como padrao de card |
| Numeracao | Componente mono fixo, largura suficiente para `01` sem quebra |
| Footer/metadata | Master placeholder com cliente, versao, data e opcional slide number |

### Layouts-base

| Layout | Uso | Componentes |
|---|---|---|
| `cover_executive_map` | Slide 1 | Kicker, titulo, subtitulo, mini-diagrama 2 funis, handoff, leitura executiva |
| `funnel_overview_2x5` | Slide 2 | Duas swimlanes de funil, stage chips, handoff destacado, criterio de ajuste |
| `funnel_detail_table` | Slides 3-4 | Nome do funil, tabela de ate 5 etapas, descricao e criterio de saida |
| `management_cards` | Slide 5 | Cards de metas, rituais e decisoes, com lista curta e icone Lucide opcional |

### Componentes/padroes

| Componente | Criterio para o agent/skill preencher sem quebrar |
|---|---|
| Stage chip | `NN` fixo com 2 digitos, caixa minima ampla, nunca quebrar linha |
| Nome de etapa | Ate 24 caracteres; se passar, resumir antes de substituir |
| Descricao/criterio | Ate 95 caracteres; uma frase concreta, sem bullet interno |
| Handoff | Ate 140 caracteres; se houver mais de um handoff, usar lista de no maximo 2 itens |
| Metas | 3-5 bullets, cada bullet com numero + unidade + responsavel quando possivel |
| Rituais | Separar Daily, Weekly e 1:1 quando houver dados; se ficar agregado, maximo 3 bullets |
| Decisoes pendentes | Se vazio, preencher "Nenhuma decisao pendente." |
| Stage count | Se menos de 5, ocultar/remover cards/linhas nao usados; se mais de 5, dividir em slide adicional aprovado |
| QA visual | Toda geracao deve ter thumbnail LARGE por slide alterado e verificacao de overflow/overlap/rotacao |

## Mudancas necessarias em template/runtime - somente plano

Nenhuma mudanca foi aplicada. Plano proposto para aprovacao futura:

| Area | Plano |
|---|---|
| Template F1 | Criar slide master com logo asset, estilos Jost/Inter, numeracao robusta, layouts-base e corrigir slide 4 invertido |
| Template F1 | Substituir faixas laterais em cards por componente de secao/stage que respeite melhor o Design System |
| Template F1 | Definir caixas com limites reais e tratamento para 1-5 estagios por funil |
| Registry F1 | Documentar limites de caracteres, regras de stage count e layouts-base |
| Task `generate-funnel-kpis.md` | Explicitar que F1 tem QA visual por thumbnail e que deve limpar cards/linhas nao usados |
| Task `generate-funnel-kpis.md` | Mapear `rituais` para F1 e campos granulares para F2 sem divergencia |
| Checklist B #01 | Adicionar checks visuais para F1: sem texto invertido, sem numeracao quebrada, sem overflow, identidade Winning/dupla aplicada |
| Skill `identidade-visual-dupla.md` | Se aprovado, esclarecer como a identidade Winning do master convive com paleta do produto/cliente no output final |

## Bloqueios antes da Wave 5B

| Bloqueio | Severidade | Motivo |
|---|---:|---|
| Aprovar rota Google Slides nativo como producao | Alta | Wave 5B nao deve redesenhar em rota equivocada |
| Corrigir texto invertido no slide 4 | Alta | Defeito visual confirmado em thumbnail |
| Definir escala tipografica em pontos para Slides | Alta | Design System existe em CSS/px, nao em contrato nativo de Slides |
| Aprovar limites de texto por placeholder | Alta | Sem limite, o find-replace pode quebrar layout |
| Definir regra para menos/mais de 5 estagios | Media | Template atual presume sempre 5 por funil |
| Confirmar identidade visual final | Media | Master Winning vs identidade dupla do produto/cliente |
| Confirmar benchmark Rafael para F1, se existir | Media | Nenhuma referencia F1 separada foi encontrada |

## Como usar inspiracoes da Wave 7

Minha recomendacao operacional: antes da Wave 5B, rodar uma rodada curta de Wave 7 para cada referencia real da Winning que Thiago enviar. Essa rodada nao deve apenas "atualizar waves anteriores"; ela deve gerar um plano de acao especifico para resolver gaps e melhorias encontrados na Wave 5A.

Regra critica: as referencias podem ser documentos reais da Winning Sales, mas muitas podem ser materiais `Do it yourself` (Winning ensinando o cliente a fazer). O F1 do Playbook e um entregavel `Done for you` (consultores entregando o material pronto para o cliente usar). Portanto:

- copiar estrutura didatica de workshop ou aula pode gerar um template errado para o Playbook;
- aproveitar clareza, sequencia, enquadramento, exemplos e linguagem consultiva e valido;
- converter qualquer instrucao "como fazer" em resultado pronto, criterio preenchivel, visual de decisao ou regra operacional client-facing;
- nao levar para o F1 textos que so fazem sentido em material de capacitacao, roteiro de aula, prompt interno ou manual do consultor;
- cada aprendizado da referencia deve virar uma decisao: `copiar`, `adaptar`, `nao copiar`, ou `pendente de aprovacao`.

Fluxo eficiente recomendado:

1. Thiago envia referencias pelo template rapido abaixo.
2. IA identifica IDs, le a referencia e classifica: `Done for you`, `Do it yourself`, `benchmark visual`, `benchmark narrativo`, `benchmark estrutural`, ou misto.
3. IA compara referencia contra o F1 e esta Wave 5A.
4. IA atualiza esta Wave 5A com aprendizados aplicaveis e nao aplicaveis.
5. IA monta plano de acao Wave 5B com ordem, impacto, risco e arquivos/artefatos afetados.
6. So depois de aprovado, executar mudancas no master/template/runtime.

## Plano de acao pos-Wave 7

Quando as referencias chegarem, o plano de acao deve ser anexado a esta Wave 5A ou criado como documento complementar em `02-Process/`, sem alterar runtime automaticamente.

| Item | Pergunta de decisao | Saida esperada |
|---|---|---|
| Benchmark de clareza | O que a referencia explica melhor que o F1 atual? | Ajuste de narrativa, titulo, ordem ou legenda |
| Benchmark visual | Que padrao visual Winning aparece melhor na referencia? | Regra de slide master/layout-base |
| Benchmark de estrutura | A referencia organiza funil/handoff/metas de forma mais util? | Mudanca proposta em layout ou secao |
| Conversao Do it yourself -> Done for you | O que e instrucao ao cliente e precisa virar entrega pronta? | Texto convertido para resultado, criterio ou decisao |
| Gaps da Wave 5A | Qual gap confirmado a referencia ajuda a resolver? | Acao concreta ligada ao gap |
| Nao copiar | O que nao deve ir para o F1 porque e aula/manual/workshop? | Lista de descarte justificada |
| Impacto runtime | Precisa mudar registry/task/checklist/skill ou so template? | Plano, nunca aplicacao automatica |
| Prioridade | O que vem antes da Wave 5B visual pesada? | Ordem de execucao |

Template de saida do plano de acao:

| Prioridade | Acao | Origem na referencia | Gap que resolve | Artefato afetado | Precisa aprovacao? |
|---|---|---|---|---|---|
| P0 | Corrigir defeito visual bloqueador | Wave 5A / thumbnail | Slide 4 invertido | Template F1 | Sim |
| P1 | Ajustar layout/narrativa inspirado na referencia | A preencher | A preencher | Template F1 / Wave 5A | Sim |
| P2 | Atualizar contrato de variaveis/limites | A preencher | Layout pode quebrar com texto real | Registry/task/checklist | Sim |

## Template rapido para Thiago enviar referencias

Copiar e preencher um bloco por referencia. O objetivo e ser rapido, nao perfeito.

```text
Artefato alvo:
- F1 master-funnel-diagram-winning

URL da referencia:
- [cole aqui]

URL do original/template atual:
- [cole aqui; se for F1, pode colar a URL do Google Slides master]

O que tem nessa referencia que devo observar:
- [ex.: jeito de explicar funil, ordem da narrativa, visual de etapas, uso de exemplos, forma de mostrar handoff, layout de metas]

Tipo da referencia:
- [Done for you / Do it yourself / nao sei]

Cuidado de adaptacao:
- [ex.: isso ensina o cliente a fazer; no nosso Playbook precisa virar entrega pronta]

O que NAO copiar:
- [ex.: texto de aula, instrucoes internas, linguagem de workshop, partes que nao sao client-facing]

Prioridade:
- [alta / media / baixa]
```

## Pendencias de Wave 7

- Nenhuma referencia do Rafael especifica para F1/funil foi encontrada separada no workspace.
- Ha referencias gerais a DBA, DBS e ROI "a separar", mas nao sao benchmark direto deste F1.
- Pendencia Wave 7: Thiago separar qualquer modelo de funil, mapa de pipeline, handoff ou apresentacao de gestao comercial criada/enviada pelo Rafael antes da Wave 5B se ela existir.
- Quando as referencias forem enviadas, classificar explicitamente se sao `Done for you` ou `Do it yourself` antes de aplicar qualquer aprendizado ao F1.

## Proximo passo objetivo

Proximo passo recomendado:

> Enviar 1-3 referencias reais da Winning usando o template acima, rodar Wave 7 curta para F1, atualizar esta Wave 5A com aprendizados aplicaveis e gerar um plano de acao Wave 5B. So depois executar mudancas no master.

Decisao mantida ate nova evidencia: F1 deve seguir como Google Slides nativo, com base Winning em slide master, 4 layouts-base e QA por thumbnail. A Wave 5B deve primeiro corrigir os defeitos estruturais confirmados (slide 4 invertido, numeracao quebrada, fonte/asset de marca) antes de qualquer polimento visual pesado.
