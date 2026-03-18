# 🐼 Modificando DataFrames com Pandas

Este guia mostra como filtrar e modificar dados em um DataFrame utilizando a biblioteca **Pandas** no Python.

---

## 📌 Cenário

Imagine que você possui uma planilha de vendas de casas e precisa atualizar informações, como o nome de um vendedor que saiu da empresa.

---

## 🔎 1. Filtrando dados

Antes de modificar, é importante localizar os dados desejados.

```python
df.loc[df['SellerG'] == 'Nelson']
```

Esse comando retorna todas as linhas onde o vendedor (`SellerG`) é igual a **Nelson**.

---

## ✏️ 2. Alterando um valor específico

Para substituir um valor por outro:

```python
df.loc[df['SellerG'] == 'Nelson', 'SellerG'] = 'Ronald'
```

Aqui estamos alterando todos os registros onde o vendedor era **Nelson** para **Ronald**.

---

## 🧠 Estrutura genérica

```python
df.loc[
    df['coluna_condicao'] == 'valor_procurado',
    'coluna_alvo'
] = 'novo_valor'
```

---

## 🔄 3. Alterando outra coluna com base em uma condição

Exemplo: alterar o método (`Method`) para "Pending" quando o vendedor for Ronald:

```python
df.loc[df['SellerG'] == 'Ronald', 'Method'] = 'Pending'
```

---

## ⚠️ 4. Alterando múltiplas colunas

Para modificar mais de uma coluna ao mesmo tempo:

```python
df.loc[df['SellerG'] == 'Ronald', ['Method', 'Type']] = 'Pending'
```

---

## 🧠 Estrutura genérica para múltiplas colunas

```python
df.loc[
    df['coluna_condicao'] == 'valor_procurado',
    ['coluna1', 'coluna2']
] = 'novo_valor'
```

---

## ❗ Observações importantes

* Sempre use aspas (`' '`) para valores do tipo string.
* Para múltiplas colunas, utilize **lista** (`[ ]`) e não parênteses (`( )`).
* Certifique-se de que os nomes das colunas estão corretos.
* Evite erros de digitação (ex: `f.loc` ao invés de `df.loc`).

---

## ✅ Conclusão

Com o `.loc[]`, você consegue:

* Filtrar dados com precisão
* Atualizar valores específicos
* Modificar múltiplas colunas de forma eficiente

Essa técnica é essencial para limpeza e transformação de dados em projetos de análise de dados 🚀
