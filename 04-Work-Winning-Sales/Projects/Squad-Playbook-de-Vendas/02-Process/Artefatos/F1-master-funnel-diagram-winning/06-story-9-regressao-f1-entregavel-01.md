---
created_at: 2026-05-20
updated_at: 2026-05-20
status: concluida-veredito-sim
story: 9
artifact: F1 master-funnel-diagram-winning
scope: regressao-geracao-review-entregavel-01
source_index: "04-stories-sm.md"
execution_mode: qa-regressao
recommended_agent: "/sm"
runtime_modified: true
drive_modified: true
master_modified: false
---

# Story 9 - Regressao F1 do Entregavel #01

## Resultado da execucao

Story executada em 2026-05-20 com veredito **Sim**.

- Registro de QA: `07-qa-regressao-f1-entregavel-01.md`
- Copia temporaria de QA: `1_l7o56_tjdEn4FUOzvmweEN6V1KXTTaF6sNIcEI87kQ`
- Evidencias: `evidencias-regressao-story9/`
- Master F1 oficial preservado: `1MLhe3oKxK5hvwF6wQG-djjsTZsiOGHckpeGAV99tEMc`
- Revision do master preservada: `YAezrsdvcFdYOA`
- Atualizacao pos-aprovacao de Drive/runtime: `08-registro-drive-runtime-story9.md`

## Atualizacao pos-aprovacao

Em 2026-05-20, apos correcao do alvo operacional, a autorizacao de Drive/runtime foi aplicada nesta Story 9/F1, nao na Story 0/F14.

- Apresentacao QA correta: `https://docs.google.com/presentation/d/1_l7o56_tjdEn4FUOzvmweEN6V1KXTTaF6sNIcEI87kQ/edit`
- Titulo confirmado no Drive: `QA Story 9 - F1 regressao #01 - Cliente QA F1 - 2026-05-20`
- Master oficial confirmado no Drive: `master-funnel-diagram-winning`
- Runtime/checklist/registry atualizados para exigir readback, copia de trabalho, thumbnails e preservacao do master em novas execucoes do F1.
- O registry do F1 continua apontando para o master oficial; a copia QA e evidencia de regressao, nao template promovido.

## Comando para /sm

Use este arquivo como documento de origem. O papel do SM e validar a story, remover ambiguidades e preparar o handoff para execucao por dev/QA.

```text
/sm
*story-checklist
Validar e preparar o handoff da Story 9 usando:
02-Process/Artefatos/F1-master-funnel-diagram-winning/06-story-9-regressao-f1-entregavel-01.md

Objetivo: rodar regressao de geracao/review do entregavel #01 com o runtime atualizado, preservar o master F1 oficial e registrar QA com veredito Sim/Nao.
```

## Resultado esperado

Ao final da execucao deve existir:

- documento `07-qa-regressao-f1-entregavel-01.md`;
- veredito final `Sim` ou `Nao`;
- evidencias visuais dos 5 slides gerados/testados, ou impossibilidade registrada;
- confirmacao explicita de que o master F1 oficial nao foi editado;
- backlog operacional atualizado com o resultado.

## Contexto minimo

F1 ja foi executado, aprovado e promovido:

- Story 5 aplicou a Wave 5B no master oficial.
- Story 6 aprovou o QA pos-execucao em `05-qa-pos-execucao.md`.
- Story 8 reforcou contratos em runtime/checklist/template.

Esta story nao reabre a Wave 5B. Ela testa se o fluxo atual de geracao/review do #01 ainda funciona depois do hardening da Story 8.

## Artefatos e fontes

| Item | Fonte / valor | Uso obrigatorio |
|---|---|---|
| Documento de origem | Este arquivo | Fonte da Story 9 |
| QA aprovado da Wave 5B | `05-qa-pos-execucao.md` | Baseline aprovado |
| Evidencias visuais | `evidencias-wave5b/` | Referencia visual comparativa |
| Registry F1 | `07-Runtime-Squad/templates/TEMPLATE_REGISTRY.md` secao F1 | Confirmar ID, contrato e limites |
| Task #01 | `07-Runtime-Squad/tasks/generate-funnel-kpis.md` | Executar ou simular geracao |
| Checklist #01 | `07-Runtime-Squad/checklists/camada-b-01-funil-kpis.md` | Rodar QA Camada B |
| Master F1 oficial | `1MLhe3oKxK5hvwF6wQG-djjsTZsiOGHckpeGAV99tEMc` | Preservar sem edicao direta |

