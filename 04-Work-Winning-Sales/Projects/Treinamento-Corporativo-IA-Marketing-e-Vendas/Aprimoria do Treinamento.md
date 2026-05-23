## Como automatizar seus processos de forma simples, rápida e eficiente

1. Introdução

2. Mapeamento do processos 

3. Escolher o processo que mais vai tirar gerar retorno sobre investimento

3. Identificar se é o melhor processo a ser seguido (com AI)

4. Fazer uma pesquisa de soluçskills ões já criadas desse problema que vc ta tendo

5. Criar a skill generica de marketing ou vendas para eles entenderem o conceito de skill na prática

## AI para vendas:
Executando o processo ensinado junto com ele criando uma skill:
1. Executando o processo ensinado no modulo 1 junto com ele criando uma skill que eles decidirem fazer sentido.
2. Entregar 9 skills de Vendas

### Organizar skills em:
- Gestor Comercial B2B: Head of Sales, Coordenador Comercial, Gerente Comercial, Sales Manager, Diretor Comercial, VP of Sales, CRO em empresa menor

- Especialista em Desenvolvimento de Pipeline: SDR, BDR, Pré-vendas, Sales Development, Business Development, Outbound Sales, Inbound Sales, Lead Generation

- Executivo de Contas e Receita: Account Executive, Closer, Vendedor Consultivo, Executivo de Contas, Consultor Comercial, Inside Sales, Field Sales, Enterprise Sales, Account Manager, Key Account Manager

#### Gestor Comercial B2B:

**Skill 1: Radar Semanal de Forecast e Deal Risk**
*Lê CRM, histórico de vendas e sinais de oportunidade para mostrar quais deals colocam o forecast em risco, onde há pipeline inflado e quais ações o gestor precisa cobrar na semana.*

**Valor gerado (dados):**
- **84% das empresas B2B relatam desafios relevantes de forecast**, principalmente por risco de deal invisível, CRM otimista, processo manual e dificuldade de transformar pipeline em previsão confiável; a skill cria uma rotina semanal de inspeção antes do problema virar surpresa executiva (Norwest B2B Sales & Marketing Benchmark Report, 2025).
- **IA em vendas tem alto potencial em forecast, insights comerciais e action hubs**, mas o valor aparece quando o gestor transforma sinais em ação: revisar commit, corrigir close date, destravar deal, remover oportunidade sem evidência e preparar a forecast call com perguntas objetivas (Gartner, AI in Sales, acesso 2026-05-23).
- **Padrões open-source já operacionalizam forecast como workflow de gestão**, não como relatório passivo: `forecast-discipline`, `deal-quality-model`, `crm-hygiene`, `pipeline_forecast` e `opportunity_health_score` usam tiers de forecast, score de deal, critérios de higiene, aging e retro de acurácia (gtmagents/gtm-agents; crmy-ai/crmy, GitHub, acesso 2026-05-23).

**Skill 2: Coach de Performance Comercial por Rep**
*Transforma calls, atividades e conversões por etapa em diagnóstico de habilidade por vendedor, pauta de 1:1 e plano de coaching prático.*

**Valor gerado (dados):**
- **Gestores comerciais B2B são cobrados por coaching, deal unblocking, pipeline hygiene, forecast, ramp e performance do time**, mas costumam operar com pouco tempo e muita informação espalhada; a skill transforma evidência de CRM e calls em plano de desenvolvimento por vendedor (Apollo, Sales Manager Duties, acesso 2026-05-23).
- **Produtividade comercial com IA depende de redesenhar o processo, não só automatizar tarefas isoladas**; uma rotina de coaching baseada em call review, conversão por etapa e comportamento observado melhora a capacidade do time sem depender apenas de contratar mais vendedores (Bain, AI Is Transforming Productivity, but Sales Remains a New Frontier, 2025).
- **Padrões open-source já tratam coaching como skill executável**, com rubrica, call review, scorecard, reinforcement drills, plano de coaching, KPIs e calibração gerencial; isso permite transformar 1:1s em melhoria mensurável de discovery, avanço de etapa, objeções e fechamento (gtmagents/gtm-agents `coaching-framework`, `call-review-kit`, `reinforcement-drills`; GitHub, acesso 2026-05-23).

**Skill 3: Radar de Cobertura de Pipeline e Alocação Comercial**
*Calcula se o time tem pipeline suficiente para bater meta e recomenda onde concentrar esforço por rep, segmento, canal ou etapa do funil.*

