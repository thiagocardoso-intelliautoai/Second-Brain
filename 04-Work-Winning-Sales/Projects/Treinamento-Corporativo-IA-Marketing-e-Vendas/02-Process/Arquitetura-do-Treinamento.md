---
source: Google Sheet em producao
created_at: 2026-05-21
status: draft
project: Treinamento Corporativo IA Marketing e Vendas
---

# Arquitetura do Treinamento

## Tese operacional

O treinamento nao deve ensinar IA como repertorio abstrato.

O mecanismo correto e:

1. escolher workflows reais;
2. organizar contexto minimo;
3. gerar output aplicado;
4. revisar qualidade;
5. transformar o melhor uso em rotina, Skill ou agente;
6. medir adocao e ganho.

## Loop de cada sessao

| Bloco | Duracao | Funcao |
|---|---:|---|
| Conteudo | 20-25 min | Dar linguagem, criterio e mapa mental. |
| Workshop/demonstracao | 20-25 min | Mostrar aplicacao em caso real ou semi-real. |
| Combinados/tarefa | 10-15 min | Definir output de campo, dono, criterio e prazo. |

Regra:

- cada encontro precisa gerar uma decisao, um artefato e uma tarefa de campo;
- a sessao seguinte deve abrir revisando o output anterior;
- sem revisao, o treinamento vira inspiracao de curto prazo.

## Fluxo completo

```text
Pre-work
  -> Sessao 1: fundamentos + diagnostico
  -> Campo 1: mapa de workflows + contexto minimo
  -> Sessao 2: marketing com IA
  -> Campo 2: ativo real de marketing
  -> Sessao 3: vendas com IA
  -> Campo 3: fluxo real de vendas
  -> Sessao 4: Skills, governanca e adocao
  -> Piloto 30 dias
  -> Review de impacto e decisao de escala
```

## Papel da Winning

- Conduzir pre-work e diagnostico de maturidade.
- Customizar exemplos por area e contexto.
- Facilitar workshop e revisao de outputs.
- Fornecer templates, prompts, Skills ou agentes quando ja existirem.
- Ajudar o cliente a escolher 1-2 pilotos, em vez de dispersar em muitos casos de uso.
- Fechar plano de adocao com donos, metricas e checkpoint.

## Papel do cliente

- Trazer contexto real: ICP, oferta, playbook, funil, campanhas, metas, objecoes e exemplos.
- Preencher matriz de workflows.
- Executar tarefas de campo.
- Registrar tempo antes/depois quando aplicavel.
- Submeter outputs para revisao.
- Definir sponsor, champions e donos internos para o piloto.

## Gate de priorizacao

Antes de escolher piloto, avaliar cada workflow por:

- frequencia;
- tempo gasto;
- clareza da tarefa;
- disponibilidade de dados/contexto;
- risco operacional ou comercial;
- possibilidade de revisar o output.

Padrao sugerido:

- escolher 1-2 pilotos por ciclo;
- priorizar workflows com score alto e output avaliavel;
- evitar casos com dados ruins, risco alto ou dono indefinido.

## Gate de qualidade

Um output de IA so deve ser considerado bom se:

- usa contexto real do cliente;
- tem proximo passo claro;
- segue criterio de qualidade definido antes;
- exige pouca edicao humana para ficar utilizavel;
- pode ser comparado com o output manual anterior;
- nao cria risco juridico, comercial ou reputacional desnecessario.

## Mecanismo de adocao

O plano de 30 dias deve responder:

- qual workflow sera usado;
- por quem;
- quantas vezes;
- em qual ferramenta;
- com qual contexto;
- quem revisa;
- qual metrica prova valor;
- quando acontece o proximo checkpoint.

Indicadores sugeridos:

- horas economizadas;
- adocao;
- qualidade;
- consistencia;
- impacto comercial.

## Anti-padroes

- Dar aula generica de prompt sem workflow real.
- Demonstrar ferramenta demais e processo de menos.
- Escolher muitos casos de uso ao mesmo tempo.
- Nao exigir contexto do cliente.
- Tratar output bonito como output bom.
- Nao medir antes/depois.
- Nao definir sponsor ou champion.
- Criar Skill antes de validar o workflow.
