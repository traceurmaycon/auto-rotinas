---
description: Gera arquivos DVC e ARCDEV do SISARC sem nenhum conteúdo.
---

# stp\_gerarArquivosDevolucaoSisarc

## Parâmetros

```
@pData DATE = NULL
@pDiretorio VARCHAR(100) = NULL
```

## Retorno

Não há tratamentos para retorno ainda.

## Dependências

``[`[desenv].[stp_gerarArquivo]`](stp\_gerararquivo.md)``

## Funcionamento

Cria uma tabela temporária global que alocará 4 linhas referentes aos headers e traillers dos dois arquivos. Utilizando um `SELECT` nessa tabela, executa dois bcps para a criação dos arquivos DVC e ARCDEV com as nomenclaturas DVC{DD}{MM}.037 e ARCDEV{DD}{MM}.TXT onde DD refere-se ao dia e o MM ao mês, ou seja, uma data que poderá ou não ser informada via parâmetro. Caso a data não seja informada, utiliza a função `GETDATE()` para usar o dia corrente do sistema.

Também poderá ser informado opcionalmente, o diretório de destino dos arquivos. Caso este não seja informado, os arquivos serão criados no C:/ da máquina executante.

## Exemplo de execução

`O exemplo abaixo entregaria os arquivos do dia 15 de maio de 2022 no diretório`` `_`C:/Arquivos/publica`_` ``da máquina`` `_`SUSIS_MONTR_004`_

`EXEC desenv.stp_gerarArquivosDevolucaoSisarc '2022-05-15', '\\10.0.20.95\Arquivos\publica'`
