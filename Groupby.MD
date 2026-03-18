# 📊 Agrupando Dados com GroupBy no Pandas

Este guia mostra como utilizar o método `groupby()` para agrupar e analisar dados em um DataFrame com **Pandas**.

---

## 📌 Agrupando por vendedores

Para agrupar os dados pela coluna `SellerG` (vendedores) e calcular a média apenas das colunas numéricas:

```python
df.groupby('SellerG').mean(numeric_only=True)
```

✔️ Calcula a média de cada vendedor considerando apenas colunas numéricas.

---

## 💰 Somando valores e ordenando do maior para o menor

Para identificar quais vendedores geraram mais valor financeiro:

```python
df.groupby('SellerG').sum(numeric_only=True).sort_values('Price', ascending=False)
```

✔️ Agrupa por vendedor
✔️ Soma os valores numéricos
✔️ Ordena pela coluna `Price` do maior para o menor

---

## 🏆 Top 10 vendedores

Para visualizar os 10 vendedores com maior volume financeiro:

```python
df.groupby('SellerG').sum(numeric_only=True).sort_values('Price', ascending=False).head(10)
```

✔️ Retorna apenas os 10 primeiros resultados após ordenação

---

## 🔢 Contando registros por vendedor

Para contar quantas vendas cada vendedor realizou:

```python
df.groupby('SellerG').count().sort_values('Price', ascending=False).head(10)
```

✔️ Conta a quantidade de registros por vendedor
✔️ Ordena do maior para o menor
✔️ Mostra os 10 principais

---

## 🧠 Explicação dos métodos

### 🔹 `sum(numeric_only=True)`

Soma apenas as colunas que possuem valores numéricos.

---

### 🔹 `sort_values('Price', ascending=False)`

Ordena os dados com base na coluna `Price`:

* `ascending=False` → ordem decrescente (maior para menor)
* `ascending=True` → ordem crescente (menor para maior)

---

### 🔹 `head(10)`

Retorna apenas os **10 primeiros registros** do resultado.

---

### 🔹 `count()`

Conta a quantidade de valores não nulos em cada coluna por grupo.

---

## ✅ Conclusão

Com o `groupby()`, você consegue:

* Agrupar dados de forma eficiente
* Realizar cálculos como média e soma
* Identificar padrões e rankings (ex: melhores vendedores)

Essa técnica é essencial para análise de dados e muito utilizada no mercado 🚀