**Valor gerado (dados):**
- **Forecast bom sem cobertura suficiente só antecipa a frustração**: gestores precisam cruzar quota, pipeline, win rate, ticket médio, ciclo de vendas e produtividade por rep para saber quanto pipeline novo precisa ser criado antes do trimestre virar emergência operacional.
- **70% das empresas têm dificuldade de integrar sales plays ao CRM e às tecnologias de receita**, o que prejudica execução, segmentação, coaching e produtividade; a skill transforma dados comerciais em orientação semanal de foco, não em mais uma visão estática de dashboard (Bain & Company, 2025).
- **Padrões open-source já combinam análise de pipeline, capacidade e alocação comercial**: `capacity-modeling`, `quota-health`, `territory-optimization`, `pipeline-analysis`, `performance-review` e alertas de stalled leads apontam para workflows de cobertura, produtividade por rep e priorização de esforço comercial (gtmagents/gtm-agents; Dominien/hubspot-sales-agent; iPythoning/b2b-sdr-agent-template, GitHub, acesso 2026-05-23).

**Nota para o engenheiro de Automação e IA**

Não criar uma skill genérica de "gestão comercial". Criar 3 `SKILL.md` separados, cada um com trigger, inputs obrigatórios, workflow, output em Markdown e critérios de qualidade. A v1 pode funcionar com export CSV do CRM + transcrições/notes em Markdown; integração direta com HubSpot/Salesforce fica para depois do piloto.

**Referências GitHub/open-source para reaproveitar:**
- `gtmagents/gtm-agents`: usar `forecast-discipline`, `deal-quality-model` e `crm-hygiene` como base do **Radar Semanal de Forecast e Deal Risk**.
- `gtmagents/gtm-agents`: usar `coaching-framework`, `call-review-kit` e `reinforcement-drills` como base do **Coach de Performance Comercial por Rep**.
- `gtmagents/gtm-agents`: usar `capacity-modeling`, `quota-health` e `territory-optimization` como base do **Radar de Cobertura de Pipeline e Alocação Comercial**.
- `crmy-ai/crmy`: aproveitar os padrões de `pipeline_forecast`, `opportunity_health_score` e contexto de CRM para estruturar score de oportunidade.
- `Dominien/hubspot-sales-agent`: aproveitar ideias de `pipeline-analysis` e `performance-review` para leitura de HubSpot/CRM.
- `iPythoning/b2b-sdr-agent-template`: aproveitar o padrão de reports recorrentes, stalled leads e alertas operacionais.

**Sugestão objetiva de criação:**
1. **Radar Semanal de Forecast e Deal Risk:** input = CRM export + meta + etapas + histórico; output = forecast brief, tabela de deals em risco, correções de CRM, perguntas para a forecast call e ação por owner.
2. **Coach de Performance Comercial por Rep:** input = transcrições de calls + CRM por rep + scorecard comercial; output = diagnóstico por habilidade, pauta de 1:1, plano de coaching de 2 semanas e drills de treino.
3. **Radar de Cobertura de Pipeline e Alocação Comercial:** input = quota + pipeline atual + win rate + ticket médio + ciclo médio + produtividade por rep; output = mapa de cobertura, gap por período, prioridade por segmento/rep e plano semanal de geração de pipeline.
4. **Quality gate comum:** toda recomendação precisa citar a evidência usada, separar fato/inferência/recomendação e terminar com owner, próximo passo e métrica impactada.
5. **Primeiro piloto:** rodar com 1 gestor, 1 time e dados reais de 2-4 semanas. Só automatizar integração depois que o output for útil sem explicação do consultor.

#### Especialista em Desenvolvimento de Pipeline:

**Skill 1: Copiloto de vendas**
AI que tras 6 pontos diferentes de abordagens personalizados para entrar em contato com o prospect
(Já tenho os 6 prompts que foi extraído do copiloto que o Victor Bagiio criou e foi criado o esquelo dessa skill nesse chat do codex:''Extrair 6 prompts de prospecção'' )

**Valor gerado (dados):**
- **Personalização aumenta resposta:** emails customizados têm **10% mais open rate** e **2x mais reply rate** que templates padrão; a Outreach também aponta que IA pode reduzir o preparo de outreach de cerca de **20 minutos para 2 minutos** por conta/prospect *(Outreach, Sales 2025, acesso 2026-05-23)*.
- **O gargalo do SDR/BDR é contexto em escala:** no State of Sales 2026 da Salesforce, reps passam **60% do tempo em trabalho não diretamente vendedor**, enquanto clientes cobram mais ROI mensurável e personalização; um copiloto de abordagens transforma pesquisa, sinal e proposta de valor em mensagens revisáveis sem empurrar volume genérico *(Salesforce State of Sales, 2026)*.
- **IA já é percebida como alavanca prática em vendas:** no HubSpot State of Sales 2025, só **8%** dos reps disseram não usar IA; entre usuários, **84%** dizem que IA economiza tempo/otimiza processos, **83%** dizem que ajuda a personalizar interações e **82%** dizem que melhora insights vindos de dados *(HubSpot State of Sales, 2025)*.