## Escopo

Inclui:

- regressao do fluxo de geracao/review do entregavel `#01 Funil + KPIs`;
- foco visual obrigatorio no F1 Slides;
- uso de fixture controlado, sem cliente real;
- criacao de copia temporaria de QA quando houver escrita no Drive;
- validacao de placeholders, limites de texto, thumbnails e linguagem client-facing;
- registro de achados com arquivo, slide, range ou passo afetado.

Nao inclui:

- editar o master F1 oficial sem aprovacao explicita de Thiago;
- reabrir a Wave 5B aprovada;
- alterar F11/ROI;
- promover mudanca no Drive;
- refatorar runtime fora de correcao objetiva exigida pela regressao;
- tratar a saida como entrega final de cliente.

## Fixture padrao de regressao

Usar este fixture para reduzir decisao operacional. Ajustar somente se o runtime exigir outro formato de input.

| Campo | Valor |
|---|---|
| Cliente | `Cliente QA F1` |
| Produto | `Plataforma de Automacao SDR` |
| Modo | `customizar` |
| Canais | `ambos` |
| Ticket medio mensal | `12000` |
| Ciclo de venda | `45 dias` |
| Decisores | `CEO, Head de Vendas, Operacoes` |
| Complexidade touch | `mid` |
| Responsavel prospeccao | `SDR Lead` |
| Responsavel handoff | `Executivo de Contas` |

### Funil 1 - Prospeccao Outbound

| Estagio | Nome | Descricao | Criterio de saida |
|---:|---|---|---|
| 01 | Lista ICP | Contas priorizadas por fit, segmento e potencial de receita. | Conta validada com decisor e motivo de abordagem. |
| 02 | Pesquisa | Dor, contexto e gatilho comercial mapeados antes do contato. | Hipotese de dor registrada no CRM. |
| 03 | Abordagem | Sequencia multicanal ativa com mensagem personalizada. | Decisor respondeu ou interagiu com interesse. |
| 04 | Reuniao | Conversa marcada com pauta e objetivo claro. | Reuniao confirmada com decisor certo. |
| 05 | Handoff | Oportunidade passada para vendas com contexto minimo. | AE recebeu dor, impacto, proximo passo e fonte. |

### Funil 2 - Venda Consultiva

| Estagio | Nome | Descricao | Criterio de saida |
|---:|---|---|---|
| 01 | Diagnostico | Entender processo atual, gargalos e impacto financeiro. | Dor prioritaria e impacto estimado confirmados. |
| 02 | Solucao | Conectar capacidades do produto aos gargalos do cliente. | Cliente validou aderencia da solucao proposta. |
| 03 | Business case | Quantificar ganhos, riscos evitados e esforco de implantacao. | Caso aprovado pelos decisores envolvidos. |
| 04 | Proposta | Enviar plano comercial com escopo, preco e prazo. | Proposta revisada sem duvida bloqueante. |
| 05 | Fechamento | Remover pendencias finais e alinhar assinatura. | Contrato assinado ou motivo de perda registrado. |

### Campos de gestao

| Campo | Valor |
|---|---|
| Handoff principal | `Lead sai da prospeccao quando existe reuniao confirmada, dor prioritaria e decisor mapeado para o AE assumir.` |
| Metas numericas | `12 reunioes agendadas/mes; 8 reunioes realizadas/mes; 35% MQL para SQL; ciclo medio ate 45 dias.` |
| Rituais | `Daily 15min para bloqueios; Weekly 60min para funil e metas; 1:1 semanal para coaching.` |
| Decisoes pendentes | `Confirmar fonte de CRM e criterios finais de desqualificacao.` |

## Sequencia de execucao

### Bloco 0 - Preflight

1. Confirmar que este arquivo e o documento de origem.
2. Ler `05-qa-pos-execucao.md` e tratar como baseline aprovado.
3. Ler a secao F1 do `TEMPLATE_REGISTRY.md`.
4. Ler `generate-funnel-kpis.md`.
5. Ler `camada-b-01-funil-kpis.md`.
6. Confirmar que o registry ainda aponta F1 para `1MLhe3oKxK5hvwF6wQG-djjsTZsiOGHckpeGAV99tEMc`.
7. Se o ID divergir, pausar e registrar achado antes de escrever no Drive.

