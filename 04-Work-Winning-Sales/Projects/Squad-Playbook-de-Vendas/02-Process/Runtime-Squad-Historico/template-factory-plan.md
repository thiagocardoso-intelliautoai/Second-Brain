# Plano de Acao: Template Factory do Squad

Este plano organiza a criacao e QA dos proximos templates master do Playbook Comercial, mantendo o squad portavel entre Codex e Claude e evitando que templates fracos contaminem o primeiro teste real.

## Estado Atual

- F3 `master-icp-narrative` aponta no registry para o Doc `1za_FPKz8HAZ-Dfs2png2Zuvp-GbqX22DHIIZCKmp6rc`.
- F4 `master-icp-scoring` aponta no registry para a Sheet corrigida `1Zqufaii9qTzxXT6gOcjQWfaR2ztaTXhQ4UPR4-AmAK4`.
- F4 validado no Drive: a formula de classificacao final usa percentual do maximo possivel, nao limiar absoluto 80/50. Em 2026-05-13, o MCP Sheets do consultor conseguiu exportar o arquivo, mas nao ofereceu edicao granular de celula; a correcao foi aplicada por plugin como fallback tecnico controlado e validada por leitura posterior.
- A pasta Drive validada para ICP/Persona e `Templates Master/02-icp-persona`: `1lNyvwxg3Y8qvWUJWGspwi1y9raSGHKVr`.
- Na pasta existiam versoes antigas que nao devem ser usadas:
  - `master-icp-narrative.md`
  - `master-icp-narrative-revisado.md`
  - `master-icp-scoring`
  - `master-icp-scoring-revisado`
  - Status: arquivadas na lixeira em 2026-05-13.

## Gate 0: QA do P0

Antes de criar novos templates em lote, validar estes pontos:

1. Validar no Doc F3 final:
   - Trocar `corte eliminarário` por `corte eliminatório`.
   - `{{NOME_CLIENTE}}` correto.
   - `Versao` corrigido para `Versão`.
   - Conteudo lido/exportado pelo MCP do consultor antes de seguir.
2. Corrigir na Sheet F4 final:
   - Concluido: arquivo operacional `master-icp-scoring-winning`, ID `1Zqufaii9qTzxXT6gOcjQWfaR2ztaTXhQ4UPR4-AmAK4`.
   - Concluido: `{{NOME_CLIENTE}}` inserido no cabecalho/resumo.
   - Concluido: formulas das linhas de criterio referenciam a propria linha.
   - Concluido: resumo soma/conta `H11:H18` e `I11:I18`.
   - Concluido: formulas toleram placeholders e nao exibem `#ERROR!`/`#VALUE!` antes do preenchimento real.
   - Concluido: formula `I8` classifica por percentual do maximo gradual possivel.
   - Concluido: acentos visiveis corrigidos.
   - Ressalva: aba veio como `master-icp-scoring-winning-corr` por limitacao do import CSV; conteudo e formulas estao corretos.
3. Reexportar o F3 como texto e validar:
   - Zero placeholders quebrados.
   - Todas as 3 personas com 7 dimensoes.
   - ICP em prosa com placeholder unico `{{02_ICP_PARAGRAFO}}`.
   - Imagem ausente tratada via `{{02_PERSONA_X_IMAGEM_PATH}}`, para o agent preencher com path ou pendencia explicita.
4. Reexportar o F4 como XLSX e validar:
   - 8 linhas de criterio com placeholders completos.
   - Formulas de `Score ponderado` calculam `D{linha}*G{linha}` para criterios graduais.
   - Criterios eliminatorios retornam score 0 e status de corte.
   - A classificacao final reprova primeiro por corte eliminatorio e so depois considera percentual do score gradual sobre o maximo possivel. Nao usar limiar absoluto 80/50.
   - Formula final esperada em `I8`: `=IF(I7>0;"Fora do ICP";IFERROR(IF(H6/(SUMIF(C11:C18;"Gradual";D11:D18)*5)>=0,8;"Forte fit";IF(H6/(SUMIF(C11:C18;"Gradual";D11:D18)*5)>=0,5;"Médio fit";"Fora do ICP"));"Fora do ICP"))`
   - Nenhuma formula referencia cabecalho por engano.
