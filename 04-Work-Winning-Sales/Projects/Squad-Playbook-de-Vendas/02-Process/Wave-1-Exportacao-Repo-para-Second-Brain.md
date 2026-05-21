---
source: "Thiago decision + migration planning + execution"
created_at: 2026-05-17
updated_at: 2026-05-17
status: completed
executed_at: 2026-05-17
decision: "migracao completa"
legacy_repo: "D:\\1AWinningSales-Projetos\\squadfactory\\squads\\playbook-comercial-squad"
target_project: "D:\\1A-Projetos-Pessoais\\Second Brain\\04-Work-Winning-Sales\\Projects\\Squad-Playbook-de-Vendas"
target_runtime: "D:\\1A-Projetos-Pessoais\\Second Brain\\04-Work-Winning-Sales\\Projects\\Squad-Playbook-de-Vendas\\07-Runtime-Squad"
---

# Wave 1 - Migracao Completa do Squad para o Active Project

## Decisao

A decisao revisada e: **migrar o Squad Playbook de Vendas inteiro para dentro do Active Project**.

Nao vamos manter o meio-termo em que o Second Brain e cockpit e o repo antigo continua sendo o lugar real de trabalho. Isso cria friccao, duplica contexto e faz Thiago ter que lembrar onde cada coisa vive.

Direcao:

- o Active Project vira o lugar principal de contexto, gestao e runtime do squad;
- o repo antigo vira legado/historico depois que a migracao passar nos criterios de pronto;
- a migracao deve ser mecanica primeiro e interpretativa depois;
- nada deve ser reescrito manualmente quando puder ser copiado com proveniencia;
- outputs pesados entram por manifesto, nao como sujeira dentro do runtime principal.

## Resultado esperado

Depois da Wave 1, o trabalho novo deve acontecer aqui:

```text
D:\1A-Projetos-Pessoais\Second Brain\04-Work-Winning-Sales\Projects\Squad-Playbook-de-Vendas
```

Runtime novo sugerido:

```text
D:\1A-Projetos-Pessoais\Second Brain\04-Work-Winning-Sales\Projects\Squad-Playbook-de-Vendas\07-Runtime-Squad
```

Repo legado:

```text
D:\1AWinningSales-Projetos\squadfactory\squads\playbook-comercial-squad
```

Regra apos validacao:

- nao editar mais o repo legado;
- usar o repo legado apenas para consulta historica, auditoria ou recuperacao;
- registrar no Project OS a data da virada.

## Estrutura alvo

```text
04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/
├── 00-Project-Brief.md
├── PROJECT.md
├── 01-Inputs/
├── 02-Process/
├── 03-Outputs/
├── 04-Feedback/
├── 05-Skills/
├── 06-Logs/
└── 07-Runtime-Squad/
    ├── agents/
    ├── tasks/
    ├── skills/
    ├── workflows/
    ├── checklists/
    ├── config/
    ├── templates/
    ├── data/
    ├── scripts/
    ├── docs/
    ├── squad.yaml
    ├── AGENTS.md
    ├── README.md
    └── CLAUDE.md
```

## O que migrar

Migrar para `07-Runtime-Squad/`:

- `AGENTS.md`
- `README.md`
- `CLAUDE.md`
- `squad.yaml`
- `.mcp.example.json`
- `.codex/`
- `.claude/`
- `agents/`
- `tasks/`
- `workflows/`
- `skills/`
- `checklists/`
- `config/`
- `templates/`
- `data/`
- `scripts/`
- `docs/`
- arquivos de setup e compatibilidade
- arquivos texto auxiliares que sustentam execucao ou decisao

Inventariar, mas nao copiar automaticamente para o runtime principal:

- `tmp-wave*/output/*.pptx`
- `tmp-wave*/output/*.docx`
- `tmp-wave*/output/*.xlsx`
- `tmp-wave*/preview/*.png`
- workspaces temporarios;
- caches;
- outputs gerados;
- binarios pesados.

Esses entram em manifesto de artefatos com path original, uso e decisao: copiar para area de artefatos, manter no legado ou descartar.

## Wrappers `.codex` e `.claude`

Decisao executada:

- migrar `.codex/` e `.claude/` inteiros, porque neste repo eles contem apenas wrappers/config examples;
- marcar wrappers como derivados, nao fonte de estrategia;
- continuar tratando `agents/*.md` como fonte canonica dos agentes;
- depois da migracao, usar `node scripts\sync-agent-wrappers.js` quando um agente canonico mudar;
- nao editar wrappers diretamente como decisao estrategica.

## Ordem segura de execucao

1. Gerar inventario do repo legado.
2. Gerar lista de referencias externas.
3. Criar `07-Runtime-Squad/`.
4. Copiar arquivos de runtime/contexto mantendo estrutura.
5. Registrar arquivos excluidos e motivo.
6. Gerar manifesto de artefatos pesados.
7. Atualizar paths internos quando necessario.
8. Rodar validacoes no novo local.
9. Comparar resultado com repo legado.
10. Atualizar `PROJECT.md`, links e logs.
11. Marcar repo legado como `historico / nao editar`.

## Criterios de pronto

A Wave 1 so esta pronta quando:

