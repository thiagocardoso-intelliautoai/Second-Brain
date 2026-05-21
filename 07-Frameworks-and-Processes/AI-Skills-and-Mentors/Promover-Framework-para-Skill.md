---
source: Wave 5 execution
created_at: 2026-05-17
status: active-skill
related_backlog: 07-Frameworks-and-Processes/AI-Skills-and-Mentors/Frameworks-to-Skills-Backlog.md
---

# Promover Framework para Skill

## Funcao

Decidir se um framework do vault deve virar skill, template, checklist, prompt ou continuar apenas como lente.

## Quando usar

Use quando:

- Thiago repetir o mesmo tipo de output usando um framework;
- uma IA precisar aplicar o framework sem explicacao do zero;
- um projeto gerar um metodo local que talvez seja reutilizavel;
- houver risco de criar estrutura demais.

## Inputs obrigatorios

- framework candidato;
- 1 a 3 usos reais ou tentativa concreta de uso;
- input recorrente;
- output esperado;
- onde sera testado;
- criterio de qualidade desejado.

## Decisao

| Resultado | Quando escolher |
|---|---|
| manter como framework | ainda e lente, sem output repetido |
| criar checklist | o que se repete e a avaliacao, nao o workflow |
| criar template | o formato de saida se repete |
| criar prompt | a tarefa e pontual, mas recorrente |
| criar skill local | o uso esta preso a um projeto ou cliente |
| criar skill global | o uso ja e transversal |

## Processo

1. Ler o framework.
2. Ler o output real que motivou a promocao.
3. Identificar a repeticao mecanica.
4. Separar o que e criterio, formato e workflow.
5. Decidir o menor artefato suficiente.
6. Criar a versao local primeiro quando houver duvida.
7. Adicionar quality gate.
8. Registrar no backlog.

## Quality gate

So promover quando:

- o caso de uso esta claro;
- o input nao e vago;
- o output e observavel;
- a skill reduz retrabalho ou melhora qualidade;
- existe lugar para testar;
- nao cria manutencao falsa.

## Output esperado

Entregar uma decisao curta:

```text
Decisao: criar skill local / criar skill global / manter como framework / criar checklist / criar template.
Motivo:
Input:
Output:
Quality gate:
Onde testar:
Proxima acao:
```

