---
created_at: 2026-05-18
status: concluida
wave: 2
scope: auditoria-design-system-e-google-workspace
runtime_modified: false
---

# Wave 2 - Auditoria Design System e Google Workspace MCP

## Objetivo

Registrar a auditoria local do Design System Winning Sales e a pesquisa de MCP/conector/plugin para Google Workspace, separando:

1. skills ou MCPs de operacao para Sheets, Drive, Docs e Slides;
2. skills de design para Slides.

Este registro serve como precondicao para a Wave 3.

## Regra de escopo

- Nenhum arquivo do runtime do squad foi alterado nesta wave.
- Este arquivo vive em `02-Process/`, como registro operacional do cockpit.
- Qualquer promocao para `07-Runtime-Squad/` deve ser aprovada separadamente.

## Sumario executivo

Fato confirmado:

- O Design System local cobre marca, voz, tokens, validacao visual e patterns web/prototipo.
- O Design System local nao contem templates nativos de Google Slides, Docs ou Sheets.
- O conector Google Drive disponivel no Codex conseguiu criar, editar, reler, copiar e exportar artefatos Google Workspace em sandbox.
- Slides foi testado com batch update, texto, shape, imagem publica, outline, thumbnail e export PDF.
- Sheets foi testado com batch update, formula, formatacao, validacao e formatacao condicional.
- Docs foi testado com batch update, texto, tabela e readback de paragrafos/tabelas.

Inferencia:

- Para o squad, o Codex Google Drive plugin/conector e uma rota operacional forte no Codex, mas nao resolve portabilidade para Claude Code.
- Para portabilidade Codex + Claude Code, `workspace-mcp` e o melhor candidato primario a testar em ambiente controlado, porque cobre Drive, Docs, Sheets e Slides e declara suporte a Claude Code e Codex.
- Skills externas de design para Slides nao devem ser instaladas agora. O gap real e transformar o Design System local em contrato nativo de Slides na Wave 5.

## Auditoria do Design System local

Fonte auditada:

```text
D:\1AWinningSales-Projetos\squadfactory\Design System
```

Inventario confirmado:

| Tipo | Quantidade |
|---|---:|
| `.md` | 7 |
| `.css` | 1 |
| `.yaml` | 1 |
| `.js` | 1 |
| `.jsx` | 11 |
| `.html` | 2 |
| `.png` | 5 |

Arquivos centrais confirmados:

| Arquivo | Papel |
|---|---|
| `README.md` | Brand book, fundamentos visuais, voz, iconografia e caveats |
| `SKILL.md` | Skill local Winning Sales Design |
| `REFERENCE.md` | Cheatsheet de tokens e lista negra |
| `DESIGN.md` | Especificacao resumida da identidade visual |
| `PATTERNS.md` | Patterns canonicos para nav, hero, cards, botoes, modal, footer e empty state |
| `VALIDATION.md` | Checks manuais/grep para violacoes visuais |
| `colors_and_type.css` | Fonte principal de tokens CSS |
| `tokens.yaml` | Tokens em formato estruturado |
| `tokens.tailwind.js` | Tokens para Tailwind |
| `assets/` | Logos e logomarks |
| `ui_kits/marketing_site/` | Kit marketing inferido |
| `v2/` | Versao web/prototipo mais completa |

Cobertura confirmada:

| Area | Cobertura |
|---|---|
| Marca | Navy/crimson, gradiente assinatura, premium-formal, tipo-led |
| Voz | pt-BR, "voce", primeira pessoa plural, sem emoji, sem exclamacao |
| Tipografia | Jost, Inter, Fraunces, JetBrains/ui mono |
| Layout | 8pt rhythm, containers, whitespace, grid editorial |
| Componentes web | Nav, hero, cards, botoes, eyebrow, modal/form, footer, empty state |
| Validacao | Hex hardcoded, emoji, exclamacao, SVG inline, scale, easing, blur, font hardcoded |

Gaps confirmados:

| Gap | Impacto |
|---|---|
| Nao ha slide master Google Slides nativo | Wave 5 precisa criar contrato visual de Slides antes de redesign |
| Nao ha escala tipografica em pontos para Slides | Risco de texto estourar caixas e layouts |
| Nao ha grid 16:9/4:3 para decks | Risco de inconsistencias entre DBA, DBS, proposta e battle cards |
| Nao ha regras de limite por placeholder visual | Risco de texto variavel quebrar layout |
| Nao ha templates Docs/Sheets nativos no Design System | Para Docs/Sheets, usar Template Registry + Google Drive como fonte operacional |

