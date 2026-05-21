---
created_at: 2026-05-20
updated_at: 2026-05-20
status: executado-veredito-sim
wave: "promocao-runtime-F11-v2"
scope: promocao-master-e-runtime
artifact: F11 master-roi-calculator-winning
source_docs:
  - "03-qa-f11-w6-sandbox.md"
  - "04-plano-acao-runtime-f11-v2.md"
current_master_id: "1CxI8RtqZifigfam7PhBA8NZVlaorLRSM9cTDUwbL5UY"
promoted_candidate_id: "1OWeAadbcnuqcjXVtx8-6S16XAbgKnT4S2NkKwQWu8Zw"
official_final_id: "1OWeAadbcnuqcjXVtx8-6S16XAbgKnT4S2NkKwQWu8Zw"
promoted_candidate_url: "https://docs.google.com/spreadsheets/d/1OWeAadbcnuqcjXVtx8-6S16XAbgKnT4S2NkKwQWu8Zw/edit?usp=sharing"
runtime_modified: true
drive_modified: false
master_modified: false
execution_doc: "06-registro-promocao-runtime-f11-v2.md"
story_mirror: "07-stories-espelho.md#f11-s03---promocao-e-runtime-f11-v2"
---

# Plano de Execucao - Promocao F11 v2 + Atualizacao Runtime

## Nota de governanca - 2026-05-21

Esta promocao historica agora esta espelhada pela story `F11-S03` em `07-stories-espelho.md`.

## Objetivo

Executar em uma unica frente controlada a virada do F11 v2:

1. promover a sandbox aprovada como fonte oficial do `master-roi-calculator-winning`;
2. atualizar o runtime para gerar e validar o contrato F11 v2;
3. rodar smoke test pos-promocao;
4. registrar evidencias e riscos residuais.

Este plano ainda nao executa a promocao nem altera runtime. Ele e o documento de origem para a proxima execucao.

## Decisao operacional recomendada

Usar **promocao por registry pointer** como caminho principal.

Motivo:

- foi o caminho que funcionou no F2;
- preserva o master antigo como referencia historica;
- evita bloquear a execucao por permissao de copiar, renomear ou mover arquivo no Drive;
- deixa o runtime e o ID oficial coerentes na mesma execucao.

Tentativas de metadata no Drive podem ser feitas como melhoria opcional, mas nao devem bloquear a promocao se o registry estiver correto e o smoke test passar.

## Artefatos envolvidos

| Papel | ID / Arquivo | Decisao |
|---|---|---|
| Master F11 atual | `1CxI8RtqZifigfam7PhBA8NZVlaorLRSM9cTDUwbL5UY` | Preservar como historico, nao editar diretamente. |
| Sandbox F11 v2 aprovada | `1OWeAadbcnuqcjXVtx8-6S16XAbgKnT4S2NkKwQWu8Zw` | Promover por registry pointer. |
| QA aprovado | `03-qa-f11-w6-sandbox.md` | Gate de promocao. |
| Plano runtime | `04-plano-acao-runtime-f11-v2.md` | Base das alteracoes locais. |
| Registry | `07-Runtime-Squad/templates/TEMPLATE_REGISTRY.md` | Atualizar ID oficial e contrato F11 v2. |

## Escopo autorizado quando este plano for executado

Inclui:

- atualizar o registry para apontar F11 ao ID da sandbox aprovada;
- atualizar contrato F11 no registry de 4 para 7 abas;
- atualizar task #09;
- atualizar checklist B09;
- atualizar mini-onboarding do #09;
- rodar validacoes locais disponiveis;
- rodar smoke test no Google Sheets oficial pos-promocao;
- atualizar backlog, docs F11 e indice de links se existir;
- registrar conclusao com veredito.

Nao inclui:

- alterar a REF-02 original;
- editar o master antigo diretamente;
- alterar F1, F2 ou outros masters;
- entregar calculadora final a cliente real;
- rodar geracao real sem fixture/premissas aprovadas;
- fazer refactor amplo do runtime fora dos arquivos listados.

## Arquivos a alterar

### Obrigatorios