1. Inventario completo do repo legado foi gerado.
2. Arquivos migrados estao em `07-Runtime-Squad/`.
3. Estrutura principal do squad existe no novo runtime.
4. Arquivos excluidos possuem motivo mecanico registrado.
5. Artefatos pesados possuem manifesto.
6. Referencias externas foram escaneadas e classificadas.
7. Paths absolutos antigos foram identificados.
8. Paths quebrados ou suspeitos foram marcados como `a verificar`.
9. Scripts de validacao foram testados no novo local ou registrados como pendentes com motivo.
10. O novo runtime passa nas validacoes possiveis.
11. `PROJECT.md` declara o Active Project como lugar principal de trabalho.
12. Repo legado esta marcado como historico/nao editar.

## Validacoes minimas

Rodar no novo runtime, quando possivel:

```powershell
node scripts\validate-template-registry.js
node scripts\validate-template-registry.js --require-p0
node scripts\validate-template-registry.js --strict-drive-ids
node scripts\validate-platform-compatibility.js
```

Se algum comando falhar por path, dependencia ou ambiente, registrar:

- comando;
- erro;
- causa provavel;
- se bloqueia ou nao a migracao;
- proxima acao.

## Escaneamento de dependencias externas

Antes de declarar a migracao boa, buscar no runtime migrado por:

```text
D:\
C:\
http://
https://
drive.google
docs.google
Design System
Design.md winning sales
Notion
Downloads
tmp-wave
```

Classificar cada achado:

| Categoria | Exemplo | Acao |
|---|---|---|
| Dependencia local obrigatoria | Design System Winning | registrar path e checar existencia |
| Artefato Google Workspace | Docs/Sheets/Slides/Drive IDs | registrar link e status |
| Fonte externa de schema/docs | json-schema.org, dominio Winning | registrar; nao copiar conteudo externo sem necessidade |
| Referencia historica | Notion, Downloads, origem antiga | preservar como proveniencia |
| Output temporario | `tmp-wave*` | inventariar, nao copiar pesado |
| Caminho suspeito/quebrado | path antigo ou inconsistente | marcar `a verificar` |

## Achados iniciais

Varredura inicial no repo legado encontrou referencias importantes fora do repo:

- `02-Process/Runtime-Squad-Historico/template-factory-plan.md` menciona `D:\1AWinningSales-Projetos\squadfactory\Design.md winning sales`, que parece caminho antigo ou inconsistente em relacao a `D:\1AWinningSales-Projetos\squadfactory\Design System`;
- `templates/TEMPLATE_REGISTRY.md` e `02-Process/Runtime-Squad-Historico/wave4.2-template-qa.md` contem varios links Google Drive/Docs/Sheets/Slides;
- `data/perfil-schema.json` contem `$schema` e `$id` externos;
- `tmp-wave4/output/wave4-manifest.json` contem paths absolutos dentro do repo legado;
- `config/*` menciona Google Drive/MCP como dependencia operacional.

Essa lista e inicial. A migracao precisa gerar o mapa completo.

## Riscos

| Risco | Como evitar |
|---|---|
| Copiar so parte do contexto | inventario antes da copia e conferencia depois |
| Reescrever e perder detalhe | copiar bruto primeiro, destilar depois |
| Sujar o vault com output pesado | manifesto de artefatos em vez de copia automatica |
| Quebrar scripts por path | rodar validacoes no novo local |
| Deixar dois runtimes vivos | marcar repo legado como historico depois da virada |
| Perder dependencia externa | busca por paths/URLs antes do criterio de pronto |

## Nao fazer

- Nao editar o repo legado depois que a migracao for validada.
- Nao migrar credenciais locais.
- Nao misturar fonte bruta migrada com resumo interpretativo.
- Nao copiar outputs pesados sem decisao explicita.
- Nao declarar migracao completa sem rodar ou registrar validacoes.

## Resultado da execucao

Executado em 2026-05-17.

Arquivos de controle criados:

- [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/02-Process/Runtime-Squad-Historico/MANIFESTO-DE-MIGRACAO|Manifesto de Migracao]]
- [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/02-Process/Runtime-Squad-Historico/ARTEFATOS-LEGADOS|Artefatos Legados]]
- [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/02-Process/Runtime-Squad-Historico/REFERENCIAS-EXTERNAS|Referencias Externas]]
- [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/06-Logs/2026-05-17-Wave-1-Migracao-Runtime-Squad|Log da Migracao Wave 1]]

Validacoes rodadas no runtime novo:

```powershell
node scripts\validate-template-registry.js
node scripts\validate-template-registry.js --require-p0
node scripts\validate-template-registry.js --strict-drive-ids
node scripts\validate-platform-compatibility.js
```

Resultado:

- PASS em todas as validacoes minimas;
- 86 arquivos migrados;
- checagem SHA256 origem/destino passou;
- `.tmp/`, `tmp-wave3/` e `tmp-wave4/` ficaram no legado e foram inventariados.

## Proxima acao

Usar `07-Runtime-Squad/` como runtime principal do trabalho novo.

Proximo bloco operacional recomendado:

1. Localizar no runtime novo os donos do `master-kpis-sheet-winning`.
2. Comparar o master atual com a aba PROSPECCAO da referencia.
3. Decidir Low/Mid/High touch antes de alterar agent, task, skill, checklist ou registry.