Observacoes de qualidade:

- O README declara que os kits foram inferidos a partir da marca, sem Figma, telas reais ou type license.
- O diretorio legado `D:\1AWinningSales-Projetos\squadfactory\Design.md winning sales` existe e parece uma versao parcial/legada.
- Foram encontradas ocorrencias de `#fff`, `#000` e `backdrop-filter` fora do nav em exemplos web. Isso nao bloqueia Wave 3, mas deve ser corrigido se o Design System virar fonte de producao web.

## Recomendacao 1 - Operacao MCP/conector/plugin

| Artefato | Recomendacao | Status |
|---|---|---|
| Slides | Codex Google Drive plugin/conector como rota confirmada no Codex; `workspace-mcp` como candidato primario portavel a testar para Claude Code | Codex confirmado; `workspace-mcp` a testar |
| Sheets | Codex Google Drive plugin/conector confirmado; `workspace-mcp` recomendado para portabilidade | Codex confirmado; `workspace-mcp` a testar |
| Drive | Codex Google Drive plugin/conector confirmado para create/search/copy/export; `workspace-mcp` recomendado para portabilidade | Codex confirmado; `workspace-mcp` a testar |
| Docs | Codex Google Drive plugin/conector confirmado; `workspace-mcp` recomendado; `a-bonus/google-docs-mcp` como fallback Docs/Sheets/Drive sem Slides | Codex confirmado; alternativas a testar |

Matriz comparativa:

| Candidato | Tipo | Slides | Sheets | Drive | Docs | Maturidade em 2026-05-18 | Veredito |
|---|---|---:|---:|---:|---:|---|---|
| Codex Google Drive plugin/conector | Plugin/conector ja disponivel | Alta | Alta | Alta | Alta | Confirmado por smoke test real nesta wave | Rota operacional confirmada no Codex |
| `taylorwilsdon/google_workspace_mcp` / Workspace MCP | MCP externo | Alta declarada | Alta declarada | Alta declarada | Alta declarada | 2419 stars, 745 forks, 98 issues, release `v1.21.0`, push 2026-05-17 | Melhor candidato portavel, a testar com OAuth |
| `gemini-cli-extensions/workspace` | Extensao Gemini/MCP | Media/a verificar | Sim | Sim | Sim | 569 stars, release `v0.0.8`, push 2026-05-18 | Bom para Gemini CLI; nao primario para Claude/Codex |
| `ngs/google-mcp-server` | MCP externo | Media | Sim | Sim | Sim | 2 stars, release `v0.4.0`, push 2026-02-13 | Nao primario |
| `a-bonus/google-docs-mcp` | MCP externo | Nao | Alta | Alta | Alta | 537 stars, release `v1.9.0`, push 2026-05-18 | Fallback para Docs/Sheets/Drive; nao resolve prioridade Slides |
| `adexltd/mcp-google-suite` | MCP externo | Nao | Sim | Sim | Sim | 3 stars, release 2025-03-28 | Nao recomendado |

Itens a pesquisar/testar:

- `workspace-mcp` com OAuth real e Claude Code via `claude mcp add`.
- Se `workspace-mcp` permite editar imagens locais em Slides sem URL publica.
- Se `workspace-mcp` expõe thumbnails ou rota equivalente para QA visual em Slides.
- Se `workspace-mcp` suporta copiar decks templates mantendo layouts, masters e object IDs de forma previsivel.

## Recomendacao 2 - Skills de design para Slides

| Item | Decisao |
|---|---|
| Instalar skill externa de design | Nao recomendado agora |
| Fonte visual primaria | Design System local Winning Sales |
| Gap real | Criar contrato nativo de Slides na Wave 5 |
| O que falta | Slide master, layouts por arquetipo, grid, tipografia em pt, regras de imagem, limites por placeholder, QA visual |
| Onde usar na Wave 3 | Como criterio visual e restricao de contrato, nao como template pronto |

Lista do que nao precisa ser instalado agora:

- Skill generica de UI principles.
- Skill generica de design critique.
- Skill generica de PPTX/design.
- Skill externa de "brand" Winning Sales.

Motivo: o Design System local ja cobre marca, voz, tokens e patterns. A lacuna nao e inspiracao visual; e contrato operacional para Google Slides.

