---
created_at: 2026-05-20
updated_at: 2026-05-20
status: sandbox-aprovada-qa-f11-w6
wave: "sandbox-F11-v2"
scope: execucao-sandbox-ref-02
artifact: F11 master-roi-calculator-winning
source_reference_id: "16GiuEoJHGkJeiEwxKmKxnDHK5zAdrPJkVP77hB4A5vs"
attempted_sandbox_id: "1lanCLCZYCB94hLxr0sFxdz13sy8xsK_r7dpVyZwoEp8"
manual_sandbox_id: "1OWeAadbcnuqcjXVtx8-6S16XAbgKnT4S2NkKwQWu8Zw"
runtime_modified: false
drive_modified: "sandbox_only"
master_modified: false
story_mirror: "07-stories-espelho.md#f11-s02---sandbox-e-qa-f11-w6"
---

# Execucao Sandbox F11 v2

## Nota de governanca - 2026-05-21

Esta sandbox historica agora esta espelhada pela story `F11-S02` em `07-stories-espelho.md`.

## Objetivo

Criar e adaptar uma sandbox F11 v2 baseada na REF-02, sem mexer no master atual `master-roi-calculator-winning`.

## Aprovacao recebida

Thiago aprovou a auditoria e autorizou seguir para execucao.

Escopo autorizado:

- usar a REF-02 como base;
- criar/adaptar uma sandbox;
- manter o master F11 atual intocado;
- se a copia automatica falhar, pedir para Thiago copiar manualmente e enviar a URL.

## Tentativa executada

Foi criada uma copia automatica da REF-02:

| Campo | Valor |
|---|---|
| Fonte | `Calculadora_ROI_WinningSales` |
| Fonte ID | `16GiuEoJHGkJeiEwxKmKxnDHK5zAdrPJkVP77hB4A5vs` |
| Copia criada | `1lanCLCZYCB94hLxr0sFxdz13sy8xsK_r7dpVyZwoEp8` |
| URL | `https://docs.google.com/spreadsheets/d/1lanCLCZYCB94hLxr0sFxdz13sy8xsK_r7dpVyZwoEp8/edit?usp=drivesdk` |

Em seguida, a aplicacao do pacote de adaptacao na copia falhou com:

```text
403 PERMISSION_DENIED
The caller does not have permission
```

Interpretacao:

- a copia foi criada, mas o conector de edicao de Google Sheets desta sessao nao tem permissao para alterar essa copia;
- o master F11 atual nao foi alterado;
- a REF-02 original nao foi alterada;
- nenhum arquivo de runtime foi alterado.

## Pacote que estava pronto para aplicar

O pacote de adaptacao planejado incluia:

- renomear a sandbox para `Sandbox F11 v2 - master-roi-calculator-winning - REF-02 base`;
- ajustar timezone para `America/Sao_Paulo`;
- trocar exemplos por placeholders oficiais do #09;
- tornar formulas principais tolerantes a placeholders;
- adicionar aba `7. Saidas tecnicas`;
- criar saidas `RESUMO_*` para proposta/deck;
- preservar o master atual intocado.

## Bloqueio da copia automatica

Para continuar, Thiago precisou criar manualmente uma copia da REF-02 ou ajustar permissao de uma copia existente e enviar a URL editavel.

Preferencia:

1. Abrir a REF-02.
2. Fazer `Arquivo > Fazer uma copia`.
3. Nome sugerido: `Sandbox F11 v2 - master-roi-calculator-winning - REF-02 base`.
4. Garantir que a conta/conector usado nesta sessao consiga editar a copia.
5. Enviar a URL da copia aqui.

## Execucao continuada na copia manual

Thiago enviou a copia manual editavel:

| Campo | Valor |
|---|---|
| Sandbox editavel | `Sandbox F11 v2 - master-roi-calculator-winning - REF-02 base` |
| ID | `1OWeAadbcnuqcjXVtx8-6S16XAbgKnT4S2NkKwQWu8Zw` |
| URL | `https://docs.google.com/spreadsheets/d/1OWeAadbcnuqcjXVtx8-6S16XAbgKnT4S2NkKwQWu8Zw/edit?usp=sharing` |

Alteracoes aplicadas na sandbox:

- titulo atualizado para `Sandbox F11 v2 - master-roi-calculator-winning - REF-02 base`;
- timezone corrigido para `America/Sao_Paulo`;
- exemplos da aba `2. Inputs` convertidos em placeholders oficiais do #09;
- formulas principais do motor ajustadas para tolerar placeholders usando entradas numericas seguras;
- payback/ROI/classificacao ajustados para ficar vazio ou `A definir` enquanto as premissas nao forem preenchidas;
- resumo executivo ajustado para nao gerar frase comercial falsa sem premissas;
- aba `7. Saidas tecnicas` criada;
- named ranges `RESUMO_USUARIOS`, `RESUMO_PAYBACK`, `RESUMO_ROI_ANO_1`, `RESUMO_REDUCAO_TICKETS`, `RESUMO_ECONOMIA_ANUAL` e `RESUMO_FRASE_FINAL` criados;
- master F11 atual preservado sem alteracao;
- REF-02 original preservada sem alteracao;
- runtime preservado sem alteracao.

## QA curto pos-execucao

| Checagem | Resultado |
|---|---|
| Metadata | OK: titulo corrigido, locale `pt_BR`, timezone `America/Sao_Paulo` |
| Abas | OK: 7 abas, incluindo `7. Saidas tecnicas` |
| Inputs | OK: exemplos principais convertidos em placeholders |
| Motor de calculo | OK: sem `#ERROR!`, `#VALUE!` ou `#DIV/0!` nos ranges lidos |
| Payback sem premissas | OK: vazio, nao `999,0 meses` |
| Classificacao sem premissas | OK: `A definir` |
| Resumo executivo sem premissas | OK: mensagens de preenchimento, nao frase comercial falsa |
| `RESUMO_*` | OK: bloco tecnico criado e lido em `7. Saidas tecnicas!A4:D18` |

## QA completo F11-W6

Executado em 2026-05-20:

- `03-qa-f11-w6-sandbox.md`

Resultado:

- veredito final: **Sim**;
- sandbox F11 v2 aprovada como template/base para runtime;
- nenhuma edicao adicional foi feita no QA;
- master F11 atual preservado sem alteracao;
- REF-02 original preservada sem alteracao;
- runtime preservado sem alteracao;
- plano de acao runtime criado em `04-plano-acao-runtime-f11-v2.md`.

## Proximo passo

Aguardar autorizacao explicita para executar o plano de acao runtime F11 v2 ou abrir uma execucao separada de promocao do master.
