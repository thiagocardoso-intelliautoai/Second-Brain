# Modos De Operacao

## `capturar-ideia`

Usar quando Thiago despejar ideia crua, bloco solto, transcricao curta ou anotacao sem pasta propria.

Entrada:

- texto bruto;
- tema;
- frase solta;
- bloco em `Ideias-Brutas/00-Captura-Rapida.md`.

Acao:

1. Preservar o texto original sem polir.
2. Criar slug curto em kebab-case quando a ideia ja merecer unidade propria.
3. Criar `06-Personal-Brand/Linkedin/Ideias-Brutas/<slug>/IDEIA.md` ou atualizar `00-Captura-Rapida.md`.
4. Extrair apenas campos que existirem: tese, erro combatido, por que importa, fonte de autoridade, possivel formato, status.
5. Nao preencher campo vazio por estetica.

Saida:

- `IDEIA.md` com status `raw-idea` ou `raw-draft`;
- original preservado;
- proximo passo sugerido, se houver.

Perguntar antes se:

- houver varias ideias misturadas e nao der para separar com seguranca;
- o conteudo for pessoal/sensivel;
- o slug ou tema puder causar interpretacao errada.

## `promover-ideia-para-post`

Usar quando uma ideia organizada deve virar post.

Entrada:

- `Ideias-Brutas/<slug>/IDEIA.md`;
- bloco claro de captura rapida;
- pedido explicito para transformar uma ideia em post.

Acao:

1. Preservar ou linkar a ideia original.
2. Definir um outcome principal para o leitor.
3. Extrair tese, erro combatido, decisao que destrava e autoridade de Thiago para falar.
4. Escolher uma estrutura simples: problema -> consequencia -> alternativa; contraste; storytelling; lista; declaracao -> defesa.
5. Criar 3 a 5 hooks, priorizando frases vivas do original.
6. Escrever `Versao sugerida` com voz informal, operacional, direta e com English tecnico natural.
7. Criar ou atualizar `Posts/<slug>/POST.md`.
8. Criar ou atualizar `Posts/<slug>/PREVIEW.md`.
9. Criar `visual/brief.md` apenas quando o visual ajudar.

Saida:

- `POST.md`;
- `PREVIEW.md`;
- opcionalmente `visual/brief.md`.

Perguntar antes se:

- a ideia tiver dois caminhos fortes e a escolha mudar o posicionamento;
- o hook forte puder soar agressivo demais;
- houver claim externo que precise de pesquisa;
- o formato visual for decisao importante.

## `revisar-post`

Usar quando ja existir rascunho ou `POST.md`.

Entrada:

- `Posts/<slug>/POST.md`;
- rascunho colado;
- pedido de revisao de hook, CTA, tese ou voz.

Acao:

1. Ler o post inteiro e o original preservado, se existir.
2. Aplicar `quality-gate.md`.
3. Diagnosticar o que funciona, o que esta confuso e riscos de interpretacao.
4. Criar `Versao sugerida` sem apagar a versao anterior.
5. Registrar `O que mudou` quando houver alteracao estrutural relevante.
6. Manter decisoes pendentes claras em vez de fingir certeza.

Saida:

- `POST.md` atualizado ou diagnostico no chat, conforme pedido;
- original preservado;
- status honesto: draft, pronto para revisao humana, ou precisa decisao.

Perguntar antes se:

- a revisao exigir suavizar tese polemica;
- a mudanca puder alterar a posicao original de Thiago;
- o post depender de dado factual nao comprovado.

## `criar-brief-visual`

Usar quando o post pedir capa, carrossel curto, infografico, visual de caderno, print de autoridade ou comparacao visual.

Entrada:

- `POST.md`;
- tese visual;
- pedido direto de brief visual;
- ideia com processo, matriz, comparacao ou framework.

Acao:

1. Definir objetivo visual em uma frase.
2. Recomendar formato: capa unica ou carrossel curto.
3. Definir conceito, estrutura e estilo.
4. Preferir assinatura visual: caderno, rascunho, notebook raw, pensamento sendo construido.
5. Usar data-driven para benchmark; editorial clean para materia-colab; quote card apenas para frase muito forte.
6. Criar somente `Posts/<slug>/visual/brief.md`.

Saida:

- `visual/brief.md`;
- sem HTML;
- sem PNG;
- sem PDF;
- sem pipeline de render.

Perguntar antes se:

- o visual exigir foto, print ou fonte externa especifica;
- capa vs carrossel mudar o esforço de publicacao;
- houver dado visual que precise de fonte.