5. Arquivar na lixeira as versoes antigas do P0, sem deletar permanentemente:
   - `master-icp-narrative.md`
   - `master-icp-narrative-revisado.md`
   - `master-icp-scoring`
   - `master-icp-scoring-revisado`
6. Rodar:
   - `node scripts/validate-template-registry.js --require-p0`

Regra de ferramenta: templates finais do Google Workspace devem tentar primeiro os MCPs conectados pelo consultor. Se Drive/Sheets/Slides/Docs via MCP falhar por permissao ou capacidade, tentar plugin/conector como fallback tecnico controlado. Se o plugin tambem falhar, pausar para corrigir acesso ou usar fallback manual.

## Arquitetura Do Drive

A organizacao do Drive e criterio de qualidade da fabrica de templates, nao limpeza opcional.

### Raiz operacional

Raiz: `Squad Playbook Comercial` (`1ETyAXq-dQnX7KgU0_Yo4NcBK3Lv7PVAH`).

A raiz oficial deve ficar enxuta:

- `Clientes/`
- `Templates Master/`

Pastas como `Outputs de Teste` e `Referencias` nao fazem parte do fluxo oficial. Em 2026-05-13, o MCP Drive retornou ambas como `trashed: true`; se reaparecerem como nao lixeira e estiverem vazias, mover para lixeira somente com confirmacao explicita do consultor.

### Templates Master

`Templates Master` (`1VNNZNFyoXDCGXmuaNni7l9YDWVwf4Zoc`) deve ficar organizado por numero e funcao:

- `00-indice-mestre` (`1-SRDwtFB10pYalntRU1VTytS_eO0mZ1s`)
- `01-funil-kpis` (`1TMz06bPW8iFH6CG4VuUxmAB0VU1D47e4`)
- `02-icp-persona` (`1lNyvwxg3Y8qvWUJWGspwi1y9raSGHKVr`)
- `03-prospeccao` (`1DRNB9qH6K7SypLeR0g7sH8fEhGUMGcsN`)
- `04-outreach` (`1b9MJuVikXsMb9vPcic4Oy90hyT0b46f5`)
- `08-battle-cards` (`1_9VZi-WuWy3ECOyozYdTe5KJEZPGlRl_`)
- `09-calculadora-roi` (`1LVbSUh_jXaB9HkJ1ixgTur_A2Wd5itvw`)
- `10-provas-sociais` (`1Okt5OmR0uYMp4E9ztxZJ9UnCPn6CLE-J`)
- `11-objecoes` (`1s2mhkCF6JZTzznggUg8S8aAUtV6mymsH`)

Na Onda 2:

- F1 fica em `Templates Master/01-funil-kpis`.
- F5 Doc e F5 Slides ficam em `Templates Master/03-prospeccao`.
- F6 fica em `Templates Master/04-outreach`.

### Clientes

`Clientes/{NOME_CLIENTE}` e a pasta operacional do projeto real. Ela deve separar claramente material interno do pacote final compartilhavel.

Interno, nao compartilhavel direto com cliente final:

- `perfil.json`
- `identidade-visual/`
- `reunioes/`
- `experiencia-consultor/`
- `materiais-cliente/`
- `decisoes/`
- `revisoes/`

Compartilhavel com cliente final:

- `playbook-gerado/`
  - `guia-de-uso.gdocs`
  - `00_ESTRATEGIA/`
  - `01_OPERACAO/`
  - `02_TREINAMENTO/`

Regra: `playbook-gerado/` e o unico pacote final compartilhavel. Nao compartilhar `perfil.json`, `decisoes`, `revisoes`, materiais brutos nem experiencia do consultor.

## Metodo Padrao Por Template

Para cada template, seguir o mesmo pipeline:

1. Ler o agent responsavel, task, checklist Camada B, `house-voice.md`, `find-replace-placeholders.md`, `identidade-visual-dupla.md` e o Winning Sales Design System em `D:\1AWinningSales-Projetos\squadfactory\Design.md winning sales`.
2. Criar uma especificacao curta antes do arquivo:
   - Objetivo operacional.
   - Artefato final esperado.
   - Quem preenche quais placeholders.
   - Como o vendedor/consultor usa.
