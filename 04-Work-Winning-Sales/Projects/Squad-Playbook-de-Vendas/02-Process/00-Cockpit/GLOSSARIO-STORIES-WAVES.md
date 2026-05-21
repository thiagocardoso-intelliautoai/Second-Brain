---
created_at: 2026-05-21
updated_at: 2026-05-21
status: active
classification: glossary
scope: stories-waves-governance
---

# Glossario - Stories, Waves e Artefatos

## Termos

| Termo | Definicao operacional |
|---|---|
| Story | Unidade minima de execucao. Deve conter objetivo, escopo, fora de escopo, artefato alvo, modo, criterios de aceite, evidencia esperada e status final. |
| Wave | Agrupamento, marco historico ou checkpoint. Nao autoriza execucao sozinha quando nao houver story validada. |
| Artefato | Entregavel ou template do squad, como F1, F2, F11. O codigo F existe para identificar template no registry, nao etapa de trabalho. |
| QA | Gate de validacao com evidencia. Deve terminar com `Sim` ou `Nao`, sem depender de memoria de chat. |
| Promocao | Mudanca que torna uma copia/sandbox o artefato oficial, normalmente por registry pointer ou por edicao autorizada do master. |
| Sandbox | Copia de trabalho/teste. Nao e oficial ate ser promovida explicitamente. |
| Registry | Fonte tecnica dos templates oficiais, Drive IDs e contratos em `07-Runtime-Squad/templates/TEMPLATE_REGISTRY.md`. |
| Story-espelho | Story criada depois do fato para encapsular uma wave antiga ja concluida, sem reexecutar o trabalho. |

## Regra de leitura

- Se precisar saber **o que fazer agora**, leia `00-Cockpit/STATUS-ATUAL.md`.
- Se precisar saber **o que esta concluido**, leia a story ou story-espelho do artefato.
- Se precisar saber **por que uma decisao antiga foi tomada**, leia a wave historica referenciada pela story.
- Se precisar alterar Drive, master, registry ou runtime, crie uma story nova antes.

## Anti-padroes

| Anti-padrao | Regra correta |
|---|---|
| Executar direto de uma conversa | Converter em story antes |
| Usar wave como fila viva | Usar story como fila viva |
| Chamar F1/F2/F11 de etapa | Tratar F1/F2/F11 como artefatos |
| Promover sandbox sem QA | QA `Sim` antes de promocao |
| Alterar master oficial em teste | Criar copia/sandbox primeiro |

