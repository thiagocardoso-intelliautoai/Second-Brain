# Day-to-Day Use

## Como usar no dia a dia

Use este sistema como contexto operacional para IA, nao como museu de notas.

Fluxo simples:

1. Capture rapido em `01-Inbox/`.
2. Se for projeto da Winning Sales, mova para `04-Work-Winning-Sales/Projects/`; se for cliente ou mentoria, use `05-Clients-and-Mentoring/`.
3. Se for ideia de conteudo, mova para `06-Personal-Brand/Linkedin/Ideias-Brutas/`.
4. Se virar metodo repetivel, destile para `07-Frameworks-and-Processes/`.
5. Se for fonte externa, coloque em `09-Sources-and-References/`.

Quando o Inbox acumular, peca:

```text
Organiza o Inbox lendo `01-Inbox/AGENTS.md`.
```

## Como chamar uma IA

Em uma conversa nova, mande algo como:

```text
Leia primeiro:
D:\1A-Projetos-Pessoais\Second Brain\00-Start-Here\AI-READ-ME-FIRST.md

Depois leia a pasta/arquivo relevante para esta tarefa:
[cole o caminho]
```

## Como adicionar material legado depois

1. Coloque o raw import em `10-Legacy-Imports/`.
2. Registre fonte, URL ou caminho, data e origem.
3. Classifique o conteudo: raw idea, framework, projeto, referencia, decisao, draft, processo ou documentacao tecnica.
4. Crie uma versao distilled apenas se houver uso real.
5. Preserve a linguagem original se for conteudo de voz pessoal.

## Como preservar sua voz

Quando escrever LinkedIn:

- mantenha frase bruta se ela tiver energia;
- nao corrija ate virar texto de consultoria generica;
- se a ideia estiver confusa, separe `Original` e `Versao sugerida`;
- preserve ganchos, expressoes e raciocinio proprio;
- so reescreva com permissao explicita ou em uma secao separada.

## Como usar com Obsidian

Abra `D:\1A-Projetos-Pessoais\Second Brain` como vault.

Use busca global para encontrar:

- `status: raw`
- `10-Legacy-Imports`
- `do-not-rewrite`
- nomes de projetos;
- nomes de clientes;
- frameworks.

## Como usar com Claude ou Codex

Para tarefas grandes, sempre aponte o arquivo de start:

`00-Start-Here/AI-READ-ME-FIRST.md`

Depois aponte o dominio:

- LinkedIn: `06-Personal-Brand/`
- LinkedIn Content OS: `06-Personal-Brand/Linkedin/AGENTS.md`
- automacao: `07-Frameworks-and-Processes/`
- cliente: `05-Clients-and-Mentoring/`
- Winning Sales: `04-Work-Winning-Sales/`

## Git depois

Se quiser versionar:

1. Inicializar Git na raiz do vault.
2. Commitar mudancas importantes.
3. Ignorar arquivos sensiveis se algum dia forem adicionados.
4. Usar Git como historico, nao como ferramenta obrigatoria do sistema.
