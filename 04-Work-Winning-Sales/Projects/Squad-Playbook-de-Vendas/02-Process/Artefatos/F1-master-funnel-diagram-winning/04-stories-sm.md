---
created_at: 2026-05-19
updated_at: 2026-05-20
status: story-9-concluida-veredito-sim
artifact: F1 master-funnel-diagram-winning
runtime_modified: true
drive_modified: true
source_agents:
  - architect
  - sm
---

# 04 - Stories SM / Backlog F1

## Papel deste documento

Este documento salva as stories separadas pelo SM para que a execucao posterior seja clara. A partir do QA real em `05-qa-pos-execucao.md`, ele tambem registra que a Wave 5B foi executada, aprovada e promovida no master oficial.

Nota de governanca: este e o backlog de stories do F1. A fila operacional curta do projeto vive em `02-Process/00-Cockpit/STATUS-ATUAL.md` e `02-Process/Backlog-Operacional-Atual.md`. Daqui para frente, story e a unidade de execucao; wave e apenas agrupamento, marco historico ou checkpoint.

As stories estao separadas em:

- preparacao estrategica/documental;
- execucao Wave 5B realizada;
- QA pos-execucao realizado;
- regressao de geracao/review do #01, agora em documento proprio;
- backlogs paralelos que nao devem entrar no F1 agora.

## Snapshot operacional atual

- Stories 1-4: preparacao concluida.
- Story 5: Wave 5B aplicada e promovida no master oficial `1MLhe3oKxK5hvwF6wQG-djjsTZsiOGHckpeGAV99tEMc`.
- Story 6: QA pos-execucao aprovado, incluindo thumbnails finais e stress de find-replace curto/medio/longo.
- Story 7: documento proprio F11 criado; sandbox F11 v2, QA F11-W6, promocao por registry e atualizacao runtime ficaram fora do F1.
- Story 8: concluida como hardening documental do runtime, sem edicao de Google Slides ou F11/ROI.
- Story 9: concluida em `06-story-9-regressao-f1-entregavel-01.md`; QA registrado em `07-qa-regressao-f1-entregavel-01.md` com veredito Sim; master F1 preservado.
- Story 9 pos-aprovacao: Drive/runtime registrados em `08-registro-drive-runtime-story9.md`; copia QA correta e uma apresentacao Google Slides, nao Google Docs.

## Epic A - Preparacao Wave 5B F1

### Story 1 - Estruturar Benchmark e Referencias F1

Status atual: documentacao criada em `00-referencias-e-benchmark.md`; REF-03 foi liberada e analisada.

Como SM, quero registrar as referencias ja enviadas por Thiago e classificar o que pode inspirar o F1, para que o dev nao misture material `Do it yourself` com entregavel `Done for you`.

Entregavel:

- `00-referencias-e-benchmark.md`.

Criterios de aceite:

- REF-01, REF-02, REF-03 e REF-04 estao registradas com URL, tipo, status e decisao.
- REF-01 e REF-04 estao classificadas como `Do it yourself` e entram apenas como adaptacao.
- REF-02 esta separada como benchmark transversal e backlog F11/ROI.
- REF-03 esta registrada como benchmark de conteudo/variaveis e nao como bloqueio.
- Existe matriz clara de "copiar/adaptar/nao copiar".

### Story 2 - Consolidar Auditoria 1 / Wave 5A

Status atual: documentacao criada em `01-auditoria-1-wave5a.md`.

Como SM, quero preservar a Wave 5A ja executada em formato consumivel pelo dev, para que ninguem refaca a auditoria do zero nem trate a Wave 5A como pendente.

Entregavel:

- `01-auditoria-1-wave5a.md`.

Criterios de aceite:

- Documento referencia a Wave 5A original.
- Fatos confirmados e inferencias estao separados.
- Rota Google Slides nativo esta registrada.
- Diagnostico por slide esta resumido e acionavel.
- Mapa Universal / Variavel / Hardcoded esta preservado.
- Bloqueios antes da Wave 5B estao claros.

