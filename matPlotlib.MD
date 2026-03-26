# 📊 Matplotlib

O **Matplotlib** é uma biblioteca do Python utilizada para **visualização de dados**.  
Ela permite criar diversos tipos de gráficos de forma simples e personalizável.

---

## 🔎 Sobre a biblioteca

- Responsável pela criação de gráficos em Python
- Muito utilizada em análise de dados e ciência de dados
- Funciona bem em conjunto com bibliotecas como NumPy e Pandas

---

## 📚 Documentação oficial

Acesse a documentação completa no link abaixo:  
👉 https://matplotlib.org/

# 📊 Criando Gráficos com Matplotlib

## 📌 Importando bibliotecas
import pandas as pd
import matplotlib.pyplot as plt
import numpy as np

---

## 📈 Comparando o preço do combustível entre países
plt.plot(gas['Year'], gas['Australia'])
plt.plot(gas['Year'], gas['Italy'])
plt.plot(gas['Year'], gas['USA'])

plt.show()

---

## 📝 Adicionando título e legendas
plt.title('Valores do combustível em US$')

plt.plot(gas['Year'], gas['Australia'], label='Australia')
plt.plot(gas['Year'], gas['Italy'], label='Italy')
plt.plot(gas['Year'], gas['USA'], label='USA')
plt.plot(gas['Year'], gas['Japan'], label='Japan')

plt.xticks(gas['Year'][::4])  # Mostra de 4 em 4 anos

plt.legend()
plt.show()

---

## 🎨 Formatando cores e estilos
plt.title('Valores do combustível em US$')

plt.plot(gas['Year'], gas['Australia'], 'r-', label='Australia')
plt.plot(gas['Year'], gas['Italy'], 'y-', label='Italy')
plt.plot(gas['Year'], gas['USA'], 'b-', label='USA')
plt.plot(gas['Year'], gas['Japan'], 'g-', label='Japan')

plt.xticks(gas['Year'][::4])

plt.xlabel('Years')
plt.ylabel('US$')

plt.legend()
plt.show()

---

## 💡 Sobre cores e estilos
'r-'  = vermelho linha contínua  
'r--' = vermelho tracejado  
'b-'  = azul  
'g-'  = verde  
'y-'  = amarelo  

---

## 🔁 Selecionando países com lista
list_country = ['Australia', 'USA', 'Canada']

for country in gas.columns:
    if country in list_country:
        plt.plot(gas['Year'], gas[country], label=country, marker='.')

plt.legend()
plt.show()

---

## 💾 Salvando gráfico
list_country = ['Australia', 'USA', 'Canada']

for country in gas.columns:
    if country in list_country:
        plt.plot(gas['Year'], gas[country], label=country, marker='.')

plt.legend()

plt.savefig('country.png')  # salvar antes do show
plt.show()

---

## 📌 Observações importantes
- Sempre usar plt.savefig() antes do plt.show()
- Use gas.columns para percorrer as colunas
- Use gas[country] para acessar os dados
- plt.xticks melhora a visualização do eixo X