**Skill 2: Follow up Estratégico**
*Analisa o prospect, a empresa, o histórico de contato e a oferta para gerar 6 frentes alternativas de follow-up por canal, gatilho e próximo passo, evitando repetição genérica.*

**Valor gerado (dados):**
- **Follow-up rápido captura valor que o funil costuma perder:** a pesquisa de Lead Response Management citada pela XANT/InsideSales mostra que as chances de qualificar um lead são **21x maiores** quando o contato acontece em até **5 minutos** versus 30 minutos; no mesmo relatório, a persistência média observada era baixa, com mediana de **1 tentativa** e média de **2,2 tentativas** entre empresas auditadas *(XANT/InsideSales, Annual Lead Response Report, acesso 2026-05-23)*.
- **Persistência funciona melhor quando vira cadência multicanal com contexto:** a Outreach reporta que são necessários em média **5-7 toques** para alcançar um contato pela primeira vez; a Cognism, analisando sua operação outbound de 2025, encontrou cadências coordenadas de telefone, email e LinkedIn, com **8,98% de reply rate SDR**, **16,06% de conversão para reunião** e **85,94% de meeting held rate** *(Outreach Sales 2025; Cognism State of Outbound 2026)*.
- **O follow-up precisa proteger a reunião, não só insistir no contato:** a Cognism observou que reuniões marcadas com intervalo longo caíam para cerca de **60% de show rate**, enquanto uma sequência simples de nutrição e confirmação elevou show rates para **72%** e depois para faixa de **80-82%**; a skill transforma esse padrão em mensagens com gatilho, canal, timing e próximo passo claro *(Cognism State of Outbound 2026)*.

**Skill 3: Qualificador e Priorizador de Leads/Contas**
*Classifica leads inbound ou listas outbound por fit, intenção, urgência e potencial, gerando uma fila priorizada com próximo melhor passo.*

**Valor gerado (dados):**
- **Qualificação virou gargalo central de geração de pipeline:** a Outreach aponta lead qualification como o desafio nº 1 dos vendedores em 2025 e mostra que **45%** dos times já usam modelo híbrido AI-SDR; a skill reduz o trabalho de detetive antes da abordagem e separa o que deve ser abordado agora, nutrido, enriquecido ou descartado *(Outreach Sales 2025)*.
- **Priorizar melhora velocidade e conversão no inbound:** a Harvard Business Review mostrou que empresas que respondem leads online dentro de **1 hora** têm muito mais chance de qualificar o lead do que empresas que demoram mais; a pesquisa de Lead Response Management/XANT reforça a janela crítica de **5 minutos** com **21x** mais chance de qualificação versus 30 minutos *(HBR, The Short Life of Online Sales Leads; XANT/InsideSales, acesso 2026-05-23)*.
- **Padrões open-source já operacionalizam essa skill:** GooseWorks inclui `inbound-lead-enrichment`, `inbound-lead-qualification`, `inbound-lead-triage`, `apollo-lead-finder` e `company-contact-finder`; o `vercel-labs/lead-agent` captura lead, faz deep research, qualifica e gera email com human-in-the-loop; o `brightdata/ai-lead-generator` busca, enriquece, pontua e sugere abordagem por lead *(GitHub: gooseworks-ai/goose-skills, vercel-labs/lead-agent, brightdata/ai-lead-generator, acesso 2026-05-23)*.

