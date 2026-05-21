---
created_at: 2026-05-20
updated_at: 2026-05-20
status: aprovado
story: 9
artifact: F1 master-funnel-diagram-winning
scope: regressao-geracao-review-entregavel-01
veredito: Sim
execution_mode: smoke-real-google-slides
runtime_modified: true
drive_modified: true
master_modified: false
---

# QA Regressao F1 - Entregavel #01

Data: 2026-05-20

Veredito final: **Sim**.

## Origem

Documento de origem:

- `06-story-9-regressao-f1-entregavel-01.md`

Baseline aprovado:

- `05-qa-pos-execucao.md`
- `evidencias-wave5b/`

Runtime/contrato consultado:

- `07-Runtime-Squad/templates/TEMPLATE_REGISTRY.md` secao F1
- `07-Runtime-Squad/tasks/generate-funnel-kpis.md`
- `07-Runtime-Squad/checklists/camada-b-01-funil-kpis.md`

## Artefatos

| Papel | ID / caminho | Status |
|---|---|---|
| Master F1 oficial | `1MLhe3oKxK5hvwF6wQG-djjsTZsiOGHckpeGAV99tEMc` | Preservado sem edicao |
| Revision do master antes/depois | `YAezrsdvcFdYOA` | Sem alteracao detectada |
| Copia temporaria de QA | `1_l7o56_tjdEn4FUOzvmweEN6V1KXTTaF6sNIcEI87kQ` | Usada para smoke real |
| URL da copia | `https://docs.google.com/presentation/d/1_l7o56_tjdEn4FUOzvmweEN6V1KXTTaF6sNIcEI87kQ/edit?usp=drivesdk` | Evidencia de execucao |
| Titulo da copia QA | `QA Story 9 - F1 regressao #01 - Cliente QA F1 - 2026-05-20` | Confirmado por readback pos-aprovacao |
| Revision da copia QA pos-aprovacao | `MB3ivD2qch0-gQ` | Confirmado por readback |
| Evidencias visuais | `evidencias-regressao-story9/` | 5 thumbnails baixados |

## Tipo de execucao

Foi executado um **smoke real em Google Slides**:

1. Leitura do master oficial pelo conector Google Drive/Slides.
2. Criacao de copia temporaria a partir do master oficial.
3. Aplicacao de `replaceAllText` em batch na copia temporaria usando o fixture da Story 9.
4. Readback textual da copia.
5. Geracao de thumbnails grandes dos 5 slides.
6. Download local das imagens via `contentUrl`.
7. Inspecao visual dos 5 PNGs.
8. Nova leitura do master oficial para confirmar revision preservada.

Nao houve edicao direta no master F1 oficial.

## Readback pos-aprovacao

Em 2026-05-20, o alvo foi reconfirmado como Story 9/F1:

- Apresentacao QA lida pelo conector como Google Slides nativo/editavel.
- ID da apresentacao QA: `1_l7o56_tjdEn4FUOzvmweEN6V1KXTTaF6sNIcEI87kQ`.
- Titulo da apresentacao QA: `QA Story 9 - F1 regressao #01 - Cliente QA F1 - 2026-05-20`.
- Master oficial relido como `master-funnel-diagram-winning`, revision `YAezrsdvcFdYOA`.
- Nenhuma promocao de novo ID foi feita no registry; a copia QA permanece apenas como evidencia.
- Runtime/documentos foram atualizados para novas execucoes do F1 exigirem copia de trabalho, readback e thumbnails antes do aceite.

## Fixture usado

| Campo | Valor |
|---|---|
| Cliente | `Cliente QA F1` |
| Produto | `Plataforma de Automacao SDR` |
| Funil 1 | `Prospeccao Outbound` |
| Funil 2 | `Venda Consultiva` |
| Handoff | Lead sai da prospeccao quando existe reuniao confirmada, dor prioritaria e decisor mapeado para o AE assumir. |
| Metas | 12 reunioes agendadas/mes; 8 reunioes realizadas/mes; 35% MQL para SQL; ciclo medio ate 45 dias |
| Rituais | Daily 15min; Weekly 60min; 1:1 semanal |

## Evidencias visuais

Arquivos gerados:

- `evidencias-regressao-story9/slide-01-regressao-story9.png`
- `evidencias-regressao-story9/slide-02-regressao-story9.png`
- `evidencias-regressao-story9/slide-03-regressao-story9.png`
- `evidencias-regressao-story9/slide-04-regressao-story9.png`
- `evidencias-regressao-story9/slide-05-regressao-story9.png`

## Resultado por slide

| Slide | Status | Observacao |
|---:|---|---|
| 1 | OK | Titulo quebra linha de forma controlada; sem placeholder, corte ou colisao. |
| 2 | OK | Numeracao `01..05` preservada nos dois funis; handoff claro; sem overflow. |
| 3 | OK | Funil 1 preenchido; numeracao integra; descricoes e criterios cabem na tabela. |
| 4 | OK | Funil 2 preenchido; numeracao integra; sem texto invertido ou truncado. |
| 5 | OK | Metas, rituais e decisoes cabem nos cards; leitura executiva preservada. |

## Checklist

| Gate | Resultado |
|---|---|
| Master F1 oficial preservado | OK |
| Registry aponta F1 para `1MLhe3oKxK5hvwF6wQG-djjsTZsiOGHckpeGAV99tEMc` | OK |
| Copia temporaria criada antes de find-replace | OK |
| 5 slides renderizados em thumbnails grandes | OK |
| 0 placeholders remanescentes no readback textual | OK |
| Numeracao `01..05` sem quebra nos slides 2, 3 e 4 | OK |
| Sem texto invertido, espelhado ou rotacionado indevidamente | OK |
| Sem overflow bloqueante em titulos, cards, tabelas, handoff, metas, rituais ou decisoes | OK |
| Sem linguagem interna proibida (`template`, `placeholder`, `agent`, IDs tecnicos visiveis) | OK |
| Identidade Winning preservada | OK |

## Achados

Nenhum achado bloqueante.

Observacao nao bloqueante:

- O titulo do slide 1 quebrou linha depois de `Automacao`. A quebra e controlada, legivel e coerente com o contrato de aceitar quebra no titulo/subtitulo para nome de produto.

## Conclusao

A regressao F1 do entregavel #01 passou com veredito **Sim** em smoke real de Google Slides.

O fluxo validou que o master F1 promovido continua utilizavel como origem para copia temporaria, find-replace e QA visual com os contratos reforcados da Story 8.

## Proximos passos

- Manter o master F1 oficial preservado.
- Usar esta regressao como referencia para novas geracoes/reviews do entregavel #01.
- Se uma geracao completa end-to-end do #01 for rodada depois, incluir tambem F2 Sheets no escopo e registrar em documento proprio.