3. Criar o template no Drive via MCP correto do consultor.
4. Exportar/ler o arquivo gerado pelo MCP e aplicar QA:
   - Conteudo obrigatorio.
   - Placeholders completos e em `{{UPPER_SNAKE_CASE}}`.
   - Fit com o agent/task que vai preencher.
   - UX simples para consultor/vendedor.
   - Visual Winning Sales aplicado sem exagero.
   - Design bate com `D:\1AWinningSales-Projetos\squadfactory\Design.md winning sales`: navy `#221E46`, crimson `#D3153E`, bone `#FAF7F2`, paper `#FFFFFF`, bordas `#E4E2EC`, hierarquia editorial, labels uppercase, sem emoji e sem ponto de exclamação.
   - Formulas funcionando, quando for Sheets.
   - Ordem narrativa coerente.
   - Contrato pratico: todo placeholder do arquivo real aparece na task, no registry e no agent responsavel.
   - Rota de ferramenta correta: Drive/Sheets/Slides/Docs tentam MCP primeiro; se falhar, plugin/conector como fallback tecnico; se tambem falhar, pedir correcao ou fallback manual.
5. Corrigir imediatamente se falhar.
6. Atualizar `templates/TEMPLATE_REGISTRY.md` com Drive ID e status.
7. Rodar validacao local.
8. Pausar para validacao humana quando a onda tiver impacto alto ou artefatos visuais grandes.

## Workflow Obrigatorio Para Sheets

Quando o template for Google Sheets, separar a criacao em duas etapas:

### Etapa 1: estrutura funcional

1. Criar a Sheet via MCP conectado ao Drive do consultor.
2. Montar abas, tabelas, formulas, placeholders e instrucoes de uso.
3. Validar estrutura, formulas e placeholders.
4. Enviar o link ao consultor e pausar.
5. Pedir explicitamente: liberar temporariamente como "qualquer pessoa com o link pode editar".

### Etapa 2: acabamento visual e QA

1. Com acesso de editor confirmado, aplicar formatting batch update.
2. Usar o Winning Sales Design System em `D:\1AWinningSales-Projetos\squadfactory\Design.md winning sales`.
3. Aplicar cabecalho navy, faixa crimson quando fizer sentido, fundos bone/paper, bordas ink-200, wrap, larguras, congelamento e filtros.
4. Revalidar formulas, ranges, hierarquia visual e legibilidade.
5. Avisar o consultor para voltar o compartilhamento para restrito ao final.

Regra: Sheet funcional mas visualmente crua nao passa QA. O acabamento visual e parte do template, nao uma etapa opcional.

QA de logica para Sheets:

- O registry, a task, o agent responsavel e o checklist Camada B precisam listar as mesmas colunas e os mesmos placeholders do template real.
- Slots opcionais nao podem sobrar como `{{...}}` no output final: o agent deve preencher todos, ou limpar/remover linhas extras antes do Reviewer.
- Formulas devem respeitar o locale da planilha antes da criacao/edicao. Para planilhas `pt_BR`, usar separador `;` e decimal `,` na formula enviada ao Sheets. Se a API normalizar nomes de funcoes para ingles (`IFERROR`, `SUMIF`, etc.), tudo bem; o criterio real e a formula ficar parseavel, sem `#ERROR!`.
- Nunca colar formulas em ingles com virgula em planilha `pt_BR` sem validar imediatamente. Esse erro ja ocorreu no F4 e quebrou `H6`, `I7`, `I8` e `H11:I18`.
- Formulas que dependem de placeholders numericos precisam ser tolerantes a placeholder. Enquanto campos como peso, meta, atual ou pontuacao ainda estiverem como `{{...}}`, a celula calculada deve ficar vazia ou em estado neutro via `SEERRO(...;"")`/equivalente, nunca exibir `#VALUE!` no template master.
- Depois de qualquer escrita de formula em Sheets, reabrir/ler o range por API/plugin/MCP disponivel e validar `userEnteredValue`, `effectiveValue` e `formattedValue`. Nenhum template Sheets passa QA se ranges funcionais exibirem `#ERROR!`, `#VALUE!`, `#DIV/0!` ou erro parseavel antes do preenchimento real.
- Campos usados por formula devem receber valores numericos sem unidade textual. Unidades ficam em colunas descritivas.

