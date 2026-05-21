---
created_at: 2026-05-21
updated_at: 2026-05-21
status: concluido
classification: mirror-stories
artifact: F11 master-roi-calculator-winning
official_drive_id: "1OWeAadbcnuqcjXVtx8-6S16XAbgKnT4S2NkKwQWu8Zw"
historical_master_id: "1CxI8RtqZifigfam7PhBA8NZVlaorLRSM9cTDUwbL5UY"
drive_modified: false
runtime_modified: false
---

# Stories-Espelho F11 - `master-roi-calculator-winning`

## Papel deste documento

Este arquivo transforma a frente ROI/F11 ja concluida em stories-espelho. A documentacao original continua valendo como historico, mas a leitura operacional passa a ser por stories.

Nao reexecutar estas stories. Qualquer nova calculadora real de cliente deve nascer como story nova, com premissas reais e QA de caso.

## Snapshot operacional

| Campo | Valor |
|---|---|
| Artefato | F11 `master-roi-calculator-winning` |
| Oficial atual | `1OWeAadbcnuqcjXVtx8-6S16XAbgKnT4S2NkKwQWu8Zw` |
| Historico preservado | `1CxI8RtqZifigfam7PhBA8NZVlaorLRSM9cTDUwbL5UY` |
| Formato | Google Sheets nativo |
| Estrutura oficial | 7 abas, 3 alavancas, cenarios, dashboard e `RESUMO_*` |
| QA final | Promocao/runtime com veredito `Sim` |

## F11-S01 - Auditoria Read-only e Rota F11 v2

Status: concluida.

Documentos espelhados:

- `00-wave-3-contrato-e-frente-roi.md`
- `01-auditoria-read-only-f11-w3.md`

Objetivo:

- Separar ROI do F1, auditar master historico e REF-02 em modo read-only, e recomendar rota F11 v2 antes de qualquer promocao.

Criterios de aceite cumpridos:

- Master historico e REF-02 lidos sem alteracao.
- Comparacao master vs REF-02 documentada.
- Recomendacao de sandbox hibrida baseada na REF-02 aprovada.
- Story 7 do F1 permaneceu apenas como ponte historica.

## F11-S02 - Sandbox e QA F11-W6

Status: concluida.

Documentos espelhados:

- `02-sandbox-f11-v2-execucao.md`
- `03-qa-f11-w6-sandbox.md`
- `04-plano-acao-runtime-f11-v2.md`

Objetivo:

- Criar/adaptar a sandbox F11 v2, validar 7 abas, formulas, cenarios, dashboard e saidas tecnicas antes de promocao.

Criterios de aceite cumpridos:

- Sandbox F11 v2 validada em `1OWeAadbcnuqcjXVtx8-6S16XAbgKnT4S2NkKwQWu8Zw`.
- QA com veredito `Sim`.
- Aba `7. Saidas tecnicas` com `RESUMO_*` confirmada.
- Frase comercial fica neutra quando faltam premissas reais.
- Plano de acao runtime criado.

## F11-S03 - Promocao e Runtime F11 v2

Status: concluida.

Documentos espelhados:

- `05-plano-execucao-promocao-runtime-f11-v2.md`
- `06-registro-promocao-runtime-f11-v2.md`

Objetivo:

- Promover F11 v2 por registry pointer, preservar o master historico e atualizar o runtime #09 para 7 abas e 3 alavancas.

Criterios de aceite cumpridos:

- F11 oficial atual passou a ser `1OWeAadbcnuqcjXVtx8-6S16XAbgKnT4S2NkKwQWu8Zw`.
- Master historico preservado.
- Runtime #09, checklist B09, mini-onboarding, agent specialty, validacao cross-deliverable e wrappers foram atualizados.
- Smoke test pos-promocao passou.
- Validacoes locais passaram.

## Regra daqui para frente

Nova execucao material do F11 deve criar uma story nova e so pode liberar frase comercial quando houver:

- premissas reais;
- fonte registrada;
- periodo e investimento confirmados;
- criterio de payback/ROI aceito;
- QA de caso real.

Enquanto isso nao existir, deck/proposta devem consumir `RESUMO_AVISO_COMERCIAL`, nao promessa de ROI/payback.

