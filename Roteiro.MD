# 📊 Guia Prático de Pandas para Análise de Dados

Este guia contém os principais comandos do Pandas usados no dia a dia de um analista de dados, com explicação e exemplos práticos.

---

# 🧠 1. Leitura de dados

## 📌 CSV
```python
df = pd.read_csv('arquivo.csv')
```

### Exemplo:
```python
df = pd.read_csv('vendas.csv', sep=';', encoding='utf-8')
```

**Explicação:**
- `sep` → separador de colunas
- `encoding` → evita erro com acentos

---

## 📌 Excel
```python
df = pd.read_excel('arquivo.xlsx')
```

---

# 🔍 2. Exploração inicial

## 📌 Primeiras linhas
```python
df.head(10)
```

**Explicação:** Mostra as primeiras 10 linhas

---

## 📌 Informações gerais
```python
df.info()
```

**Explicação:** Tipos de dados, valores nulos e quantidade de registros

---

## 📌 Estatísticas
```python
df.describe()
```

**Explicação:** Média, mínimo, máximo, desvio padrão

---

## 📌 Dimensão
```python
df.shape
```

**Explicação:** Retorna (linhas, colunas)

---

# 🧹 3. Limpeza de dados

## 📌 Valores nulos
```python
df.isnull().sum()
```

---

## 📌 Preencher nulos
```python
df['coluna'] = df['coluna'].fillna(0)
```

### Exemplo:
```python
df['salario'] = df['salario'].fillna(df['salario'].mean())
```

---

## 📌 Remover nulos
```python
df.dropna(inplace=True)
```

---

## 📌 Remover duplicados
```python
df.drop_duplicates(inplace=True)
```

---

# 🔎 4. Seleção de dados

## 📌 Selecionar coluna
```python
df['nome']
```

---

## 📌 Múltiplas colunas
```python
df[['nome', 'idade']]
```

---

## 📌 Filtrar dados
```python
df[df['idade'] > 18]
```

---

## 📌 Múltiplas condições
```python
df[(df['idade'] > 18) & (df['cidade'] == 'Fortaleza')]
```

**Operadores:**
- `&` → AND
- `|` → OR

---

# 📊 5. Agrupamento

## 📌 GroupBy
```python
df.groupby('cidade')['salario'].mean()
```

---

## 📌 Múltiplas agregações
```python
df.groupby('cidade').agg({
    'salario': 'mean',
    'idade': 'max'
})
```

---

# 🔢 6. Ordenação

## 📌 Ordenar valores
```python
df.sort_values(by='salario', ascending=False)
```

---

# ➕ 7. Criar e transformar colunas

## 📌 Nova coluna
```python
df['salario_anual'] = df['salario'] * 12
```

---

## 📌 Apply (função personalizada)
```python
df['nivel'] = df['salario'].apply(lambda x: 'Alto' if x > 5000 else 'Baixo')
```

---

# 🔄 8. Junção de dados

## 📌 Merge
```python
df_final = pd.merge(df1, df2, on='id', how='inner')
```

**Tipos:**
- `inner` → interseção
- `left` → tudo da esquerda
- `right` → tudo da direita

---

# 📅 9. Datas

## 📌 Converter para datetime
```python
df['data'] = pd.to_datetime(df['data'])
```

---

## 📌 Extrair informações
```python
df['ano'] = df['data'].dt.year
df['mes'] = df['data'].dt.month
```

---

# 📊 10. Análise exploratória

## 📌 Frequência
```python
df['cidade'].value_counts()
```

---

## 📌 Correlação
```python
df.corr()
```

---

## 📌 Histograma
```python
df['salario'].hist()
```

---

# ⚡ 11. Comandos mais usados

```python
df.head()
df.info()
df.isnull().sum()
df.dropna()
df.fillna()
df.groupby()
df.sort_values()
df.merge()
df.value_counts()
```

---

# 🚀 Fluxo real de um analista

1. Ler dados → `read_csv`
2. Explorar → `head`, `info`
3. Limpar → `fillna`, `dropna`
4. Filtrar → `df[...]`
5. Analisar → `groupby`
6. Ordenar → `sort_values`
7. Apresentar → gráficos ou BI

---

# 💡 Conclusão

Dominando esses comandos, você cobre cerca de **80% das tarefas reais de análise de dados**.