| Arquivo | Mudanca |
|---|---|
| `07-Runtime-Squad/templates/TEMPLATE_REGISTRY.md` | Trocar o ID oficial F11 para `1OWeAadbcnuqcjXVtx8-6S16XAbgKnT4S2NkKwQWu8Zw`; atualizar secao F11 para 7 abas, 3 alavancas, cenarios, dashboard e `RESUMO_*`; registrar nota de promocao. |
| `07-Runtime-Squad/tasks/generate-roi-calculator.md` | Reescrever #09 para F11 v2: 7 abas, 3 alavancas, mini-pausas por bloco, QA de premissas reais e aviso comercial. |
| `07-Runtime-Squad/checklists/camada-b-09-calculadora-roi.md` | Atualizar checklist para 7 abas, placeholders seguros, cenarios, dashboard, saidas tecnicas e QA de caso real. |
| `07-Runtime-Squad/tasks/run-mini-onboarding.md` | Expandir mini-onboarding #09 para alavancas, premissas, investimento, periodo, fonte e criterio de payback. |
| `07-Runtime-Squad/skills/mini-onboarding-pattern.md` | Atualizar variacao do #9 para F11 v2. |
| `02-Process/Backlog-Operacional-Atual.md` | Registrar F11 como promocao/runtime executada ou em QA, conforme resultado. |
| `02-Process/Artefatos/F11-master-roi-calculator-winning/00-wave-3-contrato-e-frente-roi.md` | Registrar execucao final da frente. |

### Condicionais

| Arquivo | Quando alterar |
|---|---|
| `03-Outputs/Links-e-Artefatos-Externos.md` | Se existir indice de links ativo, atualizar o link oficial F11. |
| `07-Runtime-Squad/checklists/camada-c-cross-deliverable.md` | Se houver tempo no mesmo patch, adicionar gate entre #09, deck/proposta e aviso comercial. Caso contrario, registrar como melhoria posterior. |

## Ordem de execucao

### Bloco 0 - Preflight

1. Confirmar que o documento de origem e este arquivo.
2. Confirmar que a sandbox aprovada ainda esta acessivel:
   - URL: `https://docs.google.com/spreadsheets/d/1OWeAadbcnuqcjXVtx8-6S16XAbgKnT4S2NkKwQWu8Zw/edit?usp=sharing`
   - abas esperadas: 7.
3. Confirmar que o master antigo sera preservado como historico:
   - `1CxI8RtqZifigfam7PhBA8NZVlaorLRSM9cTDUwbL5UY`.
4. Ler os arquivos runtime alvo antes de editar.

### Bloco A - Promocao por registry

1. Atualizar a tabela principal do registry:
   - F11 passa de `1CxI8RtqZifigfam7PhBA8NZVlaorLRSM9cTDUwbL5UY` para `1OWeAadbcnuqcjXVtx8-6S16XAbgKnT4S2NkKwQWu8Zw`.
2. Atualizar a secao F11 do registry:
   - `Sheets - 7 abas`;
   - `1. Capa`;
   - `2. Inputs`;
   - `3. Motor de Calculo`;
   - `4. Resumo Executivo`;
   - `5. Cenarios`;
   - `6. Dashboard`;
   - `7. Saidas tecnicas`.
3. Registrar nota de promocao:
   - data: 2026-05-20;
   - ID antigo preservado como historico;
   - ID novo oficial;
   - QA F11-W6 como gate.

### Bloco B - Atualizacao runtime

1. Atualizar `generate-roi-calculator.md`:
   - trocar contrato de 4 abas para 7 abas;
   - trocar modelo estreito de tickets/horas por receita, custo e risco;
   - exigir mini-pausas por bloco;
   - exigir teste com dados reais antes de liberar frase comercial;
   - exigir aviso comercial.
2. Atualizar `camada-b-09-calculadora-roi.md`:
   - separar QA de template/sandbox e QA de caso real;
   - validar 7 abas;
   - validar `RESUMO_*` legado e novo;
   - validar cenarios e dashboard;
   - validar ausencia de erro com placeholders.
3. Atualizar `run-mini-onboarding.md`:
   - #09 passa a perguntar por alavancas, premissas, periodo, investimento e fonte.
4. Atualizar `mini-onboarding-pattern.md`:
   - #9 passa a declarar 7 abas e 3 alavancas.
5. Opcional: atualizar `camada-c-cross-deliverable.md`.

### Bloco C - Validacoes locais

Rodar o que existir no workspace:

```powershell
node scripts/validate-template-registry.js
node scripts/validate-template-registry.js --require-p0
node scripts/validate-template-registry.js --strict-drive-ids
node scripts/validate-platform-compatibility.js
```

