# 📊 Ambiente de Análise de Dados em Python

Este repositório contém anotações e instruções para **configuração de um ambiente de análise de dados em Python**, utilizando **ambiente virtual**, **bibliotecas científicas** e **Jupyter Notebook**, com foco no uso de **microdados (ex: ENEM)**.

---

## ✅ Pré-requisitos

* **Python 3.x** instalado
* Sistema operacional: **Windows, Linux ou macOS**
* Acesso ao **Prompt de Comando / Terminal**

### Verificar se o Python está instalado

Abra o **CMD como administrador** e execute:

```bash
python
```

Se o terminal retornar a versão do Python, ele já está instalado corretamente.

---

## 🧪 Criando um Ambiente Virtual

Ambientes virtuais isolam dependências do projeto, evitando conflitos entre bibliotecas.

### Criar o ambiente virtual

```bash
python -m venv analise-dados
```

---

## ▶️ Ativando o Ambiente Virtual

### Windows

```bash
analise-dados\Scripts\activate
```

### Linux / macOS

```bash
source analise-dados/bin/activate
```

Quando ativado, o nome do ambiente aparecerá no início do terminal.

---

## 📦 Gerenciador de Pacotes (PIP)

### Verificar / Atualizar o PIP

```bash
py -m pip install --upgrade pip
```

Documentação oficial:
👉 [https://pip.pypa.io/en/stable/installation/](https://pip.pypa.io/en/stable/installation/)

---

## 📚 Instalando Bibliotecas Necessárias

Execute os comandos abaixo **com o ambiente virtual ativado**:

### Pandas

```bash
python -m pip install pandas
```

### SciPy

```bash
python -m pip install scipy
```

### Matplotlib

```bash
python -m pip install matplotlib
```

---

## 📓 Instalando o Jupyter Notebook

```bash
python -m pip install notebook
```

### Executar o Jupyter

```bash
python -m notebook
```

Caso ocorra erro, utilize:

```bash
python -m jupyter lab --no-browser
```

Copie e cole no navegador um dos endereços exibidos no terminal:

* [http://localhost:8888/lab?token=](http://localhost:8888/lab?token=)...
* [http://127.0.0.1:8888/lab?token=](http://127.0.0.1:8888/lab?token=)...

---

## 📂 Organização de Pastas no Jupyter

1. Ao abrir o Jupyter, localize a pasta do ambiente virtual:

   ```
   analise-dados/
   ```

2. Dentro dela, crie uma nova pasta para o projeto (ex: `enem-analise`)

3. Dentro dessa pasta, crie um **Notebook Python 3**

---

## ✍️ Uso do Notebook

* Utilize células do tipo **Markdown** para textos e anotações
* Utilize células do tipo **Code** para códigos Python

---

## 📥 Leitura dos Microdados

### Importar o Pandas

```python
import pandas as pd
```

### Ler o arquivo CSV

> ⚠️ O arquivo precisa estar dentro da pasta do projeto (ou subpastas).

Exemplo de leitura:

```python
microdadosEnem = pd.read_csv(
    "brutos/DADOS/ITENS_PROVA_2024.csv",
    sep=";",
    encoding="ISO-8859-1"
)
```

---

## 🔍 Visualização dos Dados

### Visualizar as primeiras linhas

```python
microdadosEnem.head()
```

> Exibe as **5 primeiras linhas** e todas as colunas do DataFrame.

### Exibir o DataFrame completo

```python
microdadosEnem
```

---

## 📌 Observações Importantes

* Sempre ative o ambiente virtual antes de rodar o projeto
* Use nomes de pastas e arquivos sem espaços
* Prefira versionar apenas **código e notebooks**, não dados sensíveis

---

## 🚀 Objetivo do Repositório

Este repositório serve como **base de estudos em Análise de Dados com Python**, focando em:

* Manipulação de dados com Pandas
* Exploração de microdados
* Visualização de dados
* Boas práticas de organização de projetos

---

✍️ Autor: **Matheus**
📘 Curso: Análise e Desenvolvimento de Sistemas
