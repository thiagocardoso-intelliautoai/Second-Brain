---
source: "Wave 1 migration execution"
created_at: 2026-05-17
status: legacy-artifacts-manifest
legacy_repo: "D:\\1AWinningSales-Projetos\\squadfactory\\squads\\playbook-comercial-squad"
---

# Artefatos Legados

## Regra

Este arquivo registra o que ficou no repo legado e nao entrou no runtime principal.

Nao copiar estes artefatos para o Second Brain por padrao. Usar como referencia apenas quando uma wave futura precisar auditar output, recuperar logica de geracao ou comparar visual.

## Excluidos por categoria

| Categoria | Local no repo legado | Arquivos | Bytes | Decisao |
|---|---|---:|---:|---|
| Temporarios Wave 2 | `.tmp/` | 7 | 724424 | Manter no legado; nao copiar outputs locais |
| Temporarios Wave 3 | `tmp-wave3/` | 21 | 792950 | Manter no legado; usar apenas para auditoria historica |
| Temporarios Wave 4 | `tmp-wave4/` | 141 | 3047985 | Manter no legado; previews e outputs nao entram no runtime |

## Exemplos de artefatos locais excluidos

`.tmp/`:

- `generate_wave2_pptx.js`
- `generate_wave2_xlsx.py`
- `master-funnel-diagram-winning.pptx`
- `master-funnel-diagram-winning-corrigido.pptx`
- `master-outreach-matrix-winning.xlsx`
- `master-prospecting-guide-winning.docx`
- `master-prospecting-training-winning.pptx`

`tmp-wave3/output/`:

- `master-battle-cards-winning.pptx`
- `master-roi-calculator-winning.xlsx`
- `master-social-proof-slides-winning.pptx`
- `master-social-proof-winning.docx`

`tmp-wave4/output/`:

- `master-dba-template-winning.pptx`
- `master-dbs-template-winning.pptx`
- `master-proposal-deck-winning.pptx`
- `wave4-contact-f7.png`
- `wave4-contact-f8.png`
- `wave4-contact-f9.png`
- `wave4-manifest.json`

`tmp-wave3/preview/` e `tmp-wave4/preview/`:

- previews PNG de slides e planilhas;
- servem para auditoria visual historica;
- nao sao fonte canonica do template.

## Observacao sobre scripts temporarios

Alguns scripts de geracao ainda vivem em `.tmp/` ou `tmp-wave*`.

Decisao da Wave 1: nao promover esses scripts automaticamente para o runtime. Antes de usar de novo, uma wave futura deve decidir se eles viram:

- script canonico em `scripts/`;
- referencia historica mantida no legado;
- material descartavel porque o template final vive no Google Workspace.

