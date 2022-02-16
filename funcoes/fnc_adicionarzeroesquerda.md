---
description: Adiciona zeros à esquerda de um determinado número.
---

# fnc\_adicionarZeroEsquerda

## Parâmetros

```
@pNumero	VARCHAR(480)
@pPosicoes	SMALLINT
@pTipoCampo     SMALLINT = 0
```

## Retorno

VARCHAR(480)

## Funcionamento

Insere no texto informado em `pNumero`, uma quantidade de zeros que façam com que o número de caracteres de `pNumero` + os zeros inseridos completem a quantidade de caracteres informada em `pPosicoes`. `pTipoCampo` define como será o tratamento de `pNumero` e o retorno tal como abaixo:\
**0** - DEFAULT. Apenas acrescenta os zeros à esquerda.\
**1** - Transforma um número inteiro em valor monetário sem a separação por ponto flutuante e acrescenta zeros à esquerda. \
**2** - Transforma um valor monetário informado em `pNumero` (já com o ponto flutante), retirando o ponto e acrescentado os zeros.

## Exemplos de execução

### Utilizando o tipo de campo 0

`SELECT [desenv].[fnc_adicionarZeroEsquerda] ('12345', 10, 0)`

#### `Retorno`

`0000012345`

### Utilizando o tipo de campo 1

`SELECT [desenv].[fnc_adicionarZeroEsquerda] ('2645', 8, 1)`

#### `Retorno`

`00264500`

{% hint style="info" %}
Informar um número inteiro em `pNumero` produzirá o mesmo resultado, deixando opcional informar o parâmetro como inteiro ou varchar. Este tipo de opção funciona tanto para o tipo 0, quanto para o tipo 1.
{% endhint %}

### Utilizando o tipo de campo `2`

`SELECT [desenv].[fnc_adicionarZeroEsquerda] ('1245.43', 7, 2)`

#### `Retorno`

`0124543`

{% hint style="info" %}
Informar um _float_ (número com ponto flutuante) ou um varchar também gerará o mesmo resultado para o tipo 2.
{% endhint %}

### Outras situações

Informar um número de posições iguais a quantidade de caracteres manterá o resultado inalterado para o tipo 0, truncará dois algarismos à esquerda para o tipo 1 (já que os zeros a direita são acrescentados primeiro) e também truncará dois algarismos à esquerda para o tipo 2 (mas neste caso, o ponto flutuante será removido e acrescentará os dois zeros a direita).

`SELECT [desenv].[fnc_adicionarZeroEsquerda] (1234, 4, 0)`\
`SELECT [desenv].[fnc_adicionarZeroEsquerda] (1234, 4, 1)`\
`SELECT [desenv].[fnc_adicionarZeroEsquerda] (1234.00, 4, 2)`

#### `Retorno`

`1234`\
`3400`\
`3400`

{% hint style="info" %}
Caso não seja utilizado ponto flutuante para o tipo 2, ele tratará o resultado como o tipo 1 faria.
{% endhint %}