## Workflow Obrigatorio Para Docs

Quando o template for Google Docs:

1. Criar ou editar pelo MCP/Drive correto do consultor.
2. Exportar como `text/plain` ou ler via MCP Docs/Drive do consultor.
3. Comparar o texto real exportado contra registry, task, checklist e agent:
   - mesmos placeholders;
   - mesmas secoes;
   - nenhum placeholder real sem mapeamento;
   - nenhum passo da task usando API de outro tipo de arquivo.
4. Para imagens em Docs, usar insercao suportada por Docs/MCP. Se nao houver rota confiavel, substituir por pendencia explicita, nunca deixar placeholder silencioso.
5. Se o MCP do consultor nao tiver acesso de leitura/escrita, tentar plugin/conector como fallback tecnico. Se tambem falhar, pausar e pedir correcao de acesso ou executar fallback manual.

## Tamanho Dos Lotes

Decisao: nao executar os 10 templates restantes de uma vez. O limite saudavel e:

- Docs/Sheets simples: lotes de 2 a 3 templates.
- Slides pequenos: lotes de 1 a 2 templates.
- DBA/DBS/proposta: um por vez, porque o risco visual e narrativo e maior.

Isso permite executar mais sem perder QA. O gargalo nao e gerar, e garantir que cada master seja preenchivel pelos agents sem retrabalho invisivel.

## Ordem Recomendada

### Onda 1: Base de Navegacao e Controle

Criar juntos:

- F14 `master-index-guide` (Docs)
- F2 `master-kpis-sheet` (Sheets)
- F13 `master-objections-matrix` (Sheets)

Status em 2026-05-13:

- F14 criado e validado textualmente via MCP Drive do consultor: `1Y9AC2Au26nT57nGNb3pdrN-PyW-MqBcCRXyIO1U5RYA`. Usar MCP do consultor como rota primaria de validacao.
- F2 criado, primeira versao arquivada por formula quebrada, versao corrigida validada e acabamento Winning Sales aplicado via etapa 2: `13YLWDeRIXpo7iHaM4N4JCdn3yx17fGiKAJ5bJZvYebo`.
- F13 criado, validado estruturalmente e acabamento Winning Sales aplicado via etapa 2: `1U3gXSMyBOGQ4m9N5PY3PW9UxAvIdSmxJBOy06dEj4zI`.
- Ressalva operacional: quando a Sheet for liberada temporariamente como "qualquer pessoa com o link pode editar", o consultor deve voltar o compartilhamento para restrito depois do QA final.

Motivo: sao rapidos, destravam governanca do playbook e ajudam a validar o padrao Docs/Sheets antes dos decks.

QA especial:

- F14 deve virar guia de uso simples, nao landing page.
- F2 precisa ter formulas e campos de meta/atual/% atingimento.
- F13 precisa ter objecoes verbalizadas, resposta, pergunta de devolucao e prova/gancho.
- F14 precisa mapear todos os placeholders reais: `TABELA_QUANDO_CONSULTAR`, `LINKS_DRIVE`, `LISTA_PASTAS`, `CONVENCOES_VERSIONAMENTO` e `PENDENCIAS_PROJETO`.

### Onda 2: Funil e Operacao Comercial

Criar juntos:

- F1 `master-funnel-diagram-winning` (Slides)
- F5 `master-prospecting-guide-winning` (Docs)
- F5 `master-prospecting-training-winning` (Slides)
- F6 `master-outreach-matrix` (Sheets)

Motivo: consolida a base #01 e prepara os artefatos de prospeccao/outreach que dependem de ICP e KPIs.

Status em 2026-05-13:

- Pastas `03-prospeccao` e `04-outreach` criadas via MCP Drive do consultor.
- F1 criado como Google Slides nativo: `1MLhe3oKxK5hvwF6wQG-djjsTZsiOGHckpeGAV99tEMc`.
- F5 Doc criado como Google Docs nativo: `1K-zjcFpembRND6IuE2-UF1qrytpONPLmSCJWpQkea5I`.
- F5 treinamento criado como Google Slides nativo: `1tJhBAKQVAyJ8VpNMEFgdBpWO8Mk0N6n0e0GOR_wG0wg`.
- F6 criado como Google Sheets nativo e corrigido no arquivo real: `1ezEhGslMVrIf9c772mZLRr8Y_VgocJLvLXeQ1Z2vkeM`.
- QA final no Drive real confirmou: F1 com 5 slides e regra para menos/mais de 5 estagios; F5 com 16 slides e placeholders semanticos; F6 com locale `pt_BR`, 84 linhas, acentos preservados, filtros e zero formulas.
- Arquivos Office antigos foram movidos para as subpastas corretas para limpar a raiz de `Templates Master`, mas nao sao masters finais:
  - `master-funnel-diagram-winning.pptx` (`1liWJMEDyKHfgxEnam60NYzltz8JtIZIQ`)
  - `master-prospecting-training-winning.pptx` (`1Anc34o4upVTFyOThTH4nvzIxDOAstH4I`)
  - `master-outreach-matrix-winning.xlsx` (`1ASouJNizhDgFoJsv3N89MDY11zodUnbH`)

QA especial:

- F1 deve ser visualmente escaneavel, com 5 slides, estagios e criterios de saida.
- F5 deve ser guia operacional, nao texto academico.
- F5 precisa registrar os dois masters no registry: Doc e Slides.
- F6 deve ter matriz usavel, 84 linhas oficiais, filtros e placeholders de copy em colchetes.
- F6 so passa QA quando for Google Sheets nativo com filtros aplicados. CSV cru ou XLSX local nao basta.
- Aprendizado para proximas ondas: depois de qualquer conversao Office -> Google Workspace, validar o arquivo nativo real no Drive, nao apenas o fonte local.

### Onda 3: Ferramentas de Venda

Criar juntos:

- F10 `master-battle-cards` (Slides)
- F11 `master-roi-calculator` (Sheets)
- F12 `master-social-proof` (Docs + estrutura para Slides)

Motivo: estes artefatos alimentam proposta, objeções e prova de valor.

Status em 2026-05-14:

- Pastas `08-battle-cards`, `09-calculadora-roi` e `10-provas-sociais` confirmadas via MCP Drive do consultor (`thiago.cardoso@winningsales.com.br`).
- F10 final no Drive do consultor: Google Slides nativo `13Ae4tSchwM6W90vKVRRf0LRx4drcb9O8L6st7o146ns`, em `Templates Master/08-battle-cards`.
- F11 final no Drive do consultor: Google Sheets nativo `1CxI8RtqZifigfam7PhBA8NZVlaorLRSM9cTDUwbL5UY`, em `Templates Master/09-calculadora-roi`.
- F12 final no Drive do consultor: Google Docs nativo `1tqIIZajAENRPWxi1BgTxAHNoq69M1jde4gF9Gssjh2E`, em `Templates Master/10-provas-sociais`.
- F12 Slides auxiliares final no Drive do consultor: Google Slides nativo `1UbRKzI-Dt2_1xBW6vfrA6g58ZPY4Kwg1InCLDk-8SW4`, em `Templates Master/10-provas-sociais`.
- QA técnico/estratégico de conteúdo validado nos nativos de origem criados pelo conector Google Drive: F10 `1xoXhkVnHzKXatHM9PLhF7sLk2oTrDE5AvfM_PDr9jes`, F11 `1FuesU793roZjix8g6cG5T6lmsl7CggPOI3bdLnI2pco`, F12 Doc `1Hn9Nk1A79fVvKX3IzjmNU-XVkBa6mV4QycUwVCs222M` e F12 Slides `1OraLz7t9OWuK7uaI6fZ907FCe6RUvT40_1nD2DJfRLU`.
- Revalidação de acesso em 2026-05-14: após liberação para pessoas da Winning Sales, o conector Google Drive conseguiu ler os IDs finais do Drive do consultor. F10 abriu como Slides nativo, F11 abriu como Sheets nativo com locale `pt_BR` e quatro abas, F12 Doc abriu como Google Docs nativo e F12 Slides auxiliares abriu como Slides nativo.
- QA nativo de origem: F10 tem 3 slides por alternativa com campos de posicionamento; F11 está em `pt_BR`, 4 abas, fórmulas tolerantes e visual Winning Sales no arquivo real; F12 tem Doc tagueado com 5 cases e lacunas, mais Slides montáveis.