## Smoke test Google Workspace

Data: 2026-05-18.

Ambiente testado: Codex Google Drive plugin/conector disponivel nesta sessao.

Artefatos sandbox criados:

| Tipo | Titulo | URL |
|---|---|---|
| Docs | `Wave 2 Sandbox - Docs - 2026-05-18` | https://docs.google.com/document/d/1PSOC2rgpTD-PEwzEfzdDnk1hMIozQ94wnAniwOkFEEs |
| Sheets | `Wave 2 Sandbox - Sheets - 2026-05-18` | https://docs.google.com/spreadsheets/d/1khY0sbG0RBalyLfcAz-Q0QK26Y5jANzJEZOXifKo3Xo |
| Slides | `Wave 2 Sandbox - Slides - 2026-05-18` | https://docs.google.com/presentation/d/1pPSNnpRjcG0Ow7SVGD-wMQwNV8gX5y5xr_ZcuLZ9jF4 |
| Sheets copy | `Wave 2 Sandbox - Sheets Copy - 2026-05-18` | https://docs.google.com/spreadsheets/d/1tlix2maC-mv66MhVsNzgrZvRpdQKdPYkHIf7LD-xhC8 |
| Slides copy | `Wave 2 Sandbox - Slides Copy - 2026-05-18` | https://docs.google.com/presentation/d/1U6gfe2A_XoEL1-L3lKplbOEhrnx_wxQHQ-OImQKN4UE |

Resultados:

| Capacidade | Teste | Resultado |
|---|---|---|
| Drive create | Criar Docs, Sheets e Slides nativos | Confirmado |
| Drive search | Buscar `Wave 2 Sandbox` | Confirmado; retornou os artefatos sandbox |
| Drive copy | Copiar Slides de template e duplicar Sheet em nova planilha | Confirmado |
| Drive export | Exportar Slides para PDF | Confirmado |
| Docs read/write | Inserir texto e reler paragrafos | Confirmado |
| Docs table | Inserir tabela 2x2 e reler estrutura | Confirmado |
| Sheets write | Preencher A1:C4 via batch update | Confirmado |
| Sheets formula | Formula `=B3-B2` calculou `5` | Confirmado |
| Sheets validation | Validacao numerica em B2:B3 | Confirmado |
| Sheets conditional format | Regra em C3 com fundo verde claro | Confirmado |
| Slides batch update | Inserir texto em placeholders, criar shape, inserir texto em shape | Confirmado |
| Slides image | Imagem publica via URL | Confirmado |
| Slides thumbnail | Thumbnail LARGE 1600x900 obtido e baixado localmente | Confirmado |
| Slides local image | Tentativa com imagem local em `image_uris` | Falhou por schema do conector nesta sessao |

Evidencia local gerada:

```text
D:\1A-Projetos-Pessoais\Second Brain\04-Work-Winning-Sales\Projects\Squad-Playbook-de-Vendas\.tmp-wave2-slides-thumbnail.png
```

Veredito do smoke test:

- Codex Google Drive plugin/conector: aprovado como fallback tecnico controlado e rota operacional no Codex.
- Para portabilidade Claude Code/Codex: ainda e necessario testar `workspace-mcp` com OAuth real.
- Para Slides com imagens locais: manter risco aberto ate confirmar comportamento em `workspace-mcp` ou ajustar fluxo para URL publica/Drive-hosted image.

## Plano de instalacao futuro - Workspace MCP

Nao executado nesta wave. Instalar/configurar depende de OAuth e ambiente local do consultor.

Pre-requisitos:

- Python 3.10+.
- `uv`/`uvx`.
- Google Cloud Project.
- OAuth Client ID e Client Secret.
- APIs habilitadas: Google Drive API, Google Slides API, Google Sheets API, Google Docs API.
- Credenciais fora do repo versionado.

Comando proposto para teste Claude Code:

```bash
export GOOGLE_OAUTH_CLIENT_ID="..."
export GOOGLE_OAUTH_CLIENT_SECRET="..."
uvx workspace-mcp --transport streamable-http --tool-tier complete
claude mcp add --transport http workspace-mcp http://localhost:8000/mcp
```

Para Codex:

- Usar config local do consultor.
- Basear-se em `07-Runtime-Squad/.codex/config.example.toml`.
- Nao versionar `config.toml` real nem credenciais.

Teste minimo para `workspace-mcp`:

| Area | Teste minimo |
|---|---|
| Drive | Criar pasta sandbox, copiar template, renomear, exportar |
| Slides | Copiar deck pequeno, `replaceAllText`, criar text box, criar shape, inserir imagem, obter thumbnail ou equivalente |
| Sheets | Criar aba, escrever valores, formula, validacao e formatacao condicional |
| Docs | Criar/copiar doc, substituir texto, inserir tabela, aplicar heading |

## Rollback

Para teste Codex plugin/conector:

- Os artefatos sandbox ficaram no Drive com prefixo `Wave 2 Sandbox`.
- Rollback pratico: apagar esses arquivos manualmente no Drive se nao forem mais necessarios.

Para futuro `workspace-mcp`:

```bash
claude mcp remove workspace-mcp
```

Depois:

- Parar o processo MCP.
- Remover bloco local do Codex config, se criado.
- Revogar acesso OAuth na conta Google.
- Rotacionar ou deletar OAuth Client no GCP se necessario.
- Apagar credenciais locais do MCP apenas com confirmacao humana.

## Riscos para Wave 3

| Risco | Severidade | Tratamento |
|---|---:|---|
| Portabilidade Claude Code ainda nao testada | Alta | Testar `workspace-mcp` antes de depender dele como rota primaria |
| Slides local image falhou no Codex connector | Media | Usar URL publica/Drive-hosted image ou testar `workspace-mcp` |
| Design System nao tem contrato nativo de Slides | Alta | Wave 5 deve criar slide master/contrato visual antes de redesign |
| Sem limites de placeholder por caixa | Alta | Wave 3 deve mapear limite por variavel visual |
| Plugin Codex nao e fonte portavel | Media | Documentar como fallback tecnico, nao como regra primaria universal |

## Links consultados

Fontes locais:

- `D:\1AWinningSales-Projetos\squadfactory\Design System\README.md`
- `D:\1AWinningSales-Projetos\squadfactory\Design System\SKILL.md`
- `D:\1AWinningSales-Projetos\squadfactory\Design System\PATTERNS.md`
- `D:\1AWinningSales-Projetos\squadfactory\Design System\VALIDATION.md`
- `D:\1AWinningSales-Projetos\squadfactory\Design System\tokens.yaml`
- `D:\1AWinningSales-Projetos\squadfactory\Design System\colors_and_type.css`
- `D:\1A-Projetos-Pessoais\Second Brain\04-Work-Winning-Sales\Projects\Squad-Playbook-de-Vendas\07-Runtime-Squad\templates\TEMPLATE_REGISTRY.md`
- `D:\1A-Projetos-Pessoais\Second Brain\04-Work-Winning-Sales\Projects\Squad-Playbook-de-Vendas\07-Runtime-Squad\config\mcp-capabilities.md`
- `D:\1A-Projetos-Pessoais\Second Brain\04-Work-Winning-Sales\Projects\Squad-Playbook-de-Vendas\07-Runtime-Squad\config\mcp-fallback-strategy.md`

Fontes externas:

- https://github.com/taylorwilsdon/google_workspace_mcp
- https://workspacemcp.com/
- https://github.com/googleworkspace/cli
- https://github.com/gemini-cli-extensions/workspace
- https://github.com/ngs/google-mcp-server
- https://github.com/a-bonus/google-docs-mcp
- https://github.com/adexltd/mcp-google-suite
- https://developers.google.com/workspace/slides/api/reference/rest/v1/presentations/batchUpdate
- https://developers.google.com/workspace/slides/api/reference/rest/v1/presentations.pages/getThumbnail
- https://developers.google.com/workspace/sheets/api/reference/rest/v4/spreadsheets/batchUpdate
- https://developers.google.com/workspace/docs/api/reference/rest/v1/documents/batchUpdate
- https://developers.google.com/workspace/drive/api/reference/rest/v3/files/copy
- https://developers.google.com/workspace/guides/build-with-llms

## Decisao para Wave 3

Liberado iniciar Wave 3 em modo read-only para um artefato especifico, desde que:

1. A rota tecnica seja classificada como `Codex confirmado`, `workspace-mcp a testar`, ou `fallback manual`.
2. Cada placeholder visual tenha dono, origem, limite, fallback e risco.
3. Slides nao assuma imagens locais funcionando sem testar a rota final.
4. Design System local seja usado como regra de marca, nao como template de Slides pronto.
