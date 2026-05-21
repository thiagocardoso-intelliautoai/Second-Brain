---
source: "Wave 1 migration execution"
created_at: 2026-05-17
status: completed
legacy_repo: "D:\\1AWinningSales-Projetos\\squadfactory\\squads\\playbook-comercial-squad"
target_runtime: "D:\\1A-Projetos-Pessoais\\Second Brain\\04-Work-Winning-Sales\\Projects\\Squad-Playbook-de-Vendas\\07-Runtime-Squad"
---

# Manifesto de Migracao - Wave 1

## Decisao

A Wave 1 criou `07-Runtime-Squad/` dentro do Active Project e migrou a camada de runtime/contexto do repo legado para o Second Brain.

Decisoes tomadas:

- `07-Runtime-Squad/` vira o runtime principal do Squad Playbook de Vendas.
- O repo antigo fica como legado/historico e nao deve receber trabalho novo por padrao.
- `.codex/` e `.claude/` foram migrados inteiros porque, neste repo, contem apenas wrappers de agentes e config example.
- `agents/*.md` continua sendo a fonte canonica dos agentes.
- `.codex/agents/*.toml` e `.claude/agents/*.md` sao derivados; alterar canonico primeiro e depois rodar `node scripts\sync-agent-wrappers.js`.
- Outputs pesados, previews e workspaces temporarios ficaram fora do runtime e foram inventariados em [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/02-Process/Runtime-Squad-Historico/ARTEFATOS-LEGADOS|Artefatos Legados]].

## Inventario migrado

Conferencia:

- arquivos esperados pela lista de inclusao: 86;
- arquivos copiados para o runtime novo: 86;
- tamanho total esperado: 732326 bytes;
- tamanho total copiado: 732326 bytes;
- checagem SHA256 entre origem e destino: PASS.

| Item | Arquivos | Bytes | Papel |
|---|---:|---:|---|
| `.claude/` | 7 | 111795 | Wrappers Claude derivados dos agentes canonicos |
| `.codex/` | 8 | 112562 | Wrappers Codex e config example derivados |
| `.mcp.example.json` | 1 | 530 | Exemplo seguro de MCP, sem credencial real |
| `AGENTS.md` | 1 | 3344 | Instrucao operacional do runtime |
| `CLAUDE.md` | 1 | 486 | Entrada especifica para Claude |
| `README.md` | 1 | 8427 | Visao geral do squad |
| `squad.yaml` | 1 | 2886 | Manifesto do squad, versao e componentes |
| `agents/` | 7 | 110893 | Agentes canonicos |
| `tasks/` | 18 | 100541 | Tasks de entregavel e validacao |
| `workflows/` | 3 | 30704 | Fluxos de geracao e regeneracao |
| `skills/` | 7 | 72244 | Skills operacionais do squad |
| `checklists/` | 14 | 47845 | Validacao em camadas |
| `config/` | 6 | 35961 | Stack, voz, MCP e fallback |
| `templates/` | 1 | 40300 | Registry de templates F1-F14 |
| `data/` | 1 | 4028 | Schema de perfil do cliente |
| `scripts/` | 4 | 12451 | Validadores e sincronizacao de wrappers |
| `docs/` | 5 | 37329 | Setup, compatibilidade, factory plan e QA |

## Itens excluidos do runtime principal

| Item | Arquivos | Bytes | Motivo |
|---|---:|---:|---|
| `.tmp/` | 7 | 724424 | Scripts e outputs temporarios da geracao antiga; manter no legado como referencia |
| `tmp-wave3/` | 21 | 792950 | Outputs locais, previews e workspaces temporarios |
| `tmp-wave4/` | 141 | 3047985 | Outputs locais, previews de slides e workspace temporario |

Regra: estes itens nao foram copiados para evitar transformar o Second Brain em deposito de builds, previews e binarios. Quando forem necessarios para auditoria, usar o path do repo legado registrado em [[04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/02-Process/Runtime-Squad-Historico/ARTEFATOS-LEGADOS|Artefatos Legados]].

## Validacoes rodadas

Todas as validacoes minimas foram executadas dentro de `07-Runtime-Squad/`.

| Comando | Resultado |
|---|---|
| `node scripts\validate-template-registry.js` | PASS: 14/14 templates, 292 placeholder references |
| `node scripts\validate-template-registry.js --require-p0` | PASS: 14/14 templates, 292 placeholder references |
| `node scripts\validate-template-registry.js --strict-drive-ids` | PASS: strict Drive IDs |
| `node scripts\validate-platform-compatibility.js` | PASS: 7 agents |

## Pendencia tecnica registrada

`scripts/validate-template-client-facing.js` referencia `tmp-wave4/build_wave4_decks.mjs`.

Como `tmp-wave4/` foi excluido por decisao mecanica, esse validador deve ser tratado como historico ate uma destas decisoes acontecer:

- mover o build script relevante para `scripts/` com path estavel;
- recriar uma area de geracao limpa dentro do runtime;
- aposentar esse validador se a validacao visual migrar para outro fluxo.

Isto nao bloqueia a Wave 1 porque as validacoes minimas do plano passaram.

## Correcao pos-QA - 2026-05-18

O QA posterior confirmou que a copia original passou por checagem SHA256 no momento da migracao.

Decisao aplicada:

- `scripts/validate-template-client-facing.js` passou a divergir intencionalmente do repo legado.
- O target `tmp-wave4/build_wave4_decks.mjs` agora e tratado como target legado opcional.
- Se `tmp-wave4/build_wave4_decks.mjs` nao existir no runtime, o validador retorna `SKIP` com exit code `0`.
- Se o arquivo existir e houver violacao real, o validador continua retornando erro.
- `tmp-wave4/`, `.tmp/` e `tmp-wave3/` continuam fora do runtime por decisao de arquitetura.

## Estado apos a virada

Runtime principal:

```text
D:\1A-Projetos-Pessoais\Second Brain\04-Work-Winning-Sales\Projects\Squad-Playbook-de-Vendas\07-Runtime-Squad
```

Repo legado:

```text
D:\1AWinningSales-Projetos\squadfactory\squads\playbook-comercial-squad
```

Regra operacional:

- trabalho novo deve partir do runtime no Active Project;
- repo legado fica para consulta historica, auditoria ou recuperacao;
- nao manter dois runtimes vivos em paralelo.
