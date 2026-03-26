🧠 Passo a passo de um Analista de Dados (na prática)

✅ Etapa 1 — Entender o problema (NEGÓCIO)

👉 O que fazer:

* Ler a demanda
* Identificar o objetivo
* Saber qual decisão será tomada

👉 No seu projeto:

* Comparar preços da gasolina entre países
* Identar tendências ao longo do tempo

---

✅ Etapa 2 — Coletar os dados

👉 O que fazer:

* Buscar a base de dados
* Carregar no ambiente

👉 Código:
import pandas as pd
gas = pd.read_csv('gas_prices.csv')

---

✅ Etapa 3 — Explorar os dados (visão inicial)

👉 O que fazer:

* Ver as primeiras linhas
* Entender colunas
* Identificar tipos de dados

👉 Código:
gas.head()
gas.columns
gas.info()

---

✅ Etapa 4 — Limpar os dados

👉 O que fazer:

* Ver valores nulos
* Ver dados duplicados
* Corrigir tipos de dados

👉 Código:
gas.isnull().sum()
gas.duplicated().sum()
gas.dtypes

---

✅ Etapa 5 — Análise exploratória (EDA)

👉 O que fazer:

* Ver estatísticas gerais
* Comparar países

👉 Código:
gas.describe()

---

✅ Etapa 6 — Visualização de dados

👉 O que fazer:

* Criar gráficos
* Comparar evolução ao longo do tempo

👉 Código:
import matplotlib.pyplot as plt

plt.plot(gas['Year'], gas['USA'], label='USA')
plt.plot(gas['Year'], gas['Australia'], label='Australia')
plt.plot(gas['Year'], gas['Italy'], label='Italy')

plt.legend()
plt.show()

---

✅ Etapa 7 — Gerar insights

👉 O que fazer:

* Responder perguntas com dados
* Identificar padrões

👉 Código:
gas.mean()

---

✅ Etapa 8 — Comunicação dos resultados

👉 O que fazer:

* Explicar de forma simples
* Destacar os principais pontos

👉 Exemplo:
A Itália apresenta os maiores preços ao longo do tempo, enquanto os EUA possuem menor variação.

---

✅ Etapa 9 — (Opcional) Dashboard

👉 O que fazer:

* Criar painel visual interativo
* Facilitar tomada de decisão

👉 Ferramentas:
Power BI
Tableau

---

🔥 Resumo final:

Entender problema → Coletar dados → Explorar → Limpar → Analisar → Visualizar → Gerar insights → Comunicar → Dashboard
