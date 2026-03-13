# Filtrando Dados com Pandas

Este documento mostra como realizar **filtros em um DataFrame** utilizando **condições lógicas** com a biblioteca **Pandas** no Python.

## Importando os dados

```python
import pandas as pd

df = pd.read_csv("brutos/DADOS/house.csv")
```

---

# Filtrando Dados

A filtragem de dados permite selecionar apenas as linhas que atendem a determinadas **condições lógicas**.

Utilizamos principalmente:

- `df.loc[]` → para acessar linhas por condição
- operadores lógicos:
  - `==` igual
  - `<=` menor ou igual
  - `&` AND (e)
  - `|` OR (ou)

---

# 1️⃣ Filtrar casas com **3 quartos**

```python
filter1 = df.loc[df['Rooms'] == 3]
filter1
```

Esse filtro retorna todas as linhas onde a coluna **Rooms** é igual a **3**.

---

# 2️⃣ Filtrar casas com **3 quartos e do tipo house**

```python
filter1 = df.loc[(df['Rooms'] == 3) & (df['Type'] == 'h')]
filter1
```

Nesse caso temos duas condições:

- `Rooms == 3`
- `Type == 'h'`

O operador `&` indica que **as duas condições precisam ser verdadeiras**.

---

# 3️⃣ Filtrar casas com **3 quartos, do tipo house e preço menor ou igual a 100 mil dólares**

```python
filter1 = df.loc[
    (df['Rooms'] == 3) &
    (df['Type'] == 'h') &
    (df['Price'] <= 100000)
]

filter1
```

Aqui aplicamos **três filtros ao mesmo tempo**:

1. Casas com **3 quartos**
2. Tipo **house**
3. Preço **menor ou igual a 100000**

---

# Observação importante

Quando usamos **mais de uma condição**, cada condição precisa estar **entre parênteses**.

Exemplo correto:

```python
(df['Rooms'] == 3) & (df['Type'] == 'h')
```

---

# Conclusão

O uso de filtros com `loc` e operadores lógicos permite realizar **análises específicas em datasets**, selecionando apenas os dados relevantes para estudo ou visualização.
