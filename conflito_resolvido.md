# Registro de Conflitos e Problemas Resolvidos

Este arquivo documenta os desafios técnicos encontrados durante a execução do projeto e as soluções adotadas para superá-los.

## Desafio: Erro de Correspondência de Ramificação (`pathspec 'main' did not match`)

### O Problema
Ao tentar mudar de branch e criar uma nova ramificação de trabalho utilizando o comando `git checkout main`, o Git retornou o seguinte erro no terminal:
`error: pathspec 'main' did not match any file(s) known to git`

### Diagnóstico
Ao analisar o histórico inicial do repositório através do comando `git branch`, foi identificado que o Git local estava configurado para utilizar a nomenclatura clássica e padrão **`master`** para a ramificação principal, e não `main`. Portanto, o caminho `main` era inexistente para o sistema de versionamento naquele momento.

### Solução Aplicada
1. O comando foi corrigido para apontar para a branch principal correta do repositório local: `git checkout master`.
2. A partir da branch principal identificada, novas ramificações foram geradas com sucesso seguindo o plano de trabalho estabelecido (ex: `git checkout -b feature/secao-teorica`).