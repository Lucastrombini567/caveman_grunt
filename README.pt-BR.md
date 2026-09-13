# Caveman

Fale como um homem das cavernas inteligente: mesma capacidade, menos tokens.

[Read in English](README.md)

## O que a skill faz

A Caveman comprime respostas removendo artigos não essenciais, enrolação,
formalidades e repetições. Ela preserva incertezas importantes, detalhes
técnicos, blocos de código, mensagens de erro e símbolos. O resultado depende
do modelo e da tarefa; não há promessa de uma porcentagem fixa de economia. O
modo escolhido permanece ativo até ser alterado ou desligado.

Ela só orienta o estilo da resposta: não substitui o modelo, não altera suas
ferramentas nem reduz sua capacidade de raciocínio disponível. A Caveman foi
feita para preservar a qualidade da entrega enquanto remove palavras
desnecessárias; avalie fluxos importantes com seu próprio modelo e tarefa.

Há quatro níveis:

| Nível | Mudança |
| --- | --- |
| `lite` | Remove enrolação, mas mantém frases completas. Profissional e direto. |
| `full` | Padrão. Remove artigos não essenciais; frases curtas e fragmentos claros são permitidos. |
| `ultra` | Máxima compressão com clareza. Não inventa abreviações nem usa setas para indicar causa. |
| `grunt` | Só quando solicitado. Respostas mínimas completas ou estado breve de uma ação. |

Em avisos, ações irreversíveis, sequências ambíguas ou pedidos de explicação,
a Caveman usa linguagem normal e clara naquela parte da resposta.

## Economia de tokens

A Caveman tende a reduzir tokens de saída por tornar as respostas menores, mas
o ganho depende do modelo, da tarefa e do modo escolhido. Ela não promete uma
porcentagem fixa.

O fluxo relacionado `caveman-compress` mediu cerca de **46% menos tokens de
entrada** ao comprimir arquivos de instrução. Esse número vale para arquivos
comprimidos, não para toda resposta no modo Caveman. Meça suas próprias sessões
antes de usar uma estimativa para custo.

## Desenvolvimento

Desenvolvida pelo GPT-5.6 Astra usando Ultracode, em conjunto com Fable 5.1
Ultracode.

## Como instalar

Copie os arquivos deste repositório para a pasta de skills, mantendo esta
estrutura:

```text
skills/
└── caveman/
    ├── SKILL.md
    └── references/
        └── grunt.md
```

## Como usar

```text
/caveman              # modo full, padrão
/caveman lite         # compressão mais leve
/caveman ultra        # maior compressão em linguagem normal
/caveman grunt        # respostas mínimas completas e estado de ações
/caveman off          # volta à linguagem normal
```

Também é possível dizer “stop caveman” ou “normal mode”.

## Exemplo

Pergunta: “Explique pool de conexões de banco de dados.”

Resposta normal:

> Um pool de conexões reutiliza conexões abertas com o banco de dados em vez de criar uma conexão a cada requisição, reduzindo o custo de preparação.

Caveman (`full`):

> Pool reutiliza conexões abertas do banco. Menos preparação por requisição.

Caveman (`ultra`):

> Reutiliza conexões do banco. Reduz preparação.

Pedido: “Atualize o README e me avise quando terminar.”

Caveman (`grunt`), após a atualização concluir:

> feito.

Pedido: “Atualize estes três arquivos.”

Quando duas atualizações dão certo e a terceira falha, o Grunt informa o estado
real em vez de dizer que nada aconteceu:

> 2 de 3 arquivos atualizados; o terceiro falhou.
