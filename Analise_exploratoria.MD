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

# Análise de Dados com Pandas - Uso do GroupBy

Este documento apresenta um exemplo de análise de dados utilizando a biblioteca **Pandas** em Python, com foco no método `groupby()` para agrupar e analisar informações.

## 1. Valores Ausentes (NaN)

Em conjuntos de dados, `NaN` significa **Not a Number**, ou seja, um valor ausente ou não preenchido em uma coluna numérica.

Esses valores podem atrapalhar algumas análises, por isso muitas vezes precisamos removê-los.

Podemos remover linhas com valores ausentes utilizando o método:

```python
microdadosEnemSexoFaixaEtaria = microdadosEnemSexoFaixaEtaria.dropna()
```

Para visualizar as primeiras linhas do conjunto de dados:

```python
microdadosEnemSexoFaixaEtaria.head()
```

---

# 2. Agrupando Dados com `groupby()`

O método `groupby()` permite **agrupar dados de acordo com uma coluna** e aplicar operações estatísticas nesses grupos.

Neste exemplo, vamos agrupar os dados pela coluna **TP_SEXO** (sexo).

### Contagem de registros por sexo

```python
microdadosEnemSexoFaixaEtaria.groupby('TP_SEXO').count()
```

Esse comando mostra a **distribuição de registros separados por sexo (masculino e feminino)**.

---

# 3. Análise da Faixa Etária

## Faixa etária máxima por sexo

```python
microdadosEnemSexoFaixaEtaria.groupby('TP_SEXO').max()
```

Esse comando retorna o **valor máximo da faixa etária para cada sexo**.

---

## Faixa etária mínima por sexo

```python
microdadosEnemSexoFaixaEtaria.groupby('TP_SEXO').min()
```

Esse comando retorna o **valor mínimo da faixa etária para cada sexo**.

---

# 4. Filtrando Dados

Podemos filtrar registros antes de aplicar o `groupby()`.

Exemplo: selecionar apenas registros com **faixa etária maior que 1**.

```python
microdadosEnemSexoFaixaEtaria[
    microdadosEnemSexoFaixaEtaria.TP_FAIXA_ETARIA > 1
].groupby('TP_SEXO').min()
```

Isso retorna os valores mínimos considerando **somente registros com faixa etária acima de 1**.

---

# 5. Média por Grupo

Podemos calcular a média dos valores para cada grupo.

```python
microdadosEnemSexoFaixaEtaria.groupby('TP_SEXO').mean()
```

---

# 6. Mediana por Grupo

A mediana representa o valor central da distribuição.

```python
microdadosEnemSexoFaixaEtaria.groupby('TP_SEXO').median()
```

---

# 7. Visualização com Histograma

Também podemos gerar gráficos para visualizar a distribuição dos dados.

```python
microdadosEnemSexoFaixaEtaria.groupby('TP_SEXO').hist()
```

Isso gera **histogramas separados por sexo**, permitindo observar a distribuição dos dados.

---

# 8. Estatísticas Descritivas

Podemos obter um resumo estatístico completo utilizando:

```python
microdadosEnemSexoFaixaEtaria.groupby('TP_SEXO').describe()
```

Esse comando retorna várias métricas, como:

- count (quantidade)
- mean (média)
- std (desvio padrão)
- min (mínimo)
- 25%
- 50% (mediana)
- 75%
- max (máximo)

Isso fornece uma **visão geral completa do conjunto de dados agrupado por sexo**.

---

# Conclusão

O método `groupby()` é uma das ferramentas mais importantes do **Pandas** para análise de dados, pois permite:

- Agrupar informações
- Calcular estatísticas
- Comparar grupos
- Explorar padrões nos dados

Ele é amplamente utilizado em **análise de dados, ciência de dados e business intelligence**.

# 📊 Manipulação de Dados com Pandas

Neste exemplo será demonstrado como **criar um dicionário para traduzir códigos numéricos em descrições** e **adicionar uma nova coluna ao DataFrame** com essas informações.

O exemplo utiliza dados dos **microdados do ENEM**.

---

# 📌 Estrutura inicial do DataFrame

Ao visualizar as primeiras linhas do conjunto de dados:

```python
microdadosEnemSelecionados.head()
```

Resultado:

| NU_INSCRICAO | NU_ANO | TP_ESTADO_CIVIL | TP_ANO_CONCLUIU |
|--------------|------|----------------|----------------|
|210062064233|2024|1|3|
|210062064234|2024|1|10|
|210062064235|2024|1|9|
|210062064236|2024|1|0|
|210062064237|2024|3|18|

A coluna **TP_ESTADO_CIVIL** contém códigos numéricos que representam o estado civil do participante.

---

# 📚 Criando um dicionário de estado civil

Para tornar os dados mais compreensíveis, podemos criar um **dicionário que relaciona os códigos com suas descrições**.

```python
dicionario = {
    1: 'Solteiro',
    2: 'Casado',
    3: 'Viúvo'
}
```

Esse dicionário permite transformar códigos numéricos em valores descritivos.

---

# ➕ Criando uma nova coluna no DataFrame

Agora podemos criar uma nova coluna chamada **NO_QUALSEUESTADOCIVIL**, que irá armazenar a descrição correspondente ao código presente na coluna **TP_ESTADO_CIVIL**.

```python
microdadosEnemSelecionados['NO_QUALSEUESTADOCIVIL'] = [
    dicionario[resp] for resp in microdadosEnemSelecionados.TP_ESTADO_CIVIL
]
```

Essa operação percorre cada valor da coluna **TP_ESTADO_CIVIL** e substitui o código pelo texto correspondente no dicionário.

---

# 📊 Agrupando os dados por estado civil

Também podemos analisar a distribuição dos participantes por estado civil utilizando o método `groupby()`.

```python
microdadosEnemSelecionados.groupby('TP_ESTADO_CIVIL').count()
```

Esse comando agrupa os registros por estado civil e mostra a quantidade de ocorrências em cada categoria.

---

# 🧠 Resultado da transformação

Após executar os comandos, o DataFrame passará a ter uma nova coluna com a descrição do estado civil.

Exemplo:

| TP_ESTADO_CIVIL | NO_QUALSEUESTADOCIVIL |
|----------------|----------------------|
|1|Solteiro|
|1|Solteiro|
|1|Solteiro|
|1|Solteiro|
|3|Viúvo|

Isso facilita a interpretação dos dados durante a análise.

---

# 🚀 Conclusão

Utilizando **dicionários e manipulação de colunas no Pandas**, é possível:

- Traduzir códigos numéricos para descrições
- Tornar os dados mais legíveis
- Criar novas colunas derivadas
- Facilitar análises e visualizações

Essas técnicas são muito utilizadas em **processos de limpeza e preparação de dados (Data Cleaning)**, etapa essencial em projetos de **Análise de Dados e Ciência de Dados**.
