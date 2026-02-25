# 📊 Guia de Comandos - Pandas e Matplotlib

  -------------------------------------------------------------------------------------------------------------------------------------------------------------------
  🧠 Sintaxe                                               🎯 O que faz          💻 Exemplo de uso
  -------------------------------------------------------- --------------------- ------------------------------------------------------------------------------------
  `import pandas as pd`                                    Importa a biblioteca  `df = pd.read_csv("arquivo.csv")`
                                                           Pandas para           
                                                           manipulação de dados. 

  `import matplotlib.pyplot as plt`                        Importa o Matplotlib  `plt.plot([1,2,3],[4,5,6]); plt.show()`
                                                           para criação de       
                                                           gráficos.             

  `microdadosEnem.columns.values`                          Exibe todos os nomes  `print(microdadosEnem.columns.values)`
                                                           das colunas do        
                                                           DataFrame.            

  `colunasSelecionadasEnem = [ ... ]`                      Cria lista com as     `colunasSelecionadasEnem = ['TP_SEXO', 'TP_FAIXA_ETARIA']`
                                                           colunas desejadas.    

  `microdadosEnem.filter(items=colunasSelecionadasEnem)`   Filtra o DataFrame    `microdadosEnemSelecionado = microdadosEnem.filter(items=colunasSelecionadasEnem)`
                                                           mantendo apenas as    
                                                           colunas selecionadas. 

  `microdadosEnemSelecionado.head()`                       Exibe as 5 primeiras  `microdadosEnemSelecionado.head()`
                                                           linhas do DataFrame.  

  `microdadosEnem[0:100]`                                  Seleciona as 100      `microdadosEnem[0:100]`
                                                           primeiras linhas do   
                                                           DataFrame.            

  `amostra = microdadosEnem[0:100]`                        Armazena as 100       `amostra = microdadosEnem[0:100]`
                                                           primeiras linhas em   
                                                           uma variável.         

  `microdadosEnemSelecionado['NO_MUNICIPIO_PROVA']`        Seleciona apenas a    `municipios = microdadosEnemSelecionado['NO_MUNICIPIO_PROVA']`
                                                           coluna de município.  

  `.value_counts()`                                        Conta a frequência de `microdadosEnemSelecionado['TP_SEXO'].value_counts()`
                                                           cada valor na coluna. 

  `.sort_index()`                                          Ordena os valores     `microdadosEnemSelecionado['TP_SEXO'].value_counts().sort_index()`
                                                           pelo índice (ordem    
                                                           alfabética ou         
                                                           numérica).            

  `microdadosEnemSelecionado['TP_FAIXA_ETARIA']`           Seleciona coluna de   `faixa = microdadosEnemSelecionado['TP_FAIXA_ETARIA']`
                                                           faixa etária.         

  `.hist(bins=30)`                                         Cria histograma para  `microdadosEnemSelecionado['TP_FAIXA_ETARIA'].hist(bins=30); plt.show()`
                                                           visualizar            
                                                           distribuição dos      
                                                           dados.                

  `microdadosEnemSelecionado['TP_SEXO']`                   Seleciona coluna de   `coluna_TP_SEXO = microdadosEnemSelecionado['TP_SEXO']`
                                                           sexo.                 

  `distInSexo = coluna_TP_SEXO.value_counts()`             Armazena contagem     `distInSexo = coluna_TP_SEXO.value_counts()`
                                                           absoluta por sexo.    

  `percentInSexo = 100 * distInSexo / distInSexo.sum()`    Calcula percentual de `percentInSexo = 100 * distInSexo / distInSexo.sum()`
                                                           cada categoria.       

  `distInSexo.sum()`                                       Soma total de         `total = distInSexo.sum()`
                                                           ocorrências para      
                                                           cálculo proporcional. 
  -------------------------------------------------------------------------------------------------------------------------------------------------------------------
