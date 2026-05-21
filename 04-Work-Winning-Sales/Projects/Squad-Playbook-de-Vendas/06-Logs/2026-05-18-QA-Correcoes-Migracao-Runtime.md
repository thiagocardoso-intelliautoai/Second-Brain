---
source: "QA pos-migracao Wave 1"
created_at: 2026-05-18
status: completed
related:
  - "04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/02-Process/Runtime-Squad-Historico/MANIFESTO-DE-MIGRACAO.md"
  - "04-Work-Winning-Sales/Projects/Squad-Playbook-de-Vendas/02-Process/Runtime-Squad-Historico/REFERENCIAS-EXTERNAS.md"
---

# 2026-05-18 - QA Correcoes da Migracao do Runtime

## Achados do QA

- A migracao estrutural estava correta: 86 arquivos migrados, checagem SHA256 aprovada e validacoes principais passando.
- `scripts/validate-template-client-facing.js` falhava porque apontava para `tmp-wave4/build_wave4_decks.mjs`, que ficou corretamente no repo legado.
- Algumas notas ainda usavam "repo externo" em contexto operacional futuro, o que podia induzir uma IA a editar o legado.
- O repo legado nao tinha aviso fisico no topo de `AGENTS.md` e `README.md`.

## Decisoes aplicadas

- `validate-template-client-facing.js` agora trata `tmp-wave4/build_wave4_decks.mjs` como target legado opcional.
- Se o target legado nao existir no runtime, o validador retorna `SKIP` com exit code `0`.
- Referencias operacionais futuras foram atualizadas para apontar para `07-Runtime-Squad/`.
- O README de Active Projects agora registra a excecao de migracao de runtime com inventario, manifestos, validacoes e exclusao de outputs pesados.
- O repo legado recebeu aviso fisico de `LEGADO / NAO EDITAR` em `AGENTS.md` e `README.md`.

## Validadores rodados

```powershell
node scripts\validate-template-registry.js
node scripts\validate-template-registry.js --require-p0
node scripts\validate-template-registry.js --strict-drive-ids
node scripts\validate-platform-compatibility.js
node scripts\validate-template-client-facing.js
```

Resultado esperado apos a correcao:

- os quatro validadores principais passam;
- `validate-template-client-facing.js` retorna `SKIP` quando `tmp-wave4/build_wave4_decks.mjs` nao existe no runtime;
- nenhuma falha de QA fica escondida quando o arquivo alvo existir.

## Pendencias restantes

- Auditar `D:\1AWinningSales-Projetos\squadfactory\Design System` antes de redesenho visual ou escolha de skills externas.
- Confirmar acesso de edicao aos masters Google Workspace antes de alterar templates.
- Proxima frente recomendada: Wave 4 KPI Sheet, incluindo PROSPECCAO e Low/Mid/High touch.

