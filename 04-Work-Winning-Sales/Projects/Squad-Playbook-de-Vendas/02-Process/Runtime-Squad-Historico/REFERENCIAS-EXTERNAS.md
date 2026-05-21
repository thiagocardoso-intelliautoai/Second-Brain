---
source: "Wave 1 migration execution"
created_at: 2026-05-17
status: external-references-map
scan_terms:
  - "D:\\"
  - "C:\\"
  - "http://"
  - "https://"
  - "drive.google"
  - "docs.google"
  - "Design System"
  - "Design.md winning sales"
  - "Notion"
  - "Downloads"
  - "tmp-wave"
---

# Referencias Externas

## Regra

Este mapa classifica referencias fora do runtime. Ele nao copia conteudo externo.

## Dependencias locais

| Referencia | Onde aparece | Status | Acao |
|---|---|---|---|
| `D:\1AWinningSales-Projetos\squadfactory\Design System` | Project OS e prompt preservado das Waves 2/5 | Existe | Tratar como Design System atual para auditoria futura |
| `D:\1AWinningSales-Projetos\squadfactory\Design.md winning sales` | `02-Process/Runtime-Squad-Historico/template-factory-plan.md` | Existe, mas parece versao legada/parcial | A verificar antes de redesenho ou auditoria de design |
| `tmp-wave4/build_wave4_decks.mjs` | `scripts/validate-template-client-facing.js` | Resolvido como target legado opcional | O validador retorna `SKIP` com exit code `0` quando o arquivo nao existe no runtime |
| `tmp-wave4/output/*.pptx` e `tmp-wave4/preview/` | `02-Process/Runtime-Squad-Historico/template-factory-plan.md` | Mantido no legado | Usar apenas para auditoria historica |

Observacao: tanto `Design System` quanto `Design.md winning sales` existem localmente. A Wave 1 nao decidiu qual e canonico; a regra operacional permanece usar `Design System` como padrao ate auditoria da Wave 2 ou Wave 5.

## Google Workspace

| Referencia | Onde aparece | Status | Acao |
|---|---|---|---|
| Pastas `Squad Playbook Comercial`, `Templates Master` e subpastas | `templates/TEMPLATE_REGISTRY.md` | Registradas por Drive ID | Reconfirmar governanca/pasta owner quando houver Wave 2 MCP |
| Links Google Slides F1, F5, F7, F8, F9, F10, F12 | `templates/TEMPLATE_REGISTRY.md`, `02-Process/Runtime-Squad-Historico/wave4.2-template-qa.md` | Registrados e validados por ID no QA antigo | Nao copiar; usar Drive como fonte do artefato final |
| Links Google Sheets F2, F4, F6, F11, F13 | `templates/TEMPLATE_REGISTRY.md`, `02-Process/Runtime-Squad-Historico/wave4.2-template-qa.md` | Registrados e validados por ID no QA antigo | Nao copiar; validar acesso de edicao antes de alterar |
| Links Google Docs F3, F5 Doc, F12 Doc, F14 | `templates/TEMPLATE_REGISTRY.md`, `02-Process/Runtime-Squad-Historico/wave4.2-template-qa.md` | Registrados e validados por ID no QA antigo | Nao copiar; usar como master nativo |

## URLs externas de schema

| Referencia | Onde aparece | Status | Acao |
|---|---|---|---|
| `http://json-schema.org/draft-07/schema#` | `data/perfil-schema.json` | Fonte externa padrao de JSON Schema | Manter como referencia |
| `https://winningsales.com/schemas/playbook-comercial/perfil.json` | `data/perfil-schema.json` | `$id` do schema | A verificar se existe publicacao real |

## Frameworks externos adicionados

| Referencia | Onde aparece | Status | Acao |
|---|---|---|---|
| `https://github.com/SynkraAI/aiox-core` | Raiz do Active Project: `.aiox-core/`, `.codex/`, `.claude/`, `AGENTS.md`, `.env.example` | AIOX v5.2.7 instalado em 2026-05-18 | Usar como camada de orquestracao/IDE; nao substituir o runtime canonico em `07-Runtime-Squad/` |
| Pacote npm `aiox-core@5.2.7` / `@aiox-squads/core@5.2.7` | Instalacao via `npx aiox-core@5.2.7 install --ci --yes --ide codex` e complemento Claude Code via `--ide claude-code --merge` | Validado com `npx aiox-core@5.2.7 validate` | Manter versao fixa em comandos operacionais ate decisao explicita de update |

## Referencias de origem historica

| Referencia | Onde aparece | Status | Acao |
|---|---|---|---|
| Notion | Agentes/wrappers mencionam estilo de referencia visual, nao dependencia operacional | Nao bloqueia | Sem acao |
| `C:\Users\thiag\Downloads\Melhorar Playbook de vendas Templates.txt` | Project OS fora do runtime | Ja capturado em `01-Inputs/` | Manter como proveniencia |

## Pontos de atencao

- A Wave 1 nao pesquisou MCPs nem ferramentas externas.
- A conta de execucao ainda precisa confirmar acesso de edicao aos masters Google antes de mudancas reais.
- O path `Design.md winning sales` existe, mas tem cara de Design System antigo ou parcial; nao usar como canonico sem comparar.
