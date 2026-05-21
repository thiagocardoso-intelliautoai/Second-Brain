---
source: Notion
derived_from: Notion > Winning Sales > Samuel - Automacaos social selling
created_at: 2026-05-16
status: parked
classification: backlog
last_reviewed: 2026-05-16
wave_2_decision: parked-in-winning-sales-projects
---

# Social Selling Automation - Samuel

## Objetivo

Desenhar e validar uma automacao de social selling para a Winning Sales, combinando lista de empresas, pesquisa de decisores, engajamento no LinkedIn, mensagens personalizadas e notificacao quando houver resposta.

## Estado confirmado em 2026-05-16

Fonte: intake de Thiago durante a Wave 1.

- Esta frente nasceu de uma reuniao com Samuel, Head de Conteudo da Winning Sales.
- Samuel explicou o que queria fazer, mas Rafael depois direcionou outra prioridade para Thiago: Playbook de Vendas.
- Portanto, esta frente esta estacionada/backlog no ciclo atual.
- Nao pesquisar ferramentas nem desenhar arquitetura agora, a menos que a prioridade volte.

Classificacao Wave 1:

- manter como arquivo unico estacionado por enquanto;
- decidir na Wave 2 se fica como `parked` em projetos ativos ou se vai para arquivo/backlog.

Decisao Wave 2:

- manter em `04-Work-Winning-Sales/Projects/` como backlog parked;
- nao arquivar ainda porque pode voltar como frente da Winning Sales;
- nao pesquisar ferramentas nem desenhar arquitetura enquanto Playbook for a prioridade;
- nao existe proxima acao tecnica ativa neste ciclo.

## Componentes

1. Lista de empresas semanal.
2. Monitoramento de influenciadores/perfis.
3. Gatilhos de engajamento.
4. Enriquecimento de decisores.
5. Mensagens personalizadas com IA.
6. Entrega de material relevante.
7. Notificacao e registro em planilha.

## Fluxo atual imaginado

1. Samuel gera lista de empresas no LinkedIn.
2. Lista vai para pasta no Drive.
3. Webhook captura.
4. Sistema busca decisor, por exemplo: `Head de vendas {empresa} LinkedIn`.
5. Pode usar Snov, Tavily ou outra ferramenta.
6. IA gera mensagem com base no perfil e site.
7. Sistema escolhe material da Winning para entregar.
8. Analisa posts recentes.
9. Curte ultimos posts se fizer sentido.
10. Comenta se fizer sentido.
11. Solicita conexao ou envia mensagem.
12. Se responder, notifica Samuel + cliente no Telegram e atualiza planilha.

## Decisoes tecnicas abertas

Comparar:

- Agentic workflow + ferramenta de prospeccao LinkedIn;
- Cowork + ferramenta de prospeccao LinkedIn;
- Cowork + conectores Apify;
- n8n + ferramenta de prospeccao LinkedIn.

Ferramentas candidatas:

- sem ferramenta, apenas Cowork;
- Railreach;
- LinkedInHelper;
- Apify;
- Snov;
- Tavily;
- HeyReach.

## Criterios de decisao

- estabilidade no LinkedIn;
- risco de bloqueio;
- custo;
- controle de fluxo;
- qualidade de enriquecimento;
- facilidade de manutencao;
- nivel de personalizacao;
- ponto de revisao humana antes de mensagens sensiveis.

## Proximo passo se a frente voltar

Samuel precisa trazer contexto mais especifico sobre a automacao de lista de empresas.

Thiago precisa comparar caminhos tecnicos e recomendar arquitetura.

Gatilho de retomada:

- Samuel ou Rafael recolocarem esta frente como prioridade;
- existir lista de empresas/processo real a automatizar;
- ficar claro o nivel permitido de automacao no LinkedIn e onde entra revisao humana.

## Fonte

- [[10-Legacy-Imports/Notion-Export-2026-05/Winning-Sales/Winning-Sales-Raw-Import|Winning Sales Raw Import]]

## Links relacionados

- [[04-Work-Winning-Sales/Automation-Ideas|Automation Ideas]]
- [[07-Frameworks-and-Processes/04-Work-Winning-Sales/Assistida-Workflow-Agent|Assistida, Workflow e Agent]]
- [[07-Frameworks-and-Processes/04-Work-Winning-Sales/AI-Automation-Project-Documentation|AI Automation Project Documentation]]
- [[07-Frameworks-and-Processes/04-Work-Winning-Sales/Technology-Mapping-and-Process-Diagnosis|Technology Mapping and Process Diagnosis]]
