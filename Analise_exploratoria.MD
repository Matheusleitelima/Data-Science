# 📊 Análise Exploratória de Dados -- Microdados ENEM

## 📌 Descrição

Este projeto apresenta uma **Análise Exploratória de Dados (EDA)**
utilizando os microdados do ENEM.\
O objetivo é compreender a estrutura do conjunto de dados, selecionar
variáveis relevantes e analisar distribuições e proporções para melhor
entendimento do dataset.

------------------------------------------------------------------------

## 🛠️ Bibliotecas Utilizadas

``` python
import pandas as pd
import matplotlib.pyplot as plt
```

------------------------------------------------------------------------

## 🔎 1. Visualização das Colunas

Para visualizar todas as colunas disponíveis no dataset:

``` python
microdadosEnem.columns.values
```

Esse comando retorna todas as variáveis presentes no conjunto de dados.

------------------------------------------------------------------------

## 🎯 2. Seleção de Colunas Específicas

Criação de uma lista contendo as colunas desejadas:

``` python
colunasSelecionadasEnem = [
    'NU_INSCRICAO',
    'NU_ANO',
    'TP_FAIXA_ETARIA',
    'TP_SEXO',
    'TP_ESTADO_CIVIL',
    'TP_COR_RACA',
    'TP_NACIONALIDADE',
    'TP_ST_CONCLUSAO',
    'TP_ANO_CONCLUIU',
    'TP_ENSINO',
    'IN_TREINEIRO',
    'CO_MUNICIPIO_PROVA',
    'NO_MUNICIPIO_PROVA',
    'CO_UF_PROVA',
    'SG_UF_PROVA'
]
```

Filtragem do DataFrame:

``` python
microdadosEnemSelecionado = microdadosEnem.filter(items=colunasSelecionadasEnem)
```

Visualização das primeiras linhas:

``` python
microdadosEnemSelecionado.head()
```

------------------------------------------------------------------------

## 📌 3. Seleção de Intervalo de Linhas

Para selecionar um intervalo específico de registros:

``` python
microdadosEnem[0:100]
```

Também é possível atribuir a uma variável:

``` python
amostra = microdadosEnem[0:100]
```

------------------------------------------------------------------------

## 🏙️ 4. Análise por Município

Seleção da coluna:

``` python
coluna_NO_MUNICIPIO_PROVA = microdadosEnemSelecionado['NO_MUNICIPIO_PROVA']
```

Contagem de ocorrências por município:

``` python
coluna_NO_MUNICIPIO_PROVA.value_counts().sort_index()
```

-   `value_counts()` realiza a contagem dos valores.
-   `sort_index()` organiza os resultados em ordem alfabética.

------------------------------------------------------------------------

## 👥 5. Análise por Faixa Etária

Seleção da coluna:

``` python
coluna_TP_FAIXA_ETARIA = microdadosEnemSelecionado['TP_FAIXA_ETARIA']
```

Distribuição das faixas etárias:

``` python
coluna_TP_FAIXA_ETARIA.value_counts().sort_index()
```

------------------------------------------------------------------------

## 📊 6. Visualização Gráfica

Construção de histograma para análise da distribuição etária:

``` python
coluna_TP_FAIXA_ETARIA.hist(bins=30)
```

-   `hist()` gera o gráfico de distribuição.
-   `bins` define a quantidade de intervalos do histograma.

------------------------------------------------------------------------

## ⚖️ 7. Percentual por Sexo

Seleção da coluna:

``` python
coluna_TP_SEXO = microdadosEnemSelecionado['TP_SEXO']
```

Distribuição absoluta:

``` python
distInSexo = coluna_TP_SEXO.value_counts()
```

Cálculo do percentual:

``` python
percentInSexo = 100 * distInSexo / distInSexo.sum()
```

Exemplo de resultado:

    TP_SEXO
    F    60.573619
    M    39.426381

------------------------------------------------------------------------

## 🔎 loc

Loc: localizar dentro dos dados um dado específico.

EX: quem tiver a nacionalidade brazil.

``` python
microdadosEnem.loc[microdadosEnem['TX_COR'] == 'AZUL']
```

Vai filtrar somente as linhas onde `TX_COR = AZUL`.

------------------------------------------------------------------------

## 📊 sort

``` python
microdadosEnem.sort_values('TX_GABARITO')
```

Organiza em ordem alfabética e numérica.

------------------------------------------------------------------------

``` python
microdadosEnem.sort_values('TX_GABARITO', ascending=False)
```

Inverte a ordem da lista.

------------------------------------------------------------------------

``` python
microdadosEnem.sort_values(['TX_GABARITO', 'TX_MOTIVO_ABAN'])
```

Ordena utilizando duas colunas ao mesmo tempo.


## ✅ Conclusão

A Análise Exploratória de Dados permitiu:

-   Selecionar e organizar variáveis relevantes;
-   Analisar a distribuição por município;
-   Avaliar a distribuição por faixa etária;
-   Visualizar dados graficamente;
-   Calcular proporções percentuais por sexo.

Essa etapa é essencial para compreensão inicial do dataset e preparação
para análises estatísticas ou modelagens futuras.