Se algum script nao existir ou nao for aplicavel, registrar o motivo no documento de conclusao.

Buscar divergencias textuais:

```powershell
rg -n "F11|master-roi|Calculadora ROI|4 abas|tickets|horas|RESUMO_" 07-Runtime-Squad
```

O objetivo e confirmar que nao ficou contradicao ativa dizendo que F11 oficial ainda tem apenas 4 abas.

### Bloco D - Smoke test pos-promocao no Sheets

No Google Sheets oficial promovido:

1. Ler metadata:
   - titulo;
   - locale `pt_BR`;
   - timezone `America/Sao_Paulo`;
   - abas.
2. Ler ranges:
   - `'1. Capa'!B2:F38`;
   - `'2. Inputs'!B7:F37`;
   - `'3. Motor de Calculo'!B7:F32`;
   - `'4. Resumo Executivo'!B5:F31`;
   - `'5. Cenarios'!B6:F20`;
   - `'6. Dashboard'!B6:H42`;
   - `'7. Saidas tecnicas'!A1:D18`.
3. Confirmar:
   - sem comentarios ativos bloqueantes;
   - 7 abas presentes;
   - placeholders oficiais mantidos;
   - formulas com placeholders sem `#ERROR!`, `#VALUE!` ou `#DIV/0!`;
   - `RESUMO_*` presente;
   - resumo sem frase comercial falsa quando faltam premissas.

### Bloco E - Registro final

Criar ou atualizar documento de conclusao da execucao com:

- veredito Sim/Nao;
- arquivos alterados;
- validacoes rodadas;
- smoke test pos-promocao;
- ID oficial F11 final;
- ID historico preservado;
- riscos residuais;
- proximo passo.

Documento sugerido:

- `06-registro-promocao-runtime-f11-v2.md`

Atualizar tambem:

- `Backlog-Operacional-Atual.md`;
- `00-wave-3-contrato-e-frente-roi.md`;
- `04-stories-sm.md`, se precisar refletir a ponte historica da Story 7.

## Definition of Done

A execucao so termina como **Sim** quando:

- F11 oficial no registry aponta para `1OWeAadbcnuqcjXVtx8-6S16XAbgKnT4S2NkKwQWu8Zw`;
- registry descreve F11 v2 com 7 abas;
- task #09 descreve 7 abas e 3 alavancas;
- checklist B09 valida 7 abas, cenarios, dashboard e `RESUMO_*`;
- mini-onboarding #09 coleta premissas suficientes para receita, custo, risco, investimento e fonte;
- validacoes locais possiveis foram executadas;
- smoke test no Sheets oficial passou;
- master antigo foi preservado como historico;
- registro final foi criado.

## Criterios de Nao

O veredito deve ser **Nao** se:

- a sandbox aprovada nao estiver acessivel;
- o registry nao puder ser atualizado;
- os arquivos runtime ficarem contraditorios entre si;
- o smoke test pos-promocao nao conseguir ler as 7 abas;
- aparecer erro de formula nos ranges criticos;
- `RESUMO_*` nao estiver acessivel;
- a execucao exigir editar a REF-02 original ou outro master fora de escopo.

## Rollback operacional

Se a promocao por registry for aplicada e falhar no smoke test:

1. Registrar o erro no documento de conclusao.
2. Restaurar temporariamente o ID F11 no registry para o master historico `1CxI8RtqZifigfam7PhBA8NZVlaorLRSM9cTDUwbL5UY`.
3. Manter as mudancas runtime em estado revisao se elas forem a causa provavel do erro.
4. Nao apagar a sandbox aprovada.
5. Reabrir QA F11-W6 com achado especifico.

## Registro de execucao

Executado em 2026-05-20 com veredito **Sim**.

Evidencias principais:

- registry F11 aponta para `1OWeAadbcnuqcjXVtx8-6S16XAbgKnT4S2NkKwQWu8Zw`;
- master historico `1CxI8RtqZifigfam7PhBA8NZVlaorLRSM9cTDUwbL5UY` preservado;
- runtime #09 e validacoes relacionadas atualizados para F11 v2;
- validacoes locais passaram;
- smoke test pos-promocao no Sheets passou;
- registro final criado em `06-registro-promocao-runtime-f11-v2.md`.
