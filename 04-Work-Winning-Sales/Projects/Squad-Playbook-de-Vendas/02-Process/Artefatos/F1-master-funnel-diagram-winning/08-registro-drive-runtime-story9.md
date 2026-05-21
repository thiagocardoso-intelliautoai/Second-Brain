---
created_at: 2026-05-20
updated_at: 2026-05-20
status: concluido
story: 9
artifact: F1 master-funnel-diagram-winning
scope: registro-pos-aprovacao-drive-runtime
drive_modified: true
runtime_modified: true
master_modified: false
veredito: Sim
---

# Registro Drive/Runtime - Story 9 F1

## Decisao operacional

Esta atualizacao corrige o alvo da aprovacao: a autorizacao de Drive/runtime vale para a Story 9/F1, nao para a Story 0/F14.

## Drive

| Papel | Valor | Status |
|---|---|---|
| Master F1 oficial | `1MLhe3oKxK5hvwF6wQG-djjsTZsiOGHckpeGAV99tEMc` | Preservado |
| Titulo do master | `master-funnel-diagram-winning` | Confirmado por readback |
| Revision do master | `YAezrsdvcFdYOA` | Preservada |
| Copia QA Story 9 | `1_l7o56_tjdEn4FUOzvmweEN6V1KXTTaF6sNIcEI87kQ` | Criada e validada |
| URL QA | `https://docs.google.com/presentation/d/1_l7o56_tjdEn4FUOzvmweEN6V1KXTTaF6sNIcEI87kQ/edit` | Evidencia |
| Titulo QA | `QA Story 9 - F1 regressao #01 - Cliente QA F1 - 2026-05-20` | Confirmado por readback |
| Revision QA | `MB3ivD2qch0-gQ` | Confirmada por readback |

Nao houve promocao de novo ID no registry. A copia QA e evidencia de regressao, nao master oficial.

## Runtime atualizado

Arquivos atualizados para incorporar o aprendizado da Story 9:

- `07-Runtime-Squad/tasks/generate-funnel-kpis.md`
- `07-Runtime-Squad/checklists/camada-b-01-funil-kpis.md`
- `07-Runtime-Squad/templates/TEMPLATE_REGISTRY.md`
- `02-Process/Backlog-Operacional-Atual.md`
- `02-Process/Artefatos/F1-master-funnel-diagram-winning/04-stories-sm.md`
- `03-Outputs/Links-e-Artefatos-Externos.md`
- `02-Process/Mapa-do-Squad-e-Repo-Externo.md`

## Regra que passa a valer

Toda nova execucao material do F1 deve:

1. Confirmar que o registry aponta para `1MLhe3oKxK5hvwF6wQG-djjsTZsiOGHckpeGAV99tEMc`.
2. Criar ou usar uma copia de trabalho, nunca executar find-replace direto no master.
3. Registrar ID, titulo e revision do master antes/depois.
4. Registrar ID, titulo e revision da copia/output.
5. Validar 0 placeholders remanescentes por readback.
6. Gerar thumbnails dos 5 slides e salvar evidencia local ou linkavel.
7. Manter o registry inalterado, salvo aprovacao explicita de promocao de master.

## Nao realizado

- Nao foi editado o master F1 oficial.
- Nao foi promovida a copia QA como template oficial.
- Nao foi alterado F2 Sheets.
- Nao foi executada geracao end-to-end completa do entregavel #01; esta Story 9 foi regressao/smoke real do F1 Slides.