### Story 3 - Consolidar Escopo Pre-Wave 5B

Status atual: documentacao criada em `02-consolidacao-pre-wave5b.md`.

Como SM, quero separar o que entra, o que nao entra e o que fica pendente antes da Wave 5B, para que o dev execute apenas mudancas aprovadas.

Entregavel:

- `02-consolidacao-pre-wave5b.md`.

Criterios de aceite:

- P0/P1/P2 da Wave 5B estao priorizados.
- Itens fora de escopo estao explicitos.
- Assets/fontes estao tratados como gates; REF-03 ja foi analisada.
- ROI/F11 esta separado do F1.
- Definition of Ready para o dev esta registrada.

### Story 4 - Preparar Plano Tecnico Unico para Dev

Status atual: documentacao criada em `03-plano-de-acao-tecnico.md`.

Como SM, quero entregar ao dev um plano tecnico unico, para que ele consiga executar Wave 5B sem buscar contexto solto no chat.

Entregavel:

- `03-plano-de-acao-tecnico.md`.

Criterios de aceite:

- Plano lista fontes obrigatorias.
- Master alvo e IDs estao claros.
- Layouts-base estao definidos.
- Contrato de placeholders tem limites iniciais.
- Ordem de execucao esta definida.
- Mudancas de runtime aparecem apenas como plano condicionado a aprovacao.
- QA gates e Definition of Done estao claros.

## Epic B - Execucao Wave 5B F1

### Story 5 - Aplicar Wave 5B no F1 Google Slides

Status atual: concluida em 2026-05-19; ver `05-qa-pos-execucao.md`.

Como dev, quero aplicar o plano tecnico no master/copia do F1 em Google Slides, para transformar a auditoria e os benchmarks em uma base visual reutilizavel.

Dependencias resolvidas:

- Story 4 concluida.
- Aprovacao para editar copia de trabalho e promover para o master oficial.
- Asset oficial de logo/wordmark localizado e aplicado.

Criterios de aceite:

- Texto invertido do slide 4 corrigido.
- Numeracao quebrada corrigida nos slides 2, 3 e 4.
- Tipografia Winning aplicada com escala consistente.
- Slide 2 comunica fluxo/handoff, nao apenas inventario.
- Slides 3 e 4 estao legiveis como consulta operacional.
- Slide 5 comunica metas, rituais e decisoes como gestao executiva.
- Deck continua nativo/editavel no Google Slides.
- Nenhuma linguagem Do it yourself vira texto final do cliente.

### Story 6 - QA Pos-Execucao F1

Status atual: concluida em 2026-05-19; ver `05-qa-pos-execucao.md` e `evidencias-wave5b/`.

Como reviewer/QA, quero validar visualmente e tecnicamente o F1 apos a Wave 5B, para liberar entrada na Wave 6 Sim/Nao.

Entregavel:

- `05-qa-pos-execucao.md`, com evidencias reais de baseline, passos intermediarios, final, master promovido e QA find-replace.

Criterios de aceite:

- Thumbnails de todos os slides alterados foram geradas.
- Checklist de QA visual foi preenchido.
- Placeholders foram testados com texto no limite.
- Nenhum texto invertido, overflow ou numeracao quebrada permanece.
- Fatos, pendencias e riscos residuais estao documentados.

## Epic C - Backlogs paralelos

### Story 7 - Criar Frente Separada para Master ROI/F11

Status atual: documento proprio criado; auditoria read-only F11-W3, sandbox F11 v2, QA F11-W6 e promocao/runtime F11 v2 concluidos em 2026-05-20; nao entra no F1.

Como PM/SM, quero separar a melhoria do ROI em uma frente propria, para aproveitar a REF-02 sem contaminar a Wave 5B do F1.

Entregaveis criados:

- `02-Process/Artefatos/F11-master-roi-calculator-winning/00-wave-3-contrato-e-frente-roi.md`.
- `02-Process/Artefatos/F11-master-roi-calculator-winning/01-auditoria-read-only-f11-w3.md`.
- `02-Process/Artefatos/F11-master-roi-calculator-winning/02-sandbox-f11-v2-execucao.md`.
- `02-Process/Artefatos/F11-master-roi-calculator-winning/03-qa-f11-w6-sandbox.md`.
- `02-Process/Artefatos/F11-master-roi-calculator-winning/04-plano-acao-runtime-f11-v2.md`.
- `02-Process/Artefatos/F11-master-roi-calculator-winning/05-plano-execucao-promocao-runtime-f11-v2.md`.
- `02-Process/Artefatos/F11-master-roi-calculator-winning/06-registro-promocao-runtime-f11-v2.md`.

Criterios de aceite:

- REF-02 esta registrada como benchmark principal do ROI.
- Original F11 `1CxI8RtqZifigfam7PhBA8NZVlaorLRSM9cTDUwbL5UY` esta identificado.
- Decisao de duplicar/substituir/aproveitar visualmente e tratada fora do F1.
- Calculos da referencia nao sao alterados sem necessidade.
- Sandbox F11 v2 baseada na REF-02 foi executada em copia manual editavel.
- QA F11-W6 completo foi aprovado com veredito Sim para a sandbox/template.
- Plano de promocao/runtime F11 v2 foi executado com veredito Sim.
- Registry agora aponta F11 para `1OWeAadbcnuqcjXVtx8-6S16XAbgKnT4S2NkKwQWu8Zw`; o master anterior `1CxI8RtqZifigfam7PhBA8NZVlaorLRSM9cTDUwbL5UY` fica historico.
- O runtime do #09 foi atualizado para 7 abas, 3 alavancas, cenarios, dashboard, `RESUMO_*` e aviso comercial.
- Nenhuma alteracao foi feita no F1, na REF-02 original ou no master historico F11.
- Proximo passo ROI/F11 e gerar caso real somente com mini-onboarding de premissas reais e QA de caso.

### Story 8 - Avaliar Mudancas em Runtime, Templates e Checklists

Status atual: concluida em 2026-05-20 no escopo documental/runtime. Nao houve edicao de Google Slides master nem de F11/ROI.

Como architect/SM, quero avaliar quais aprendizados do F1 devem virar regras do squad, para melhorar proximas execucoes sem mexer em runtime sem permissao.

Entregavel:

- Regras permanentes de QA/contrato adicionadas em `TEMPLATE_REGISTRY.md`, `generate-funnel-kpis.md` e `checklists/camada-b-01-funil-kpis.md`.

Criterios de aceite:

- Cada mudanca proposta tem motivo e arquivo alvo.
- Nao ha edicao de Drive, Google Slides master ou F11/ROI.
- Regras novas preservam portabilidade Codex/Claude.
- Checklist inclui overflow, numeracao, texto invertido e identidade Winning.

## Epic D - Regressao F1 / Entregavel #01

### Story 9 - Regressao F1 do Entregavel #01

Status atual: concluida em 2026-05-20 com veredito Sim.

Documento separado:

- `06-story-9-regressao-f1-entregavel-01.md`
- `07-qa-regressao-f1-entregavel-01.md`

Resumo:

- validou geracao/review do F1 do entregavel #01 com runtime/contrato atualizado;
- preservou o master F1 oficial;
- registrou QA de regressao com veredito Sim;
- atualizou runtime/checklist/registry para exigir readback, thumbnails e preservacao do master em novas execucoes.

## Ordem recomendada de execucao

1. Tratar Stories 1-6 como concluidas para o F1.
2. Usar `05-qa-pos-execucao.md` como fonte de verdade da Wave 5B aprovada.
3. Usar `02-Process/Artefatos/F11-master-roi-calculator-winning/00-wave-3-contrato-e-frente-roi.md` como frente separada de ROI/F11.
4. Tratar `06-story-9-regressao-f1-entregavel-01.md` e `07-qa-regressao-f1-entregavel-01.md` como regressao F1 aprovada.
5. Usar os contratos reforcados da Story 8 em toda nova geracao/revisao do entregavel #01.