**Nota para o engenheiro de Automação e IA:**
- **Criar como 3 `SKILL.md` separadas e encadeáveis**, não como uma skill gigante: `Qualificador e Priorizador de Leads/Contas` gera a fila e o brief; `Copiloto de vendas` usa esse brief para criar 6 ângulos de abordagem; `Follow up Estratégico` usa histórico + status da cadência para criar 6 próximos toques.
- **Sources GitHub para adaptar:** `gooseworks-ai/goose-skills` como referência para `inbound-lead-enrichment`, `inbound-lead-qualification`, `inbound-lead-triage`, `apollo-lead-finder` e `company-contact-finder`; `vercel-labs/lead-agent` como referência de workflow inbound com pesquisa, qualificação, email e human-in-the-loop; `brightdata/ai-lead-generator` como referência de busca/enriquecimento/score/outreach tip; `gtmagents/gtm-agents` como referência de sales prospecting, cold outreach, social selling, lead qualification e sequências.
- **Ordem de criação sugerida:** começar pela Skill 3, porque ela define schema de lead/conta, ICP fit, score, motivo e próximo passo; depois criar a Skill 1 usando esse schema como input; por último criar a Skill 2 reaproveitando o mesmo contexto + histórico de contato.
- **MVP recomendado:** inputs mínimos = ICP, oferta, persona, lista de leads/contas, histórico de contato e objetivo comercial; output mínimo = score, motivo, próximo passo, ângulo de abordagem, mensagem revisável e nota curta para CRM. Primeira versão deve ser assistida, com aprovação humana antes de enviar mensagem ou gravar no CRM.
- **Teste de qualidade antes de virar material de treinamento:** rodar com 5 leads inbound, 5 contas outbound e 5 prospects parados; avaliar se o output é específico, usa evidência real, tem CTA claro, evita inventar dados, diferencia canal/timing e reduz retrabalho do SDR.

#### Executivo de Contas e Receita:

**Skill 1: Raio-X de Deal MEDDICC + Mutual Action Plan**
*Analisa uma oportunidade real para diagnosticar saúde do deal, gaps de MEDDICC/MEDDPICC, risco de forecast e próximo movimento com evidência de compra.*

**Valor gerado (dados):**
- **69% dos vendedores que usam IA reduzem o ciclo de vendas em média em 1 semana** e **68% dizem que IA ajuda a fechar mais deals**; a skill aplica IA no ponto em que ciclo, forecast e fechamento se encontram: deal review, próximos passos e remoção de bloqueios (LinkedIn Sales Solutions, ROI of AI, 2025).
- **Compradores B2B passam só 17% do tempo de compra falando com fornecedores** e, quando comparam vários fornecedores, apenas 5-6% com cada vendedor; isso aumenta o valor de um MAP vivo, de champion validado e de critérios de decisão explícitos (Gartner, B2B Buying Journey).
- **Padrões open-source já tratam deal health, MEDDICC e MAP como workflow executável**, não como conceito solto: `gtm-enterprise-account-planning` usa MEDDICC, stakeholder map, health check e Mutual Action Plan; `gtm-agents` inclui pipeline health, deal velocity, forecasting e enterprise sales (GitHub, acesso 2026-05-23).

**Skill 2: Discovery-to-Value Case Builder**
*Transforma discovery, transcrição de call e contexto da conta em mapa de dor, impacto financeiro, critérios de decisão e hipótese de valor antes da proposta.*

**Valor gerado (dados):**
- **38% dos vendedores que usam IA para pesquisar leads e empresas economizam mais de 1,5h por semana**, mas a alavanca maior para AE é usar esse contexto para melhorar a qualidade da discovery, não só preparar reunião (LinkedIn Sales Solutions, ROI of AI, 2025).
- **GenAI já é usada em speech analytics para analisar calls, intenção do cliente, comportamentos do vendedor e drivers de conversão**, criando coaching e melhoria de performance a partir de conversas reais (McKinsey, Five ways B2B sales leaders can win with tech and AI, 2025).
- **Padrões reais de call analysis avaliam probing, talk ratio, objeções, dor, orçamento, timeline e próximos passos com scorecards estruturados**, mostrando que a skill deve gerar diagnóstico de venda e gaps de qualificação, não resumo de reunião (Sales Call Analysis System Prompt; `gtm-agents/sales-calls`, GitHub, acesso 2026-05-23).

**Skill 3: Plano de Conta + Expansão por Sinais**
*Cria um plano acionável de conta para expansão, renovação ou land-and-expand usando sinais de saúde, uso, stakeholders, metas do cliente e timing comercial.*

**Valor gerado (dados):**
- **51% dos líderes de vendas com IA dizem que silos tecnológicos atrasam ou limitam iniciativas de IA** e **46% dizem que problemas de qualidade de dados prejudicam vendas**; plano de conta com sinais reduz dependência de informação espalhada e opinião solta (Salesforce State of Sales, 2026).
- **RevOps moderno mede pipeline velocity, deal size, retenção, expansão e feedback loops entre marketing, vendas, produto e customer success**; a skill conecta account management com decisão de receita, não só relacionamento (KPMG, RevOps Redefined, 2025).
- **Padrões open-source de account management já combinam health score, QBR, expansão, stakeholders e renewal strategy**: `account-health-framework` padroniza risco/oportunidade e `expansion-playbook` transforma milestones e uso em plays de upsell/cross-sell com KPIs como attach rate, win rate e cycle time (gtmagents/gtm-agents, GitHub, acesso 2026-05-23).

