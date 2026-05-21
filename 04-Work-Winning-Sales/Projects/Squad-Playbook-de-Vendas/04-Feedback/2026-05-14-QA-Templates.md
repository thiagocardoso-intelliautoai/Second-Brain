---
source: "D:\\1AWinningSales-Projetos\\squadfactory\\squads\\playbook-comercial-squad\\docs\\wave4.2-template-qa.md + original prompt recovery"
created_at: 2026-05-16
updated_at: 2026-05-17
qa_date: 2026-05-14
status: qa-protocol
feedback_type: quality-review
related_output: Playbook templates and template registry
---

# QA Templates - 2026-05-14

## O que esta nota e agora

Esta nota preserva a destilacao do QA integrado de 2026-05-14 e adiciona o protocolo que faltou no prompt original:

> validar, um artefato por vez, se subagents + skills + MCP conseguem preencher variaveis sem substituir texto fixo indevidamente, gerar textao que estoura layout, ou quebrar formulas, validacoes, logica condicional e referencias cruzadas.

Regra central: cada analise termina com veredito obrigatorio **Sim** ou **Nao**. Nao usar "depende" como resposta final.

## Decisao registrada no QA original

O QA integrado registrou:

```text
Pronto para piloto end-to-end controlado.
```

Isso significa que os templates e contratos locais nao tinham bloqueadores remanescentes depois das correcoes daquela onda. Nao significa que as melhorias de Wave 4, Wave 5 e Wave 6 ja foram feitas.

## O que foi validado em 2026-05-14

- 14 templates logicos do registry + auxiliares F5 Slides e F12 Slides.
- Arquivos operacionais abriram por Drive ID.
- Arquivos sao Google Workspace nativos.
- O conector/plugin conseguiu ler texto, estrutura ou thumbnails de amostra.
- Registry, tasks, agents e checklists ficaram alinhados apos correcoes.
- Wrappers `.codex` e `.claude` foram sincronizados com `agents/*.md`.
- Validacao de compatibilidade passou com 7 agents.

Validacoes locais registradas:

```powershell
node scripts\validate-template-registry.js --require-p0
node scripts\validate-template-registry.js --strict-drive-ids
node scripts\validate-platform-compatibility.js
```

Resultado:

- PASS.
- PASS.
- PASS.

## Bloqueadores e pendencias herdadas

Bloqueadores remanescentes registrados no QA original:

- nenhum bloqueador remanescente apos sincronizacao final dos wrappers e rerun das validacoes.

Pendencias importantes:

- reconfirmar parent folders com a conta owner/consultor, porque a conta do conector usada no QA nao abriu a raiz nem `Templates Master`;
- ajustar timezone de algumas Sheets para `America/Sao_Paulo` se um fluxo futuro depender de datas/horarios em formulas;
- fazer revisao visual humana opcional dos thumbnails finais antes de demonstracao externa.

## Protocolo geral de QA tecnico

Aplicar a um artefato por vez.

Antes de avaliar:

- identificar template, Drive ID, agent dono, task dona, skills usadas, checklist afetado e registry correspondente;
- registrar se a validacao foi via MCP, plugin/conector ou fallback manual;
- nao alterar o template durante a analise;
- separar fato observado de inferencia;
- listar evidencias suficientes para sustentar o veredito.

Pergunta obrigatoria:

```text
Os subagents + skills + MCP conseguem preencher as variaveis deste artefato sem:
1. substituir texto fixo indevidamente;
2. gerar texto longo que estoura layout;
3. quebrar formulas, validacoes, logica condicional ou referencias cruzadas;
4. deixar placeholders remanescentes;
5. apagar estrutura fixa que deveria continuar no template?
```

Formato minimo de resposta:

| Campo | Resposta |
|---|---|
| Artefato | nome + tipo + Drive ID |
| Agent/task/skill | arquivos envolvidos |
| Metodo de validacao | MCP, plugin, manual ou misto |
| Evidencias | lista curta |
| Riscos encontrados | lista curta |
| Correcao exigida | sim/nao + onde |
| Veredito final | Sim ou Nao |

Definicao do veredito:

- **Sim**: o artefato pode ser preenchido pelo fluxo atual sem quebrar contrato, layout ou logica relevante.
- **Nao**: ha risco concreto de quebra, lacuna de capacidade, placeholder sem dono, layout vulneravel ou dependencia sem fallback claro.

Proibido responder:

- "depende";
- "provavelmente";
- "parece ok" sem evidencias;
- "ok se o consultor revisar" como substituto de veredito tecnico.

## Analise 1 - Apresentacoes

Escopo: Google Slides e PPTX de referencia, uma apresentacao por vez.

Chunking obrigatorio:

- ate 30 slides por chunk;
- se a apresentacao tiver mais de 30 slides, emitir veredito parcial por chunk e veredito final da apresentacao;
- nao misturar DBA, DBS, proposta, battle cards ou provas sociais no mesmo diagnostico.

Checklist por apresentacao:

- Drive ID ou path confirmado;
- template-master identificado no registry;
- agent/task/skill/checklist responsaveis localizados;
- Design System Winning lido quando a analise envolver visual;
- placeholders listados;
- slides opcionais identificados;
- numeracao hardcoded identificada;
- imagens, icones e graficos classificados como fixos ou variaveis;
- estrategia de batch find-replace confirmada;
- fallback manual existe se MCP Slides nao suportar a operacao.

Checklist por slide:

| Criterio | Pergunta |
|---|---|
| Texto fixo | O texto fixo esta protegido contra find-replace indevido? |
| Variaveis | Todo placeholder tem dono, fonte e limite de tamanho? |
| Densidade | O conteudo variavel cabe sem virar textao? |
| Layout | O grid aguenta variacao curta/media/longa? |
| Tipografia | A hierarquia continua legivel apos substituicao? |
| Imagens | Existe regra para inserir, substituir ou manter imagem? |
| Shapes | Shapes variaveis podem ser editados sem apagar estrutura? |
| Numeracao | Numeros sao automaticos/derivados ou hardcoded ruim? |
| Identidade | O slide segue regra do Design System Winning? |
| Narrativa | O slide continua apresentavel por consultor em call real? |

Prompt operacional - Slides:

```text
Analise esta apresentacao do Squad Playbook Comercial, uma apresentacao por vez.

Objetivo: decidir se subagents + skills + MCP conseguem preencher variaveis sem substituir texto fixo indevidamente, gerar textao que estoura layout, quebrar estrutura visual ou deixar placeholders remanescentes.

Se a apresentacao tiver mais de 30 slides, divida em chunks de 30 slides. Para cada chunk, emita veredito parcial Sim/Nao. Ao final, emita veredito final Sim/Nao para a apresentacao inteira. Nao responda "depende".

Antes de avaliar visual, leia o Design System Winning:
D:\1AWinningSales-Projetos\squadfactory\Design System

Para cada slide, avalie:
- texto fixo protegido;
- placeholders e variaveis;
- limite de tamanho de texto;
- risco de overflow;
- grid;
- tipografia;
- cor;
- imagens/icones/graficos;
- shapes e text boxes;
- numeracao;
- narrativa;
- consistencia com identidade Winning.

Mapeie cada elemento como:
- Universal;
- Variavel de apresentacao;
- Variavel de slide;
- Hardcoded ruim.

Ao final, responda:
1. quais slides passam;
2. quais slides falham;
3. quais mudancas sao exigidas no template;
4. quais mudancas sao exigidas em agent/task/skill/checklist;
5. se MCP Slides precisa suportar batch_update_presentation, replaceAllText, insercao de imagens, edicao de shapes/text boxes ou deleteObject;
6. veredito final obrigatorio: Sim ou Nao.
```

## Analise 2 - Sheets

Escopo: Google Sheets e XLSX de referencia, uma planilha por vez.

Granularidade obrigatoria:

- planilha;
- aba;
- intervalo/celula;
- formulas;
- validacoes;
- logica condicional;
- referencias cruzadas.

Checklist por planilha:

- Drive ID ou path confirmado;
- template-master identificado no registry;
- agent/task/skill/checklist responsaveis localizados;
- abas obrigatorias e opcionais listadas;
- formulas criticas identificadas;
- validacoes de dados identificadas;
- formatacao condicional identificada;
- referencias cruzadas entre abas identificadas;
- locale/timezone checados quando afetam formulas;
- fallback manual existe se MCP Sheets nao suportar a operacao.

Checklist por aba/celula:

| Criterio | Pergunta |
|---|---|
| Texto fixo | O label fixo esta protegido? |
| Input | Celulas de input estao claras e nao confundem formula? |
| Formula | A formula continua parseavel no locale certo? |
| Validacao | Dropdowns/regras sobrevivem a duplicacao e preenchimento? |
| Condicional | Formatacao condicional continua apontando para os intervalos certos? |
| Referencia cruzada | Links entre abas e entregaveis continuam coerentes? |
| Placeholder | Todo placeholder tem dono e tipo esperado? |
| Limpeza | Linhas/abas nao usadas podem ser removidas sem quebrar referencias? |

Prompt operacional - Sheets:

```text
Analise esta planilha do Squad Playbook Comercial, uma planilha por vez.

Objetivo: decidir se subagents + skills + MCP conseguem preencher variaveis sem substituir texto fixo indevidamente, quebrar formulas, validacoes, logica condicional, referencias cruzadas ou deixar placeholders remanescentes.

Avalie por:
- planilha;
- aba;
- intervalo/celula;
- formula;
- validacao;
- logica condicional;
- referencia cruzada.

Para cada aba, liste:
- celulas fixas que nao devem mudar;
- celulas variaveis;
- formulas criticas;
- intervalos de validacao;
- dependencias com outras abas;
- dependencias com outros entregaveis do squad.

Teste mentalmente ou via ferramenta disponivel:
- formulas com dados de exemplo;
- locale e separador correto;
- comportamento quando uma opcao nao se aplica;
- limpeza de linhas/abas opcionais.

Para o caso Low/Mid/High touch, compare:
1. aba dinamica;
2. tres abas separadas;
3. alternativa mais simples.

Ao final, responda:
1. o que passa;
2. o que falha;
3. mudancas exigidas no template;
4. mudancas exigidas em agent/task/skill/checklist/registry;
5. operacoes MCP Sheets necessarias;
6. veredito final obrigatorio: Sim ou Nao.
```

