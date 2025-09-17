# Pandas - Biblioteca Python para Manipulação de Dados

O **Pandas** é uma biblioteca Python amplamente utilizada para **análise e manipulação de dados**. Ela permite trabalhar com grandes volumes de dados e extrair informações úteis de forma eficiente.

## Principais conceitos:

- **Row (Linha):** Representa uma linha do conjunto de dados.  
- **Column (Coluna):** Representa uma coluna do conjunto de dados.  
- **DataFrame:** Estrutura que combina linhas e colunas, permitindo organizar e manipular os dados de maneira semelhante a uma planilha Excel.

## Funcionalidades:

- Leitura e gravação de arquivos em diversos formatos, incluindo **CSV, Excel, JSON, SQL** e outros.  
- Manipulação de dados: filtragem, ordenação, agregação e limpeza.  
- Extração de informações úteis de grandes volumes de dados.  
- **Visualização de dados:** Pandas permite gerar gráficos simples diretamente a partir dos dados, facilitando a análise visual.

## Documentação:

1. Pesquise no Google por **"Pandas documentation"**.  
2. Acesse o site oficial do Pandas e vá em **Getting Started** para aprender como utilizar a biblioteca.  
3. A documentação mostra como **ler, manipular, salvar e visualizar dados** usando Pandas.

> O Pandas é ideal para análise de dados, estatísticas, preparação de dados para aprendizado de máquina e criação de gráficos básicos para visualização.

# Abrindo Arquivos com Pandas

O **Pandas** permite abrir e manipular arquivos de diferentes formatos de forma simples e eficiente.

## 1. Importando Pandas

No **Jupyter Lab**, digite na primeira célula:

```python
import pandas as pd


2. Abrindo arquivos CSV

Na célula seguinte, crie uma variável para armazenar os dados:
# Substitua o caminho pelo local do seu arquivo
dados = pd.read_csv('__MACOSX/fifa.csv')

# Mostrar os dados
print(dados)
# ou apenas
dados

O Pandas lê o arquivo e exibe as informações na tela.

A leitura é feita automaticamente de acordo com o tipo de dados presente no arquivo.


3. Abrindo páginas web (HTML)

# Substitua 'url' pela página que contém a tabela
dados_html = pd.read_html('url')
Também é possível ler tabelas diretamente de páginas web:
# Exibe as tabelas encontradas
print(dados_html)