### Bloco A - Preparar input

1. Converter o fixture acima para o formato exigido pelo runtime, se necessario.
2. Validar limites do F1 antes do find-replace:
   - `NOME_CLIENTE` ate 34 caracteres;
   - `NOME_PRODUTO` ate 36 caracteres;
   - nome de funil ate 28 caracteres;
   - proposito de funil ate 110 caracteres;
   - nome de estagio ate 24 caracteres;
   - descricao e criterio de saida ate 95 caracteres;
   - handoff ate 140 caracteres;
   - metas/rituais/decisoes com 3-5 bullets curtos.
3. Se algum campo exceder limite, resumir o texto e registrar a adaptacao.

### Bloco B - Gerar ou simular

1. Caminho preferencial: executar o fluxo de `generate-funnel-kpis.md` em copia temporaria de QA.
2. Caminho alternativo: se nao houver automacao/permissao, executar smoke controlado com copia temporaria e find-replace manual/simulado.
3. Nunca executar find-replace diretamente no master F1 oficial.
4. Se a execucao real nao for possivel, o veredito nao pode ser `Sim`; registrar `Nao` com motivo objetivo e proximo desbloqueio.

### Bloco C - QA visual e textual

Validar os 5 slides gerados/testados:

- render dos 5 slides existe;
- Google Slides continua nativo/editavel;
- numeracao `01`, `02`, `03`, `04`, `05` nao quebra nos slides 2, 3 e 4;
- nenhum texto esta invertido, espelhado, rotacionado indevidamente ou cortado;
- nao ha overflow em titulos, cards, tabelas, handoff, metas, rituais ou decisoes;
- slide 2 mostra fluxo e handoff, nao inventario solto;
- slide 5 comunica gestao executiva;
- nao sobra placeholder visivel;
- nao aparece linguagem interna como `template`, `placeholder`, `agent`, `regra operacional`, ID tecnico ou instrucao de workshop/aula;
- identidade Winning permanece coerente com a Wave 5B aprovada.

Comparar contra `evidencias-wave5b/` apenas para detectar regressao. Nao refazer auditoria visual ja aprovada.

### Bloco D - Registro final

Criar `07-qa-regressao-f1-entregavel-01.md` com:

- data da regressao;
- fonte usada;
- fixture usado;
- tipo de execucao: real, smoke ou simulada;
- link/ID da copia temporaria, se existir;
- evidencias visuais;
- checklist de QA;
- achados;
- veredito `Sim` ou `Nao`;
- confirmacao de preservacao do master F1;
- proximos passos.

Atualizar `02-Process/Backlog-Operacional-Atual.md` com o status final da Story 9.

## Criterios de aceite

A regressao passa como `Sim` somente se:

- o master F1 oficial foi preservado;
- o fluxo usou o master F1 correto como origem;
- os 5 slides foram inspecionados por thumbnail/preview ou evidencia equivalente;
- nao ha placeholder, overflow, numeracao quebrada, texto invertido ou linguagem interna no F1 final testado;
- regras novas da Story 8 foram aplicadas na pratica;
- o documento de QA da regressao existe e contem veredito final.

## Criterios de Nao

Registrar veredito `Nao` se:

- o ID do master F1 divergir do registry;
- nao houver permissao para gerar copia temporaria nem alternativa de smoke test;
- a regressao exigir editar o master F1 oficial sem aprovacao;
- qualquer slide tiver placeholder visivel, overflow, numeracao quebrada, texto invertido ou linguagem interna;
- a evidencia visual nao puder ser obtida;
- o runtime ignorar os limites e checks adicionados na Story 8.

## Definition of Done

A Story 9 termina quando:

- `07-qa-regressao-f1-entregavel-01.md` existe;
- o veredito final esta registrado como `Sim` ou `Nao`;
- evidencias visuais foram registradas ou a impossibilidade foi explicada;
- o master F1 foi preservado, salvo aprovacao explicita de correcao/promocao;
- qualquer falha virou achado objetivo com arquivo/slide/range afetado;
- `Backlog-Operacional-Atual.md` foi atualizado.

## Proximo comando esperado

```text
Executar Story 9 - Regressao F1 do Entregavel #01
```
