---
created_at: 2026-05-21
updated_at: 2026-05-21
status: concluido
classification: mirror-stories
artifact: F2 master-kpis-sheet-winning
official_drive_id: "1uMch8PIUm_M3DkuAKxYRgjWdpbpxDsKzjLMSjlLup3g"
historical_master_id: "13YLWDeRIXpo7iHaM4N4JCdn3yx17fGiKAJ5bJZvYebo"
previous_promoted_copy_id: "1TtoiNQHHr3e5okgSAVYofG5qs53UoCLFEDjQMnKHle8"
drive_modified: false
runtime_modified: false
---

# Stories-Espelho F2 - `master-kpis-sheet-winning`

## Papel deste documento

Este arquivo transforma as Waves 3, 4 e 6 do F2 em stories-espelho para reduzir a confusao operacional.

Nao reexecutar estas stories. Elas existem para apontar de forma limpa para o que ja foi concluido e para definir que novas mudancas do F2 devem nascer como stories novas.

## Snapshot operacional

| Campo | Valor |
|---|---|
| Artefato | F2 `master-kpis-sheet-winning` |
| Oficial atual | `1uMch8PIUm_M3DkuAKxYRgjWdpbpxDsKzjLMSjlLup3g` |
| Formato | Google Sheets nativo |
| Estrutura oficial | 2 abas: `KPIs` + `PROSPECCAO` |
| QA final | Wave 6 com veredito `Sim` |
| Promocao | Registry pointer em 2026-05-20 |

## F2-S01 - Contrato e Auditoria Read-only

Status: concluida.

Wave espelhada:

- `02-Process/Wave-3-Contrato-F2-Master-KPIs-Sheet.md`

Objetivo:

- Mapear contrato do F2 antes de qualquer alteracao: placeholders, formulas, donos, limites, riscos e fallback.

Criterios de aceite cumpridos:

- Execucao read-only.
- Master historico `13YLWDeRIXpo7iHaM4N4JCdn3yx17fGiKAJ5bJZvYebo` lido e documentado.
- Lacunas de rituais, schema e referencia `.xlsx` registradas.
- Nenhuma alteracao em Drive ou runtime nesta story.

## F2-S02 - Sandbox F2 v2 `KPIs + PROSPECCAO`

Status: concluida.

Wave espelhada:

- `02-Process/Wave-4-F2-Master-KPIs-Sheet-v2.md`

Objetivo:

- Criar e validar uma sandbox F2 v2 com aba `KPIs` preservada e uma aba unica de prospeccao, sem seletor dinamico e sem tres abas Low/Mid/High.

Criterios de aceite cumpridos:

- Sandbox criada em `1TtoiNQHHr3e5okgSAVYofG5qs53UoCLFEDjQMnKHle8`.
- Aba `KPIs` preservada.
- Aba `PROSPECCAO` criada como unica, estatica e editavel.
- Runtime atualizado para declarar os novos campos, rituais e validacao de prospeccao.
- Validacoes locais passaram.
- Master historico nao foi editado nesta etapa.

## F2-S03 - QA e Promocao por Registry

Status: concluida.

Wave espelhada:

- `02-Process/Wave-6-QA-F2-Master-KPIs-Sheet-v2.md`

Objetivo:

- Aprovar a sandbox F2 v2, promover o ID oficial por registry e registrar smoke test pos-promocao.

Criterios de aceite cumpridos:

- QA final com veredito `Sim`.
- F2 oficial atual normalizado para `1uMch8PIUm_M3DkuAKxYRgjWdpbpxDsKzjLMSjlLup3g`.
- Registry atualizado.
- Smoke test pos-promocao confirmou metadata, abas `KPIs` + `PROSPECCAO` e ranges criticos.
- Master anterior preservado como historico.

## Regra daqui para frente

Nova execucao material do F2 deve criar uma nova story, com:

- objetivo e fora de escopo;
- Drive ID oficial;
- modo (`read-only`, `sandbox`, `promocao-master` ou `qa`);
- wave relacionada, se houver;
- criterios de aceite;
- evidencia esperada;
- status final.

Nao reabrir Waves 3, 4 ou 6 sem motivo novo e story nova.

