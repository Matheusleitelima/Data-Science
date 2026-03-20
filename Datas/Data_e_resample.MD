# 📊 Trabalhando com Datas e Resample no Pandas

Antes de utilizar o `resample()`, é necessário preparar corretamente os dados de data no DataFrame.

---

## 🔹 1. Converter a coluna para datetime

```python
df['Date'] = pd.to_datetime(df['Date'], dayfirst=True)
```

### 📌 Explicação:

* Converte a coluna `Date` para o tipo datetime
* `dayfirst=True` indica que o formato está como dia/mês/ano

---

## 🔹 2. Definir a coluna como índice

```python
df.set_index('Date', inplace=True)
```

### 📌 Explicação:

* O `resample()` só funciona com índices do tipo data
* Aqui definimos a coluna `Date` como índice do DataFrame

---

## 🔹 3. Estrutura do resample()

```python
df.resample('TEMPO').AGREGAÇÃO()
```

### 📌 Exemplos:

```python
df.resample('M').mean(numeric_only=True)
```

* Agrupa os dados por mês
* Calcula a média das colunas numéricas

```python
media_mensal = df.resample('M')['Price'].mean()
```

* Calcula a média mensal apenas da coluna `Price`

---

## 🔹 Frequências mais usadas

| Código | Significado |
| ------ | ----------- |
| `'D'`  | Diário      |
| `'W'`  | Semanal     |
| `'M'`  | Mensal      |
| `'Y'`  | Anual       |

---

## 🔹 4. Contagem de registros por mês

```python
df_vendas_mes = df.resample('MS').size()
```

### 📌 Explicação:

* `'MS'` = Month Start (início de cada mês)
* `.size()` = conta a quantidade de registros por período
* Resultado: total de registros (ex: vendas) por mês

---

## 🔹 5. Formatando o índice

```python
df_vendas_mes.index = df_vendas_mes.index.strftime('%m/%Y')
```

### 📌 Explicação:

* Converte o índice de data para string formatada
* `%m` = mês
* `%Y` = ano

📌 Exemplo de saída:

```
01/2024
02/2024
03/2024
```

---

## 🔹 Resultado final

```python
df_vendas_mes
```

### 📌 Exemplo:

```
01/2024    120
02/2024    98
03/2024    150
```

* Índice → mês/ano
* Valor → quantidade de registros no mês

---

## 🧠 Resumo

1. Converter a coluna para datetime
2. Definir como índice
3. Usar `resample()` para agrupar por tempo
4. Aplicar uma agregação (`mean`, `sum`, `size`, etc.)
5. (Opcional) formatar o índice para visualização

---
