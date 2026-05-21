---
source: Wave 5 execution
created_at: 2026-05-17
status: active-policy
---

# Politica de Skills e Mentores

## Objetivo

Evitar dois erros:

- criar prompt generico sem uso real;
- deixar um bom metodo enterrado em nota solta.

## Tipos de artefato

| Tipo | Funcao | Quando usar |
|---|---|---|
| Framework | lente de pensamento ou metodo conceitual | quando ajuda a decidir ou enxergar melhor, mas ainda nao tem uso repetido |
| Prompt | instrucao pontual | quando resolve uma tarefa especifica e nao precisa virar processo |
| Template | estrutura de output | quando o formato se repete mais que o raciocinio |
| Skill | workflow operacional com input, output, limites e quality gate | quando existe tarefa recorrente com risco de perder qualidade |
| Comando | atalho para acionar uma skill | quando o uso ja esta maduro e frequente |
| Mentor | lente cognitiva inspirada em pessoa, escola ou conjunto de principios | quando a tarefa pede julgamento, critica ou criterio decisorio |

## Skill global vs local

Crie skill global em `07-Frameworks-and-Processes/AI-Skills-and-Mentors/` quando:

- o uso for transversal;
- o input e o output servirem para mais de uma frente;
- a skill nao depender de contexto privado de um cliente;
- a skill tiver criterio de qualidade observavel;
- a manutencao compensar.

Crie skill local quando:

- o uso estiver preso a um projeto, cliente ou repo;
- a skill depender de arquivos canonicos locais;
- ainda for cedo para generalizar;
- a generalizacao aumentaria o risco de chute.

Locais preferidos:

```text
04-Work-Winning-Sales/Projects/<Projeto>/05-Skills/
05-Clients-and-Mentoring/Mentoria-IA/05-Skills/
05-Clients-and-Mentoring/<Cliente>/05-Skills/
06-Personal-Brand/<Pipeline>/05-Skills/
```

## Promocao de framework para skill

Um framework so vira skill quando tiver:

- caso de uso concreto;
- input recorrente;
- output esperado;
- criterio de qualidade;
- pelo menos 1 uso real forte ou 2 a 3 usos parecidos;
- lugar claro para testar.

Se isso nao existir, mantenha como framework, checklist ou backlog.

## Mentores

Mentor nao e autoridade final. Mentor e uma lente.

Todo mentor precisa declarar:

- caso de uso;
- fontes usadas;
- limites;
- perguntas tipicas;
- anti-padroes;
- criterio de qualidade;
- checkpoint humano para valores, obsessoes e contradicoes produtivas.

Para pessoa publica, pesquisar fontes antes de criar. Preferir livros, aulas, entrevistas longas, site oficial e materiais primarios.

Para pessoa privada ou material interno, preservar fonte e confidencialidade.

## Quality gate de uma skill

Antes de chamar algo de skill pronta, verificar:

- o gatilho de uso esta claro;
- os inputs obrigatorios estao claros;
- o output esperado esta claro;
- existe regra de quando nao usar;
- existe criterio de qualidade;
- a skill foi testada ou esta marcada como draft;
- ela nao duplica outra skill existente.

## Regra de descarte

Se uma skill nao for usada, ficar vaga ou exigir manutencao sem ganho, ela deve ser:

- rebaixada para checklist;
- arquivada;
- ou fundida com outra skill.