QA especial:

- F10 precisa caber em 3 cards práticos por concorrente/alternativa, com quando aparece, como posicionar, riscos, objeções prováveis, resposta recomendada, prova/argumento e perguntas de controle.
- F11 precisa ter inputs claros, fórmulas auditáveis, locale `pt_BR`, `;`, tolerância a placeholders e visual Winning Sales legível desde o master.
- F12 precisa ser biblioteca tagueada, não lista solta de cases, com tipo de prova, segmento, dor resolvida, antes/depois, métrica, frase/quote, uso recomendado, restrição de uso e link/evidência.
- Antes de iniciar a próxima wave, se o nível de auditoria exigido for 100%, repetir leitura profunda dos IDs finais com a mesma identidade Google do Drive do consultor.

### Onda 4: Decks Grandes

Criar um por vez, na ordem real de dependência:

- F7 `master-dba-template-winning`
- F8 `master-dbs-template-winning`
- F9 `master-proposal-deck-winning`

Motivo: sao os artefatos mais longos, mais visuais e mais sujeitos a desalinhamento narrativo. F9 fecha a onda porque consome o recap do DBA, a Calculadora ROI (#09) e Provas Sociais (#10).

Status em 2026-05-14:

- MCPs primarios Drive/Slides/Sheets retornaram `Auth required`; por decisao operacional do consultor, a Onda 4 foi executada via plugin/conector Google Drive na conta disponivel do Samuel, como fallback tecnico aprovado.
- F7 final copiado para o Drive do consultor: Google Slides nativo `1y5DQOjCljY18FVwMkbglWf-cBlckltXfogJ21L9eeuo`, 72 slides, nome `master-dba-template-winning`.
- F8 final copiado para o Drive do consultor: Google Slides nativo `1DshHoQYm1gUdmMWHqW9HbIHnS9dRkv3fSlBxn_QyKbk`, 48 slides, nome `master-dbs-template-winning`.
- F9 final copiado para o Drive do consultor: Google Slides nativo `1feXvh8Ox139_J1xcDqxJWScqXRrOrokZYsND9hPkgd8`, 12 slides, nome `master-proposal-deck-winning`.
- QA nativo via conector confirmou titulo, contagem, texto extraivel, placeholders em `{{UPPER_SNAKE_CASE}}`, acentos preservados e thumbnails de amostra.
- Fonte local auxiliar: `tmp-wave4/output/*.pptx` e previews em `tmp-wave4/preview/`. Estes arquivos locais nao sao master final; os masters operacionais sao os Google Slides nativos acima.
- Revalidacao de acesso em 2026-05-14: apos liberacao para pessoas da Winning Sales, o conector Google Drive conseguiu ler os tres Google Slides finais copiados no Drive do consultor: F7 com 72 slides, F8 com 48 slides e F9 com 12 slides.
- Registro operacional: os IDs de origem criados via plugin/Samuel foram F7 `1G4S_-ltWRCAU5-drduycsFZir7ccJ_Bj_w4byu1XIPA`, F8 `11hYM2tUY7HGRDV2PQpCZIQMSEf3Zz6x4aQn1RO2I638` e F9 `1GfMus2WxkEmE8W0FQai49YaTll-wnDjp3afCB_TrOvo`. A tabela operacional deve usar os IDs finais copiados ao Drive do consultor.

QA especial:

- F7 deve aplicar logica 90/10 em blocos, nao virar deck generico: 8 blocos, 72 slides, suporte a ate 6 modulos; se houver menos, o gerador remove slides excedentes; se houver mais, duplica o padrao de modulo.
- F8 deve ser continuidade do DBA, nao um novo diagnostico: 9 etapas, 48 slides, recap com `{{RECAP_DOR_PRINCIPAL_1}}`, `{{RECAP_DOR_PRINCIPAL_2}}`, `{{RECAP_OBJETIVO_PRIORITARIO}}` e `{{RECAP_DECISORES_MAPEADOS}}`.
- F9 deve ter estrutura fixa de proposta com 12 slides e puxar DBA, ROI e cases sem duplicacao: slide 3 compatível com #05, slide 8 com #10, slide 10 com #09 e slide 12 de premissas.

### Onda 4.2: QA Integrado dos Templates

Objetivo: validar os 14 templates logicos do registry, incluindo F5 Slides e F12 Slides auxiliares, contra Drive real, registry, tasks, agents, skills e checklists.

Registro detalhado: `02-Process/Runtime-Squad-Historico/wave4.2-template-qa.md`.

Status em 2026-05-14:

- Todos os 16 arquivos operacionais (14 templates logicos + 2 auxiliares) abriram por Drive ID pelo conector Google Drive, como Google Workspace nativo.
- O conector confirmou leitura de Docs, Sheets e Slides; Sheets em locale `pt_BR`; Slides com texto extraivel e thumbnails de amostra.
- Foram corrigidos os contratos locais que poderiam quebrar geracao:
  - nomes reais do Drive normalizados para `*-winning`;
  - F2 ajustado para colunas reais A:H, sem exigir Frequencia/Observacoes;
  - F5 `03_APLICACAO_*` explicitado em registry/task/checklist;
  - F12 taxonomia explicitada em registry/task/agent/checklist;
  - F12 Slides ganhou regra de duplicar layout para case 4+.
- Validacao local final: wrappers `.codex` e `.claude` sincronizados com os canônicos via `scripts/sync-agent-wrappers.js`; compatibilidade passou com 7 agents.
- Pendencia nao bloqueante para geracao: a conta atual do conector nao abriu a raiz `Squad Playbook Comercial` nem `Templates Master`, entao a pasta correta precisa de reconfirmacao com a conta owner/consultor. A geracao por Drive ID esta liberada para piloto controlado.

Resultado das validacoes locais:

- `node scripts\validate-template-registry.js --require-p0`: PASS.
- `node scripts\validate-template-registry.js --strict-drive-ids`: PASS.
- `node scripts\validate-platform-compatibility.js`: PASS.

Decisao: **pronto para piloto end-to-end controlado**, sem bloqueadores de geracao conhecidos apos as correcoes locais e a sincronizacao final dos wrappers. Antes de uma auditoria 100% de governanca do Drive, validar os parent folders com a conta owner/consultor.

## Checklist QA Final De Cada Onda

- Registry aponta para Drive IDs reais.
- Arquivos estao na pasta correta do Drive.
- Nomes antigos/rascunhos estao arquivados ou claramente fora do caminho operacional.
- Nenhum template final tem checklist interno visivel.
- Nenhum placeholder quebrado por typo.
- Nenhum texto de instrucao para o agent aparece como conteudo final do template.
- Visual usa navy/crimson/bone/paper da Winning Sales com parcimonia.
- O template e bonito o suficiente para teste fiel, mas sem complexidade que atrapalhe preenchimento.
- O agent responsavel tem informacao suficiente para preencher todos os placeholders.
- O QA visual consultou explicitamente `D:\1AWinningSales-Projetos\squadfactory\Design.md winning sales`; template que parece CSV/import cru nao passa.
- Para Sheets, design e tao obrigatorio quanto formula: cabecalho visual, hierarquia de secoes, largura legivel, congelamento/filtros quando aplicavel, cores Winning Sales e area de uso clara para o vendedor.
- Quando o MCP conectado ao Drive cria Sheets via CSV, a planilha pode ficar funcional mas visualmente crua. Isso nao passa QA. Para aplicar design Winning Sales em Sheets, usar uma destas rotas:
  - Preferencial: batch update de Google Sheets em conta com permissao de editor.
  - Alternativa controlada: consultor libera temporariamente "qualquer pessoa com o link pode editar", o agent aplica formatting batch update, valida e depois a permissao e removida.
  - Fallback manual: consultor aplica cabecalho navy/crimson, backgrounds bone/paper, bordas ink-200, congelamento, filtros, larguras e wrap seguindo este plano.

## Proximo Passo Operacional

1. Antes de cada nova onda, executar QA de contrato: arquivo real no Drive x registry x task x agent x checklist.
2. Corrigir gaps de contrato antes de criar novos templates.
3. Executar a proxima onda no tamanho definido.
4. Pausar para validacao visual/estrutural quando a onda terminar.