**Nota para o engenheiro de Automação e AI**

Referências GitHub/open source observadas:
- `github/awesome-copilot` > `gtm-enterprise-account-planning`: melhor referência para a Skill 1. Tem MEDDICC, stakeholder map, health check, Mutual Action Plan e regra prática de MAP parado.
- `zubair-trabzada/ai-sales-team-claude`: boa referência de arquitetura de skills comerciais. Usa orquestrador + subskills para research, qualification, contacts, prep, proposal e objections.
- `gtmagents/gtm-agents`: usar como biblioteca de padrões. Referências úteis: `call-analysis-framework`, `call-review-kit`, `account-health-framework`, `expansion-playbook`, `sales-pipeline`, `deal-velocity` e `forecasting`.
- `brightdata/ai-sdr-bdr-agent`: não copiar o foco SDR, mas reaproveitar a lógica de score por ICP, trigger, contato, timing e CRM sync.
- `Sales Call Analysis System Prompt`: boa referência para rubrica de discovery: probing, talk ratio, objeções, dor, orçamento, timeline e próximos passos.

Sugestão objetiva de criação:
- Criar **3 skills separadas**, não uma skill gigante de "vendas consultivas".
- Cada skill deve ter: trigger claro, inputs obrigatórios, workflow em etapas, output em Markdown e critérios de qualidade.
- MVP sem integração primeiro: vendedor cola CRM notes, transcrição da call, dados da conta e contexto da oferta; a skill devolve diagnóstico e próximo passo.
- Depois integrar com CRM/call recorder apenas para preencher inputs automaticamente.
- Usar sempre score simples: `Verde / Amarelo / Vermelho`, nota 0-100, principais gaps e `next best action`.
- Separar **fatos, inferências e dados faltantes**. Não inventar stakeholder, métrica, budget, sponsor, concorrente ou close date.
- Outputs esperados: deal review + MAP atualizado; discovery scorecard + value hypothesis; account plan + expansion plays.
- Não transformar essas skills em gerador de e-mail ou proposta. A função delas é melhorar decisão comercial, qualificação, avanço de etapa, forecast e expansão.


## AI para Marketing:
1. Executando o processo ensinado no modulo 1 junto com ele criando uma skill que eles decidirem fazer sentido.
2. Entregar 9 skills de marketing 

### Organizar skills em:
- Gestor de Marketing B2B: Head, Coordenador, Gerente, CMO em empresa menor

- Estrategista de Conteúdo e Posicionamento: Product Marketing, Content, Copy, Brand, Social, SEO

- Especialista de Demanda e Growth: Demand Gen, Performance, ABM, Campaigns, Events, Partnerships

#### Gestor de Marketing B2B:
**Skill 1: Diagnóstico Semanal de Pipeline e Forecast de Marketing**
*Lê metas, CRM, campanhas ativas e conversões para mostrar se marketing está no caminho de bater pipeline, onde está o risco e qual ação precisa acontecer agora.*