## Analise 3 - Docs

Escopo: Google Docs e DOCX de referencia, um documento por vez.

Granularidade obrigatoria:

- documento;
- secao;
- tabela;
- bullet;
- variavel;
- paginacao;
- TOC;
- formatacao.

Checklist por documento:

- Drive ID ou path confirmado;
- template-master identificado no registry;
- agent/task/skill/checklist responsaveis localizados;
- secoes fixas e variaveis listadas;
- tabelas com colunas fixas/variaveis mapeadas;
- bullets com tamanho esperado definido;
- TOC/paginacao considerados;
- estilos do documento preservados;
- fallback manual existe se MCP Docs nao suportar a operacao.

Checklist por secao/variavel:

| Criterio | Pergunta |
|---|---|
| Texto fixo | A estrutura fixa fica intacta apos preenchimento? |
| Variavel | A variavel tem fonte, dono e limite de tamanho? |
| Tabela | Linhas/colunas podem crescer sem quebrar leitura? |
| Bullets | Bullets ficam concisos e nao viram paragrafo longo? |
| Paginacao | Quebras de pagina e cabecalhos continuam aceitaveis? |
| TOC | Sumario precisa atualizar automaticamente ou manualmente? |
| Formatacao | Estilos sobrevivem ao find-replace? |
| Placeholder | Sobra `{{...}}` no documento final? |

Prompt operacional - Docs:

```text
Analise este documento do Squad Playbook Comercial, um documento por vez.

Objetivo: decidir se subagents + skills + MCP conseguem preencher variaveis sem substituir texto fixo indevidamente, quebrar tabela, bullet, paginacao, TOC, formatacao ou deixar placeholders remanescentes.

Avalie por:
- documento;
- secao;
- tabela;
- bullet;
- variavel;
- paginacao;
- TOC;
- formatacao.

Para cada secao, liste:
- texto fixo que deve permanecer;
- variaveis;
- fonte esperada de cada variavel;
- limite de tamanho;
- risco de textao;
- formato esperado de tabela ou lista;
- estilos que precisam ser preservados.

Valide:
- se o find-replace preserva estilos;
- se tabelas continuam legiveis;
- se bullets continuam concisos;
- se paginacao e TOC nao ficam quebrados;
- se todos os placeholders foram resolvidos.

Ao final, responda:
1. o que passa;
2. o que falha;
3. mudancas exigidas no template;
4. mudancas exigidas em agent/task/skill/checklist/registry;
5. operacoes MCP Docs necessarias;
6. veredito final obrigatorio: Sim ou Nao.
```

## Verificacao de MCP por tipo

| Tipo | Operacoes minimas para aprovar |
|---|---|
| Slides | duplicar master, `replaceAllText`, `batch_update_presentation`, editar shapes/text boxes, inserir/substituir imagens, deletar slides opcionais, validar placeholders |
| Sheets | duplicar/criar sheet, criar abas, escrever valores, preservar formulas, validar formulas, criar/validar dropdowns, preservar formatacao condicional, ler celulas/abas |
| Docs | duplicar/criar doc, substituir texto, preservar estilos, editar tabelas, inserir listas, ler estrutura, validar placeholders |
| Drive | copiar templates, criar pastas, mover outputs, listar arquivos, registrar links finais |

Se o MCP nao cobrir uma operacao critica, o veredito pode ser **Sim** somente se houver fallback manual claro, testavel e aceitavel para o consultor. Caso contrario, **Nao**.

## Implicacao para as proximas waves

Este feedback muda o Project OS do Playbook, nao o Strategy OS.

Fatos confirmados:

- o QA de 2026-05-14 nao registrou bloqueadores remanescentes;
- o squad estava pronto para piloto end-to-end controlado;
- ainda existem pendencias locais de permissao/pastas, timezone e revisao visual opcional.

Inferencias da IA:

- a proxima iteracao nao deve recomecar o squad;
- Wave 4 e Wave 5 podem alterar templates e contratos, entao precisam passar por Wave 3 antes da mudanca e por este protocolo como QA gate antes de piloto;
- melhoria visual so deve virar bloqueadora se afetar demonstracao, consultor usuario ou cliente.

Deve atualizar quando o protocolo for aplicado:

- [ ] Project OS / cockpit
- [ ] `templates/TEMPLATE_REGISTRY.md`
- [ ] agent/task/skill/checklist afetado no runtime novo `07-Runtime-Squad/`
- [ ] output original no runtime novo, repo legado ou Google Workspace, conforme origem
- [ ] log de decisao no Second Brain

## Perguntas para Thiago

- Qual artefato deve receber primeiro este QA Sim/Nao: KPI Sheet, DBA, DBS, proposta, funil ou prospeccao?
- Quem vai ser o revisor humano final: Thiago, Rafael ou consultor usuario?
