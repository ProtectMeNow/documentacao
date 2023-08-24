# Branches

## Introdução

Para o padrão de branches, irão ter 4 tipos:

- main
- develop
- feature
- fix

A **main** é branch de produção, onde fica o código final, ou seja, o código que foi testado pronto para
ser utilizado pelo consumidor. Já a **develop** terá código de desenvolvimento, que será devidamente testado para ser
mandado para **main**. A **feature** são as branches criada para desenvolvimento das tarefas,  e por fim, a **fix**
serve para corrigir erros e bugs na branch **develop**.

![branches](../../_media/git-github/branches.svg)

## Nomes de branches

| Nome                       | Tipo    | Descrição                |
| -------------------------- | ------- | ------------------------ |
| ```feature/nome-feature``` | feature | Para toda a nova tarefa  |
| ```fix/nome-feature```     | fix     | Correção de erros e bugs |

## Como criar branch

Para criar uma nova branch faça os seguintes passos:

1. Primeiro acesse a branch origem com o comando ```checkout```:

```bash
git checkout develop
```

2. Depois adicione a flag ```-b``` junto ao comando ```checkout```:

```bash
git checkout -b feature/nome-feature
```

Agora já pode começar o desenvolvimento.
