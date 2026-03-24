# 📊 Plotly Express - Guia Completo de Visualizações

O **Plotly Express (`plotly.express`)** é uma biblioteca Python de alto nível para criação de gráficos interativos de forma simples e rápida, muito usada em análise de dados.

---

## 📦 Instalação

```bash
pip install plotly
```

---

## 📥 Importação

```python
import plotly.express as px
```

---

## 📊 1. Histograma (Distribuição de Dados)

### 📌 Para que serve:
Mostra a distribuição de uma variável numérica, agrupando os valores em intervalos.

### 🧠 Exemplo:

```python
import plotly.express as px

df = px.data.tips()

fig = px.histogram(df, x='total_bill')
fig.show()
```

### 🔍 Principais parâmetros:
- `df`: DataFrame com os dados
- `x`: coluna numérica a ser analisada

---

## 📊 2. Gráfico de Dispersão (Scatter Plot)

### 📌 Para que serve:
Mostra a relação entre duas variáveis numéricas.

### 🧠 Exemplo:

```python
import plotly.express as px

df = px.data.iris()

fig = px.scatter(
    df,
    x='sepal_width',
    y='sepal_length',
    color='species',
    symbol='species'
)

fig.show()
```

### 🔍 Principais parâmetros:
- `x`, `y`: variáveis numéricas
- `color`: separa por categorias (cores)
- `symbol`: diferencia os pontos visualmente

---

## 📊 3. Gráfico de Barras

### 📌 Para que serve:
Comparar valores entre diferentes categorias.

### 🧠 Exemplo:

```python
import plotly.express as px

df = px.data.medals_long()

fig = px.bar(
    df,
    x='nation',
    y='count',
    color='medal',
    title='Long-Form Input'
)

fig.show()
```

### 🔍 Principais parâmetros:
- `x`: categorias
- `y`: valores numéricos
- `color`: subdivisão (ex: tipo de medalha)

---

## 🥧 4. Gráfico de Pizza

### 📌 Para que serve:
Mostrar proporções de um total.

### 🧠 Exemplo:

```python
import plotly.express as px

df = px.data.tips()

fig = px.pie(
    df,
    values='tip',
    names='day'
)

fig.show()
```

### 🔍 Principais parâmetros:
- `values`: valores numéricos
- `names`: categorias

---

## 📈 5. Gráfico de Linha (Séries Temporais)

### 📌 Para que serve:
Mostrar evolução de dados ao longo do tempo.

### 🧠 Exemplo:

```python
import plotly.express as px

df = px.data.gapminder().query("continent == 'Oceania'")

fig = px.line(
    df,
    x='year',
    y='lifeExp',
    color='country'
)

fig.show()
```

### 🔍 Principais parâmetros:
- `x`: tempo (ano, data, etc.)
- `y`: valor numérico
- `color`: separação por categorias

---

## 🚀 Resumo Geral

| Tipo de Gráfico | Uso Principal                     |
|----------------|----------------------------------|
| Histogram      | Distribuição de valores          |
| Scatter        | Relação entre variáveis          |
| Bar            | Comparação entre categorias      |
| Pie            | Proporções                       |
| Line           | Evolução ao longo do tempo       |

---

## 💡 Dica

O Plotly permite interação nos gráficos (zoom, hover, filtros), sendo muito usado em:
- Análise de Dados
- Dashboards
- Ciência de Dados
