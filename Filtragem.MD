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

# Filtrando Dados com Regular Expression (Regex) no Pandas

Este guia mostra como realizar **filtros em colunas de texto** utilizando **expressões regulares (Regex)** com a biblioteca **Pandas** no Python.

Esse tipo de filtragem é muito útil quando os dados possuem **textos misturados** ou **informações combinadas na mesma coluna**, como endereço com número e nome da rua.

---

# Importando as bibliotecas

Primeiro, precisamos importar o **Pandas** e o módulo **re** (responsável por trabalhar com expressões regulares).

```python
import pandas as pd
import re

df = pd.read_csv("brutos/DADOS/house.csv")
```

---

# Filtrar casas de uma rua específica

Suponha que a coluna **Address** contém valores como:

```
123 Turner St
45 Turner St
78 Smith Rd
```

Se quisermos filtrar apenas casas da rua **Turner St**, podemos usar:

```python
filter2 = df.loc[df['Address'].str.contains('Turner St')]
filter2
```

Esse filtro retorna todas as linhas onde a coluna **Address** contém o texto **Turner St**.

---

# Filtrar mais de uma rua

Também é possível filtrar **múltiplos valores** utilizando o operador `|`, que significa **OU (OR)**.

```python
filter2 = df.loc[df['Address'].str.contains('Turner St|Turner Rd')]
filter2
```

Nesse caso, o filtro retorna linhas que contenham:

- **Turner St**
- **Turner Rd**

---

# Ignorar diferenças entre letras maiúsculas e minúsculas

Em datasets reais, podem existir **variações na escrita**, como:

```
Turner St
TURNER ST
turner st
```

Para ignorar diferenças entre **maiúsculas e minúsculas**, usamos o parâmetro `flags=re.I`.

```python
filter2 = df.loc[df['Address'].str.contains('Turner St|Turner Rd', flags=re.I)]
filter2
```

O parâmetro:

```
flags=re.I
```

faz com que o filtro **ignore diferenças entre letras maiúsculas e minúsculas**.

---

# Conclusão

A utilização de **expressões regulares (Regex)** no Pandas permite realizar filtros mais flexíveis em colunas de texto.

Principais vantagens:

- Filtrar **partes de textos**
- Buscar **múltiplos padrões**
- Ignorar diferenças de **maiúsculas e minúsculas**
- Trabalhar com **dados inconsistentes**

Essas técnicas são muito utilizadas em **análise de dados e limpeza de datasets**.
