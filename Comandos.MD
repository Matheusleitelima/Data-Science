| 🧠 Comando / Sintaxe                                   | 🎯 Objetivo                                                    |
| ------------------------------------------------------ | -------------------------------------------------------------- |
| `import pandas as pd`                                  | Importar a biblioteca Pandas para manipulação de dados.        |
| `import matplotlib.pyplot as plt`                      | Importar Matplotlib para criação de gráficos.                  |
| `microdadosEnem.columns.values`                        | Visualizar todos os nomes das colunas do DataFrame.            |
| `colunasSelecionadasEnem = [ ... ]`                    | Criar lista com as colunas desejadas.                          |
| `microdadosEnem.filter(items=colunasSelecionadasEnem)` | Filtrar o DataFrame mantendo apenas as colunas selecionadas.   |
| `microdadosEnemSelecionado.head()`                     | Exibir as 5 primeiras linhas do DataFrame.                     |
| `microdadosEnem[0:100]`                                | Selecionar as 100 primeiras linhas do DataFrame.               |
| `amostra = microdadosEnem[0:100]`                      | Armazenar as 100 primeiras linhas em uma variável.             |
| `microdadosEnemSelecionado['NO_MUNICIPIO_PROVA']`      | Selecionar apenas a coluna de município.                       |
| `.value_counts()`                                      | Contar a frequência de cada valor na coluna.                   |
| `.sort_index()`                                        | Ordenar os valores pelo índice (ordem alfabética ou numérica). |
| `microdadosEnemSelecionado['TP_FAIXA_ETARIA']`         | Selecionar coluna de faixa etária.                             |
| `.hist(bins=30)`                                       | Criar histograma para visualizar distribuição dos dados.       |
| `microdadosEnemSelecionado['TP_SEXO']`                 | Selecionar coluna de sexo.                                     |
| `distInSexo = coluna_TP_SEXO.value_counts()`           | Armazenar contagem absoluta por sexo.                          |
| `percentInSexo = 100 * distInSexo / distInSexo.sum()`  | Calcular percentual de cada categoria.                         |
| `distInSexo.sum()`                                     | Somar total de ocorrências para cálculo proporcional.          |
