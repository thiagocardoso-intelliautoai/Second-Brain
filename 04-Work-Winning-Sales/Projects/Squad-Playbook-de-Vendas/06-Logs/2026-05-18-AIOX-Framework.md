---
created_at: 2026-05-18
status: completed
type: framework-integration
framework: AIOX
version: 5.2.7
source: "https://github.com/SynkraAI/aiox-core"
---

# AIOX Framework - Instalacao

## Decisao

Adicionar o framework AIOX na raiz do Active Project `Squad-Playbook-de-Vendas`.

## Caminho Correto

`D:\1A-Projetos-Pessoais\Second Brain\04-Work-Winning-Sales\Projects\Squad-Playbook-de-Vendas`

## Comandos Usados

```powershell
npx aiox-core@5.2.7 install --ci --yes --ide codex
npx aiox-core@5.2.7 install --ci --yes --ide claude-code --merge
```

Os comandos foram executados com cache npm isolado em `%TEMP%/aiox-isolated-npm-cache`.

## Configuracao Escolhida

A configuracao usada foi a default nao-interativa do instalador AIOX:

- projeto tratado como brownfield/existente;
- perfil `advanced`;
- idioma `pt`/portuguese nos arquivos gerados;
- IDEs materializadas: Codex e Claude Code;
- sem preenchimento de chaves/API keys;
- `.env` gerado apenas como template vazio.

## Artefatos Criados

- `.aiox-core/`: framework AIOX instalado.
- `.codex/agents/`: agentes AIOX para Codex.
- `.codex/skills/`: skills locais AIOX para Codex.
- `.claude/`: comandos, agentes, regras e hooks gerados pelo instalador AIOX para Claude Code.
- `.antigravity/`, `.cursor/`, `.gemini/`, `.github/` e `.kimi/`: artefatos de compatibilidade gerados pelo sync do AIOX.
- `AGENTS.md`: instrucoes raiz para Codex, ajustadas para apontar para o runtime canonico do Playbook.
- `.env` e `.env.example`: templates de variaveis, sem credenciais reais.
- `.gitignore`: regras locais para `.env`, `node_modules/`, logs e arquivos de build.

## Regra De Integracao

AIOX passa a ser camada de orquestracao/IDE na raiz do projeto. Ele nao substitui o runtime markdown-first do Playbook em `07-Runtime-Squad/`.

Fonte canonica do Playbook:

- `07-Runtime-Squad/AGENTS.md`
- `07-Runtime-Squad/agents/*.md`
- `07-Runtime-Squad/tasks/*.md`
- `07-Runtime-Squad/workflows/*.md`
- `07-Runtime-Squad/skills/*.md`
- `07-Runtime-Squad/checklists/*.md`
- `07-Runtime-Squad/templates/TEMPLATE_REGISTRY.md`

## Validacao

```powershell
npx aiox-core@5.2.7 validate
Push-Location 07-Runtime-Squad
node scripts/validate-template-registry.js
node scripts/validate-platform-compatibility.js
Pop-Location
```
