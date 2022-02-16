---
description: >-
  Dada uma string, esta função permite inserir um ponto flutuante na posição
  antipenúltima do texto.
---

# fnc\_inserirPontoFlutuante

## Parâmetros

VARCHAR(20)

## Retorno

VARCHAR(21)

## Funcionamento

Utiliza o texto do parâmetro informado, inverte o texto, insere um "." na terceira posição e inverte novamente.

## Exemplo de execução

`SELECT [desenv].[fnc_inserirPontoFlutuante] ('242500')`

#### `Retorno`

<mark style="background-color:orange;">`2425.00`</mark>