**Valor gerado (dados):**
- **59% dos CMOs dizem não ter budget suficiente para executar a estratégia em 2025**, mesmo com budgets estabilizados em **7,7% da receita da empresa** — isso força ganho de produtividade via analytics, tecnologia e IA, não só mais gasto *(Gartner CMO Spend Survey, 2025)*.
- **Marketing B2B segue pressionado por pipeline e receita influenciada**, mas recursos limitados podem tirar foco das metas de curto prazo; Forrester aponta que a resposta exige estratégia alinhada e melhoria de processo, não mais atividade solta *(Forrester, B2B Marketing's Top Challenges and Priorities for 2025)*.
- **51% das organizações veem silos de dados como obstáculo central** e só **11% dizem manter dados de CRM de forma meticulosa**; diagnóstico semanal reduz cegueira operacional e melhora forecast antes do problema virar surpresa executiva *(KPMG, RevOps Redefined, 2025)*.

**Skill 2: Priorizador de Campanhas, Canais e Orçamento**
*Classifica campanhas e canais em escalar, manter, corrigir ou pausar, cruzando spend, conversão, pipeline, CAC e qualidade das oportunidades.*

**Valor gerado (dados):**
- **Budget parado + meta subindo = necessidade de realocação inteligente**: Gartner mostra budgets flat em 2025, então a alavanca do gestor passa a ser cortar desperdício e concentrar investimento no que move pipeline *(Gartner CMO Spend Survey, 2025)*.
- **B2B marketers já estão sendo cobrados por revenue influenced, ROAS e pipeline**, não só por clique, lead ou MQL; o Revenue Attribution Report do LinkedIn reforça a conexão entre campanhas e resultado comercial real *(LinkedIn Marketing Solutions, 2025)*.
- **Padrões open-source já operacionalizam esse tipo de skill**: GTM Agents inclui `budget-optimization`, `channel-pacing-guardrails` e `attribution-playbook`; Meta MCP expõe insights, comparação de campanhas, exportação CSV/JSON e attribution tracking para análise assistida por agente *(gtmagents/gtm-agents; brijr/meta-mcp, GitHub, acesso 2026-05-23)*.

**Skill 3: Loop de Alinhamento Marketing-Vendas-Produto**
*Transforma lead quality, feedback de vendas, win/loss, objeções e sinais de produto em ajustes práticos de ICP, handoff, mensagem e enablement.*

**Valor gerado (dados):**
- **Times comerciais precisam alinhar objetivos, métricas e incentivos**, saindo de funis transacionais para um funil comercial integrado com marketing, vendas, produto e CS; KPMG destaca pipeline velocity, deal size, CAC, product feedback loops e account-based success metrics como peças de alinhamento *(KPMG, RevOps Redefined, 2025)*.
- **Mais de 40% dos respondentes de marketing, vendas e customer success apontam gaps de skill e treinamento como barreira à integração das equipes de front-office**; a skill cria um ritual de aprendizagem e ajuste contínuo, não uma reunião solta *(KPMG, RevOps Redefined, 2025)*.
- **Padrões reais de GitHub apontam para ICP scoring, signal library, weekly update, pipeline, wins/losses e enablement**, exatamente os blocos necessários para transformar feedback comercial em decisão de marketing *(KarlRaf/gtm-starter-kit; octavehq/lfgtm; gtmagents/gtm-agents, GitHub, acesso 2026-05-23)*.

#### Estrategista de Conteúdo e Posicionamento:
**Skill 1: Minerador de Voz do Cliente e Sinais de Mercado**
*Transforma calls, CRM, reviews, comentários, concorrentes e pesquisa de mercado em mapa de dores, objeções, linguagem real do comprador e ângulos estratégicos para conteúdo, copy e posicionamento.*

**Valor gerado (dados):**
- **Compradores B2B formam shortlist antes de falar com vendas**; a mensagem precisa vencer no dark funnel, antes do lead levantar a mão *(6sense, B2B Buyer Experience Report, 2025)*.
- **61% dos compradores B2B preferem uma jornada sem vendedor**, mas rejeitam outreach irrelevante; linguagem real do cliente reduz mensagem autocentrada e aumenta relevância percebida *(Gartner, 2025)*.
- **Padrões open-source já tratam Voice of Customer como insumo base de marketing**: ESC Skills usa Message Mining com reviews, calls, Reddit e CRM para gerar Pain Map, Objection Map, Swipe File e Language Map; `product-marketing-context` também força captura de customer language e proof points *(guilhermemarketing/esc-skills; coreyhaines31/marketingskills, GitHub, acesso 2026-05-23)*.

**Skill 2: Message House de Posicionamento Defensável**
*Transforma pesquisa de cliente, concorrência e produto em posicionamento, narrativa GTM, pilares de mensagem, claims, provas e linguagem proibida.*

**Valor gerado (dados):**
- **Product Marketing segue central para posicionamento, messaging, lançamento, colaboração com vendas/produto e receita**, então uma skill de message house ataca uma responsabilidade core do perfil, não uma tarefa periférica *(Product Marketing Alliance, State of Product Marketing Report, 2025)*.
- **Inconsistência entre o que o comprador vê no site e o que ouve de vendas derruba confiança**, especialmente em jornadas self-service; message house cria um sistema comum de mensagem para marketing, vendas e produto *(Gartner, 2025)*.
- **Padrões open-source confirmam o workflow**: `gtm-positioning-strategy`, `product-positioning` e `product-messaging` trabalham triggers como mensagem igual à concorrência, falta de clareza comercial, value props, proof points e hierarquia de mensagens *(github/awesome-copilot; realjaymes/marketingagentskills, GitHub, acesso 2026-05-23)*.

**Skill 3: Brief Estratégico de Conteúdo por Intenção, POV e Prova**
*Cria um briefing de conteúdo B2B que une intenção de busca, buyer journey, tese da marca, prova, diferenciação e plano de distribuição antes de escrever a peça.*

**Valor gerado (dados):**
- **B2B Content Marketing segue pressionado por estratégia, recursos e medição de resultado**, então brief bom reduz retrabalho e aumenta qualidade do conteúdo antes da produção *(Content Marketing Institute, B2B Content Marketing Benchmarks, Budgets, and Trends, 2025)*.
- **AI Search e zero-click reduzem dependência de clique orgânico tradicional**, exigindo conteúdo com autoridade, clareza de entidade, POV e prova, não só keyword stuffing *(Bain, Losing Control: How Zero-Click Search Affects B2B Marketers; BrightEdge, AI Search Shift, 2025)*.
- **Padrões open-source já operacionalizam SEO/content brief**, mas a adaptação de maior valor é adicionar VoC, posicionamento e proof library para evitar conteúdo genérico *(OpenClaudia/openclaudia-skills `seo-content-brief`; gtmagents/gtm-agents, GitHub, acesso 2026-05-23)*.

**Nota para o Engenheiro de Automação e AI:**
- Criar as 3 skills como `SKILL.md` separadas e encadeadas, não como prompts avulsos. Ordem sugerida: primeiro `Minerador de Voz do Cliente`, depois `Message House`, depois `Brief Estratégico de Conteúdo`.
- Para o **Minerador de Voz do Cliente**, usar como base `guilhermemarketing/esc-skills` (Message Mining) e `coreyhaines31/marketingskills` (`product-marketing-context`). Adaptar para aceitar calls, CRM, reviews, comentários e páginas de concorrentes; output obrigatório: Pain Map, Objection Map, Language Swipe File, Proof Gaps e backlog de ângulos.
- Para o **Message House**, usar como base `github/awesome-copilot` (`gtm-positioning-strategy`) + `realjaymes/marketingagentskills` (`product-positioning` e `product-messaging`). Adaptar para entregar positioning statement, narrativa curta, pilares, claims, provas, objeções e lista de termos proibidos.
- Para o **Brief Estratégico de Conteúdo**, usar como base `OpenClaudia/openclaudia-skills` (`seo-content-brief`) e padrões de content pipeline em `gtmagents/gtm-agents`. Adaptar para exigir intenção de busca, POV, VoC, prova, CTA, distribuição e critério de qualidade; não deixar a skill virar "gerador de artigo".
- Gate mínimo de qualidade: toda recomendação precisa apontar fonte, evidência ou hipótese; toda citação de cliente precisa preservar proveniência; e se faltar dado, a skill deve devolver lacunas antes de inventar mensagem.

#### Especialista de Demanda e Growth:
**Skill 1: Inteligência de Conta + Outreach Brief**
*Pesquisa profunda de uma conta-alvo + brief de abordagem pronto pra SDR agir em minutos, ancorado num buying signal real.*

**Valor gerado (dados):**
- **5,2x reply rate** quando a mensagem é ancorada num buying signal específico vs template genérico (18% vs 3,43%) — *(Growthspree, ABM Execution Report, 2026)*
- **70% da jornada de compra B2B é dark funnel**: quando o lead chega sozinho, já tem 2-3 vendors no shortlist — *(ZoomInfo, B2B Buying Signals Guide, 2026)*
- **15-20 min → 2 min por conta**: pesquisa manual vira automática, libera 50-70h em campanhas de 200 contas — *(MarketBetter, 2026 ABM Playbook, 2026)*
- **116% ROI documentado**: caso Madison Logic + AgentSync usando inteligência de conta pra ativar campanhas coordenadas — *(Madison Logic case study, via G2 AI in B2B Marketing, 2026)*
- **31% lift em qualification accuracy** com AI scoring sobre dados enriquecidos vs scoring básico — *(SyncGTM, B2B Sales-Marketing Alignment Playbook, 2026)*
- **Resposta em <1h converte 53%** vs 17% em 24h — speed-to-lead com inteligência é cobertura dupla — *(Lead Response Management Study, MIT/Oldroyd, 2007 — citado em Geisheker 2026)*

**Skill 2: Diagnóstico de Performance + Rebalanceamento de Campanhas**
*Analisa campanhas e canais com dados de funil para recomendar o que escalar, manter, corrigir, pausar ou redistribuir em orçamento.*

**Valor gerado (dados):**
- **78% dos CMOs B2B dizem que provar ROI ficou mais importante nos últimos 2 anos** e **57% dos marketers B2B dizem que as metas de pipeline estão subindo** — a skill transforma pressão por resultado em decisão objetiva de budget, canal e campanha *(LinkedIn Marketing Solutions, 2025/2026)*.
- **QLO no LinkedIn reduziu cost per qualified lead em 39% nos primeiros adotantes** e CVO gerou até **20% mais volume de conversão** em testes iniciais; o padrão é otimizar para lead qualificado e valor de conversão, não só CPL bruto *(LinkedIn Marketing Solutions, Pipeline Acceleration, 2025)*.
- **Padrões open-source já operacionalizam esse tipo de workflow**: `budget-optimization` modela plano vs real, efficiency bands, cenários de realocação e guardrails; `channel-pacing-guardrails` monitora CPL, CAC, ROAS, payback e alertas por canal *(gtmagents/gtm-agents, GitHub, acesso 2026-05-23)*.

**Skill 3: Triage de Sinais de Demanda + Handoff MQL→SQL**
*Transforma leads, eventos, webinars, campanhas, parceiros e sinais de intenção em uma fila priorizada com score, motivo, owner, SLA e próxima ação.*

**Valor gerado (dados):**
- **O maior gargalo da jornada B2B aparece entre MQL e SQL**, com leads levando mais de 3 meses para avançar em média, enquanto a jornada completa dura cerca de **211 dias**; a skill ataca speed-to-lead, aceite comercial e vazamento de demanda *(Dreamdata Benchmark 2025, citado por LinkedIn Marketing Solutions, 2025)*.
- **Demand Gen real hoje inclui lead + account ops: sourcing, scoring, routing, nurturing, parceria com SDRs/AEs e reporte de funnel performance**; esse é exatamente o ponto em que a demanda vira pipeline ou morre no handoff *(Snappr, Lead Demand Generation job description, acesso 2026-05-23)*.
- **Padrões open-source de `lead-scoring`, `revops` e `sla-tracking` usam fit + intent + thresholds + SLA + feedback loop** para qualificar, rotear e calibrar MQL/SQL; é uma skill de operação de receita, não só análise genérica *(AbsolutelySkilled/lead-scoring; gtmagents/gtm-agents, GitHub, acesso 2026-05-23)*.

**Nota para o Engenheiro de Automação e IA**

Não criar essas skills do zero. Use como referência:
- [`gtmagents/gtm-agents`](https://github.com/gtmagents/gtm-agents): olhar principalmente `budget-optimization`, `channel-pacing-guardrails`, `campaign-planning`, `marketing-analytics` e `attribution-playbook` para a Skill 2. O que reaproveitar: leitura de plano vs real, bandas de eficiência, thresholds de CPL/CAC/ROAS/payback, cenários de realocação e tabela final de ação.
- [`AbsolutelySkilled/AbsolutelySkilled`](https://github.com/AbsolutelySkilled/AbsolutelySkilled): olhar `lead-scoring` para a Skill 3. O que reaproveitar: ICP fit, behavioral/intent score, thresholds MQL/SQL, score decay, motivos de qualificação e feedback de rejeição.
- [`sales-skills/sales`](https://github.com/sales-skills/sales): usar como runner-up para blocos de `lead-score`, `intent`, `crm-update`, follow-up e sales analytics. O que reaproveitar: formato de handoff simples para vendas e lógica de próxima ação.

Sugestão objetiva de criação:
- Começar pela Skill 2 porque é mais fácil validar com CSV/planilha: inputs mínimos = `campaign_metrics.csv`, `crm_funnel.csv`, metas por canal e restrições de budget; output obrigatório = tabela `escalar / manter / corrigir / pausar`, motivo, métrica afetada, ação recomendada e risco.
- Depois criar a Skill 3 como roteador de demanda: inputs mínimos = lista de leads/contas, ICP, eventos de engajamento, origem, stage do CRM e SLA comercial; output obrigatório = fila priorizada, score, motivo, owner, SLA, próxima ação e destino (`SDR agora`, `nurture`, `investigar`, `descartar`).
- Integrar as duas com a Skill 1: quando a Skill 3 marcar uma conta como `alta prioridade + alta intenção`, ela deve recomendar rodar **Inteligência de Conta + Outreach Brief** antes do contato SDR.
- Quality gate das duas: nenhuma recomendação pode sair sem dado usado, hipótese, próxima ação e critério de sucesso. Primeiro validar em planilha; só depois pensar em integração com CRM, ads ou automação.
