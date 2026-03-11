# 📤 Exportação de Dados com Pandas

Durante a análise de dados, muitas vezes precisamos **salvar os resultados processados** para utilização posterior, compartilhamento ou criação de relatórios.
A biblioteca **Pandas** permite exportar dados facilmente para diferentes formatos, como **CSV, Excel e TXT**.

## 🔹 Reiniciando o Kernel

Caso ocorra algum erro de biblioteca ou ambiente no **Jupyter Notebook**, pode ser necessário reiniciar o kernel:

* Clique com o **botão direito no notebook**
* Selecione **Restart Kernel**

Isso reinicia o ambiente de execução e evita conflitos de memória ou bibliotecas.

---

# 📄 Exportando para CSV

Para salvar um DataFrame em formato **CSV**:

```python
dados.to_csv('dados1.csv')
```

O arquivo será salvo **no mesmo diretório do notebook ou script Python**.

### Removendo a coluna de índice

Por padrão, o Pandas exporta o **índice do DataFrame**.
Para evitar isso:

```python
dados.to_csv('dados1.csv', index=False)
```

---

# 📊 Exportando para Excel

Para salvar os dados em formato **Excel (.xlsx)**:

```python
dados.to_excel('dados.xlsx', index=False)
```

⚠️ Observação:
Pode ser necessário instalar a biblioteca **openpyxl**:

```bash
pip install openpyxl
```

---

# 📑 Exportando para TXT

Também é possível salvar os dados em **arquivo de texto (.txt)**.

Exemplo usando **tabulação como separador**:

```python
dados.to_csv('dados3.txt', index=False, sep='\t')
```

### Explicação

* `sep='\t'` → define **tabulação** como delimitador.
* Isso evita o uso da vírgula `,` padrão do CSV.

---

# 📂 Onde os arquivos são salvos?

Os arquivos exportados serão salvos **no mesmo diretório onde o notebook ou script está sendo executado**.

---

# 🚀 Resumo

| Formato | Comando                                            |
| ------- | -------------------------------------------------- |
| CSV     | `dados.to_csv('dados.csv', index=False)`           |
| Excel   | `dados.to_excel('dados.xlsx', index=False)`        |
| TXT     | `dados.to_csv('dados.txt', sep='\t', index=False)` |

---

✔️ Esses formatos são muito utilizados em **análise de dados**, **integração com outras ferramentas** e **compartilhamento de resultados**.
