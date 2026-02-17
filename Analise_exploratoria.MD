# 📊 Análise Exploratória de Dados -- Microdados ENEM

## 📌 Descrição

Este documento apresenta o processo de Análise Exploratória de Dados
(EDA) realizado com os microdados do ENEM, utilizando Python e
bibliotecas de análise de dados.

------------------------------------------------------------------------

## 🛠️ Bibliotecas Utilizadas

``` python
import pandas as pd
import matplotlib.pyplot as plt
```

------------------------------------------------------------------------

## 1️⃣ Visualização das Colunas do Dataset

``` python
microdadosEnem.columns.values
```

------------------------------------------------------------------------

## 2️⃣ Seleção de Colunas Específicas

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

``` python
microdadosEnemSelecionado = microdadosEnem.filter(items=colunasSelecionadasEnem)
microdadosEnemSelecionado.head()
```

------------------------------------------------------------------------

## 3️⃣ Seleção de Intervalo de Linhas

``` python
microdadosEnem[0:100]
```

------------------------------------------------------------------------

## 4️⃣ Análise por Município

``` python
coluna_NO_MUNICIPIO_PROVA = microdadosEnemSelecionado['NO_MUNICIPIO_PROVA']
coluna_NO_MUNICIPIO_PROVA.value_counts().sort_index()
```

------------------------------------------------------------------------

## 5️⃣ Análise por Faixa Etária

``` python
coluna_TP_FAIXA_ETARIA = microdadosEnemSelecionado['TP_FAIXA_ETARIA']
coluna_TP_FAIXA_ETARIA.value_counts().sort_index()
```

------------------------------------------------------------------------

## 6️⃣ Visualização Gráfica

``` python
coluna_TP_FAIXA_ETARIA.hist(bins=30)
plt.xlabel("Faixa Etária")
plt.ylabel("Quantidade")
plt.title("Distribuição por Faixa Etária")
plt.show()
```

------------------------------------------------------------------------

## 7️⃣ Análise Percentual por Sexo

``` python
coluna_TP_SEXO = microdadosEnemSelecionado['TP_SEXO']
distInSexo = coluna_TP_SEXO.value_counts()
percentInSexo = 100 * distInSexo / distInSexo.sum()
```

Forma alternativa:

``` python
percentInSexo = coluna_TP_SEXO.value_counts(normalize=True) * 100
```

Exemplo de resultado:

    TP_SEXO
    F    60.57%
    M    39.42%

------------------------------------------------------------------------

## ✅ Considerações Finais

A Análise Exploratória de Dados permitiu compreender a estrutura do
dataset, identificar padrões de distribuição e calcular métricas
percentuais relevantes para entendimento inicial dos dados.
