# 🧹 Limpando espaços em colunas no Pandas

Ao trabalhar com dados no Pandas, é muito comum encontrar **espaços indesejados** nos nomes das colunas ou nos valores. Isso pode causar erros em filtros, consultas e análises.

---

## 📌 Removendo espaços dos nomes das colunas

### ✅ 1. Remover espaços no início e fim

```python
df.columns = df.columns.str.strip()
```

**Exemplo:**

```
" Price " → "Price"
```

---

### ✅ 2. Remover todos os espaços

```python
df.columns = df.columns.str.replace(' ', '')
```

**Exemplo:**

```
"Sale Price" → "SalePrice"
```

---

### ✅ 3. Substituir espaços por underline (boa prática)

```python
df.columns = df.columns.str.replace(' ', '_')
```

**Exemplo:**

```
"Sale Price" → "Sale_Price"
```

---

### ✅ 4. Padronização completa (recomendado 🔥)

```python
df.columns = df.columns.str.strip().str.lower().str.replace(' ', '_')
```

**Exemplo:**

```
" Sale Price " → "sale_price"
```

---

## 📌 Removendo espaços dos valores das colunas

Às vezes o problema está nos dados dentro das colunas:

```python
df['Address'] = df['Address'].str.strip()
```

---

## 🚀 Dica de ouro

Sempre que carregar um dataset, faça essa padronização:

```python
df.columns = df.columns.str.strip().str.lower().str.replace(' ', '_')
```

Isso evita erros futuros, principalmente ao usar métodos como `query()`.

Limpeza de dados

df.isnull().sum()
df.dtypes
df.duplicated().sum()

---

## ⚠️ Observações

* `.str.strip()` → remove espaços no início e fim
* `.str.replace(' ', '_')` → substitui espaços
* `.str.lower()` → padroniza para minúsculo

---

## ✅ Conclusão

Limpar e padronizar os nomes das colunas é uma etapa essencial no pré-processamento de dados, garantindo mais organização, legibilidade e menos erros durante a análise.
