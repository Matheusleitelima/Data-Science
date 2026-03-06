# 📊 Análise de Microdados do ENEM com Pandas

Este documento apresenta os principais comandos utilizados para análise de dados utilizando **Python, Pandas e Matplotlib** aplicados aos microdados do ENEM.

O objetivo é demonstrar operações comuns de **manipulação, filtragem, agrupamento e análise estatística de dados**.

---

# 📚 Comandos Utilizados

| 🧠 Comando / Sintaxe                                   | 🎯 O que faz                                                  | 💻 Exemplo de uso                                                                  |
| ------------------------------------------------------ | ------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| `import pandas as pd`                                  | Importa a biblioteca Pandas para manipulação de dados.        | `df = pd.read_csv("arquivo.csv")`                                                  |
| `import matplotlib.pyplot as plt`                      | Importa Matplotlib para criação de gráficos.                  | `plt.plot([1,2,3],[4,5,6]); plt.show()`                                            |
| `microdadosEnem.columns.values`                        | Visualiza todos os nomes das colunas do DataFrame.            | `print(microdadosEnem.columns.values)`                                             |
| `colunasSelecionadasEnem = [ ... ]`                    | Cria uma lista com as colunas desejadas.                      | `colunasSelecionadasEnem = ['TP_SEXO','TP_FAIXA_ETARIA']`                          |
| `microdadosEnem.filter(items=colunasSelecionadasEnem)` | Filtra o DataFrame mantendo apenas as colunas selecionadas.   | `microdadosEnemSelecionado = microdadosEnem.filter(items=colunasSelecionadasEnem)` |
| `microdadosEnemSelecionado.head()`                     | Exibe as 5 primeiras linhas do DataFrame.                     | `microdadosEnemSelecionado.head()`                                                 |
| `microdadosEnem[0:100]`                                | Seleciona as 100 primeiras linhas do DataFrame.               | `microdadosEnem[0:100]`                                                            |
| `amostra = microdadosEnem[0:100]`                      | Armazena as 100 primeiras linhas em uma variável.             | `amostra = microdadosEnem[0:100]`                                                  |
| `microdadosEnemSelecionado['NO_MUNICIPIO_PROVA']`      | Seleciona apenas a coluna de município.                       | `municipios = microdadosEnemSelecionado['NO_MUNICIPIO_PROVA']`                     |
| `.value_counts()`                                      | Conta a frequência de cada valor na coluna.                   | `microdadosEnemSelecionado['TP_SEXO'].value_counts()`                              |
| `.sort_index()`                                        | Ordena os valores pelo índice (ordem alfabética ou numérica). | `microdadosEnemSelecionado['TP_SEXO'].value_counts().sort_index()`                 |
| `microdadosEnemSelecionado['TP_FAIXA_ETARIA']`         | Seleciona coluna de faixa etária.                             | `faixa = microdadosEnemSelecionado['TP_FAIXA_ETARIA']`                             |
| `.hist(bins=30)`                                       | Cria histograma para visualizar distribuição dos dados.       | `microdadosEnemSelecionado['TP_FAIXA_ETARIA'].hist(bins=30); plt.show()`           |
| `microdadosEnemSelecionado['TP_SEXO']`                 | Seleciona coluna de sexo.                                     | `coluna_TP_SEXO = microdadosEnemSelecionado['TP_SEXO']`                            |
| `distInSexo = coluna_TP_SEXO.value_counts()`           | Armazena contagem absoluta por categoria.                     | `distInSexo = coluna_TP_SEXO.value_counts()`                                       |
| `percentInSexo = 100 * distInSexo / distInSexo.sum()`  | Calcula percentual de cada categoria.                         | `percentInSexo = 100 * distInSexo / distInSexo.sum()`                              |
| `distInSexo.sum()`                                     | Soma o total de ocorrências.                                  | `total = distInSexo.sum()`                                                         |
| `.dropna()`                                            | Remove linhas com valores ausentes (NaN).                     | `microdadosEnemSexoFaixaEtaria = microdadosEnemSexoFaixaEtaria.dropna()`           |
| `.groupby('TP_SEXO')`                                  | Agrupa os dados pela coluna de sexo.                          | `microdadosEnemSexoFaixaEtaria.groupby('TP_SEXO')`                                 |
| `.groupby('TP_SEXO').count()`                          | Conta a quantidade de registros em cada grupo.                | `microdadosEnemSexoFaixaEtaria.groupby('TP_SEXO').count()`                         |
| `.groupby('TP_SEXO').max()`                            | Retorna o valor máximo de cada grupo.                         | `microdadosEnemSexoFaixaEtaria.groupby('TP_SEXO').max()`                           |
| `.groupby('TP_SEXO').min()`                            | Retorna o valor mínimo de cada grupo.                         | `microdadosEnemSexoFaixaEtaria.groupby('TP_SEXO').min()`                           |
| `.groupby('TP_SEXO').mean()`                           | Calcula a média dos valores em cada grupo.                    | `microdadosEnemSexoFaixaEtaria.groupby('TP_SEXO').mean()`                          |
| `.groupby('TP_SEXO').median()`                         | Calcula a mediana dos valores em cada grupo.                  | `microdadosEnemSexoFaixaEtaria.groupby('TP_SEXO').median()`                        |
| `df[df.coluna > valor]`                                | Filtra registros que atendem uma condição.                    | `microdadosEnemSexoFaixaEtaria[microdadosEnemSexoFaixaEtaria.TP_FAIXA_ETARIA>1]`   |
| `.groupby('TP_SEXO').hist()`                           | Cria histogramas separados para cada grupo.                   | `microdadosEnemSexoFaixaEtaria.groupby('TP_SEXO').hist()`                          |
| `.groupby('TP_SEXO').describe()`                       | Retorna estatísticas completas para cada grupo.               | `microdadosEnemSexoFaixaEtaria.groupby('TP_SEXO').describe()`                      |

---

# 📈 Análises Possíveis

Utilizando esses comandos é possível:

- Analisar a **distribuição de participantes por sexo**
- Verificar **faixa etária mínima e máxima**
- Calcular **média e mediana da idade**
- Visualizar **distribuição dos dados com histogramas**
- Obter **estatísticas completas do conjunto de dados**

---

# 🧠 Conceitos Importantes

### NaN
`NaN` significa **Not a Number**, indicando que um valor está ausente ou não foi preenchido.

Esses valores podem ser removidos usando:

```python
df.dropna()
```

---

### GroupBy

O método `groupby()` é uma das ferramentas mais importantes do **Pandas**, pois permite:

- Agrupar dados por categorias
- Aplicar funções estatísticas
- Comparar diferentes grupos
- Identificar padrões nos dados

---

# 🚀 Conclusão

A utilização de **Pandas** permite realizar análises de dados de forma rápida e eficiente.

Com poucos comandos é possível:

- Manipular grandes volumes de dados
- Realizar análises estatísticas
- Criar visualizações
- Identificar padrões importantes

Essas técnicas são amplamente utilizadas em áreas como:

- **Análise de Dados**
- **Ciência de Dados**
- **Business Intelligence (BI)**
- **Pesquisa acadêmica**
