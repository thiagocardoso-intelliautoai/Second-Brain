---
created_at: 2026-05-20
updated_at: 2026-05-21
status: active
classification: execution-backlog
scope: stories-waves-governance
drive_modified: true
runtime_modified: true
---

# Backlog Operacional Atual - Stories x Waves

## Papel deste documento

Este backlog e a fila operacional curta do Playbook de Vendas. Ele existe para parar a confusao entre `stories` e `waves` e dizer o que deve ser executado em seguida.

Cockpit principal:

- `02-Process/00-Cockpit/STATUS-ATUAL.md`

Regra base:

- F1 foi tratado por stories dentro de `02-Process/Artefatos/F1-master-funnel-diagram-winning/04-stories-sm.md`.
- F2 agora tem stories-espelho em `02-Process/Artefatos/F2-master-kpis-sheet-winning/00-stories-espelho.md`, apontando para as Waves 3, 4 e 6.
- F11 agora tem stories-espelho em `02-Process/Artefatos/F11-master-roi-calculator-winning/07-stories-espelho.md`, apontando para a frente ROI ja concluida.
- Daqui para frente, cada execucao concreta deve ter uma story como documento de origem. Wave so agrupa, marca historico ou cria checkpoint.
- Quando um artefato usar os dois formatos, a story deve apontar para a wave correspondente e a wave deve apontar para a story correspondente.
- Conversa de chat, mapa de contexto, referencia solta ou insight de benchmark nao autorizam execucao sozinhos.

## Contrato de execucao

Antes de executar qualquer mudanca material, registrar ou confirmar:

| Campo | Regra |
|---|---|
| Documento de origem | Story validada pelo SM; wave so como marco relacionado |
| Artefato alvo | F1, F2, F11 ou outro artefato explicitamente nomeado |
| Modo | `read-only`, `sandbox`, `runtime-docs`, `promocao-master` ou `qa` |
| Documento espelho | Quando houver story + wave, os dois documentos precisam se linkar |
| Permissao de Drive | Qualquer alteracao em Google Drive/Slides/Sheets precisa de aprovacao explicita |
| Evidencia esperada | Validacao local, smoke test, thumbnails, ranges lidos ou log de QA conforme o artefato |

## Fila atual recomendada

| Ordem | Frente | Documento de origem | Status | Proximo passo |
|---:|---|---|---|---|
| 1 | Cockpit operacional | `00-Cockpit/STATUS-ATUAL.md` | Ativo em 2026-05-21 | Abrir este cockpit antes de qualquer nova execucao |
| 2 | Governanca stories x waves | Este backlog + cockpit | Concluida nesta atualizacao | Story e unidade de execucao; wave e marco historico/checkpoint |
| 3 | F2 `master-kpis-sheet-winning` | `Artefatos/F2-master-kpis-sheet-winning/00-stories-espelho.md` | Concluida em 2026-05-20 | Usar F2-S01/F2-S02/F2-S03 como historico; proxima mudanca exige story nova |
| 4 | F11 `master-roi-calculator-winning` | `Artefatos/F11-master-roi-calculator-winning/07-stories-espelho.md` | Concluida em 2026-05-20 | Usar F11-S01/F11-S02/F11-S03 como historico; geracao real exige story nova |
| 5 | F1 regressao do entregavel #01 | `Artefatos/F1-master-funnel-diagram-winning/06-story-9-regressao-f1-entregavel-01.md` | Concluida em 2026-05-20 | QA registrado em `07-qa-regressao-f1-entregavel-01.md`; runtime/Drive registrados em `08-registro-drive-runtime-story9.md`; copia QA `1_l7o56_tjdEn4FUOzvmweEN6V1KXTTaF6sNIcEI87kQ`; master F1 preservado |

## Estado dos artefatos

### F1 - `master-funnel-diagram-winning`

Formato usado ate aqui: stories.

Estado:

- Stories 1-4 concluiram preparacao da Wave 5B.
- Story 5 executou a Wave 5B e promoveu o master F1.
- Story 6 aprovou QA pos-execucao.
- Story 8 reforcou contratos de runtime/checklist/template sem alterar Google Slides.
- Story 7 gerou documento proprio para F11/ROI; sandbox F11 v2, QA F11-W6, promocao por registry e atualizacao runtime foram executados fora do F1.
- Story 9 foi executada em `02-Process/Artefatos/F1-master-funnel-diagram-winning/06-story-9-regressao-f1-entregavel-01.md`, registrada em `02-Process/Artefatos/F1-master-funnel-diagram-winning/07-qa-regressao-f1-entregavel-01.md` e aprovada com veredito `Sim`.
- Apos aprovacao de Drive/runtime, a Story 9 tambem registrou `08-registro-drive-runtime-story9.md`; o runtime do #01 agora exige readback do master/copia, thumbnails dos 5 slides e preservacao explicita do master em modo QA/sandbox.

Regra:

- Novas execucoes do F1 devem nascer como story explicita.
- Se a nova execucao for chamada de Wave 6/regressao, ela deve apontar para as stories F1 ja concluidas.
- A regressao F1 nao reabriu a Wave 5B nem editou o master F1; ela validou em smoke real que o runtime/contrato atualizado gera/revisa o F1 do #01 corretamente.

### F2 - `master-kpis-sheet-winning`

Formato usado ate aqui: waves; formato operacional atual: stories-espelho.

Estado:

- Wave 3 concluiu contrato e auditoria do F2 em modo read-only.
- Wave 4 criou/aprovou sandbox F2 v2 com `KPIs` + `PROSPECÇÃO`.
- Wave 6 aprovou QA da sandbox e liberou promocao.
- Em 2026-05-20, a promocao foi executada por registry; apos normalizacao de pasta no Drive, o F2 oficial atual passou a ser `1uMch8PIUm_M3DkuAKxYRgjWdpbpxDsKzjLMSjlLup3g`.
- O master F2 original `13YLWDeRIXpo7iHaM4N4JCdn3yx17fGiKAJ5bJZvYebo` foi preservado como referencia historica; o conteudo dele nao foi alterado nesta promocao.
- Atualizacao metadata em 2026-05-20: o arquivo antigo foi renomeado no Drive para `master-kpis-sheet-winning (historico pre-Wave 6)` e o arquivo oficial foi normalizado via Sheets API para `master-kpis-sheet-winning`.
- Organizacao no Drive confirmada em 2026-05-20: a pasta `Templates Master/01-funil-kpis` contem o F2 oficial `1uMch...` e a subpasta `_historico-nao-oficial(apagar futuramente)`.
- As Waves 3, 4 e 6 foram espelhadas em `02-Process/Artefatos/F2-master-kpis-sheet-winning/00-stories-espelho.md`.

Regra:

- A proxima execucao material do F2, se existir, deve ser organizacao de pasta no Drive ou QA de geracao real, nao nova auditoria da Wave 4/6.
- Nao reexecutar Waves 3, 4 ou 6 sem motivo novo e story nova.

### F11 - `master-roi-calculator-winning`

Formato usado ate aqui: wave propria em `02-Process/Artefatos/F11-master-roi-calculator-winning/00-wave-3-contrato-e-frente-roi.md`; formato operacional atual: stories-espelho em `02-Process/Artefatos/F11-master-roi-calculator-winning/07-stories-espelho.md`.

Estado:

- F11 nasceu como desdobramento da Story 7 do F1, mas agora tem documento proprio.
- O master historico identificado e `1CxI8RtqZifigfam7PhBA8NZVlaorLRSM9cTDUwbL5UY`.
- O F11 oficial atual no registry e `1OWeAadbcnuqcjXVtx8-6S16XAbgKnT4S2NkKwQWu8Zw`.
- REF-02 deve ser tratada como benchmark de ROI, fora do F1.
- A auditoria read-only F11-W3 foi executada em `02-Process/Artefatos/F11-master-roi-calculator-winning/01-auditoria-read-only-f11-w3.md`.
- A auditoria read-only F11-W3 foi aprovada por Thiago em 2026-05-20.
- Nenhuma alteracao no master F11, na REF-02 ou no runtime foi feita nesta auditoria.
- Tentativa automatica criou a copia `1lanCLCZYCB94hLxr0sFxdz13sy8xsK_r7dpVyZwoEp8`, mas a edicao falhou com `403 PERMISSION_DENIED`.
- Thiago enviou copia manual editavel `1OWeAadbcnuqcjXVtx8-6S16XAbgKnT4S2NkKwQWu8Zw`.
- A sandbox F11 v2 foi executada nessa copia manual e esta registrada em `02-Process/Artefatos/F11-master-roi-calculator-winning/02-sandbox-f11-v2-execucao.md`.
- Sandbox atual: `https://docs.google.com/spreadsheets/d/1OWeAadbcnuqcjXVtx8-6S16XAbgKnT4S2NkKwQWu8Zw/edit?usp=sharing`.
- O QA F11-W6 completo foi aprovado em `02-Process/Artefatos/F11-master-roi-calculator-winning/03-qa-f11-w6-sandbox.md`.
- O plano de acao para atualizar o runtime foi criado em `02-Process/Artefatos/F11-master-roi-calculator-winning/04-plano-acao-runtime-f11-v2.md`.
- O plano executavel combinado de promocao F11 v2 + atualizacao runtime foi criado em `02-Process/Artefatos/F11-master-roi-calculator-winning/05-plano-execucao-promocao-runtime-f11-v2.md`.
- Em 2026-05-20, a promocao foi executada por registry: o F11 oficial passou a ser `1OWeAadbcnuqcjXVtx8-6S16XAbgKnT4S2NkKwQWu8Zw`.
- Em 2026-05-20, a metadata foi normalizada via Sheets API: F11 oficial `master-roi-calculator-winning`, historico `master-roi-calculator-winning (historico pre-promocao F11 v2)` e source QA Onda 3 `master-roi-calculator-winning (source QA Onda 3 - nao oficial)`.
- O runtime #09, checklist B09, mini-onboarding, agent specialty e validacoes cross-deliverable foram atualizados para F11 v2.
- Smoke test pos-promocao passou: metadata `pt_BR`/`America/Sao_Paulo`, 7 abas, ranges criticos legiveis, sem comentarios ativos e sem erros visiveis nos ranges varridos.
- F11-S01, F11-S02 e F11-S03 foram criadas como stories-espelho para leitura operacional.

Regra:

- O master historico F11 nao deve ser tratado como oficial atual.
- A proxima geracao real do #09 deve rodar mini-onboarding com premissas reais e QA de caso antes de liberar frase comercial.
- Nao reabrir a frente ROI concluida sem story nova.

## O que nao executar direto

- Nao executar a partir de uma referencia ou benchmark sem story/wave.
- Nao tratar o mapa do squad como fila quando a secao for apenas contexto.
- Nao reabrir F1 como pendente sem contradizer `05-qa-pos-execucao.md`.
- Nao tratar o master F2 antigo `13YLWDeRIXpo7iHaM4N4JCdn3yx17fGiKAJ5bJZvYebo` nem a copia promovida anterior `1TtoiNQHHr3e5okgSAVYofG5qs53UoCLFEDjQMnKHle8` como oficiais atuais; o registry agora aponta para `1uMch8PIUm_M3DkuAKxYRgjWdpbpxDsKzjLMSjlLup3g`.
- Nao editar Drive/master oficial sem aprovacao explicita para aquela execucao.
