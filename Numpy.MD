# 📊 NumPy - Guia Básico

## 📌 O que é o NumPy?
O NumPy é uma biblioteca do Python responsável por trabalhar com arrays (listas otimizadas), permitindo operações matemáticas rápidas e eficientes.

🔗 Documentação oficial: https://numpy.org/

---

## 📦 Diferença entre lista e NumPy array

```python
import numpy as np

a = [1, 2, 3, 4, 5]        # Lista Python
b = np.array([1, 2, 3, 4, 5])  # NumPy array

print(a)
print(b)
```

✅ Diferenças:
- Array do NumPy não mostra vírgulas ao imprimir
- Consome menos memória
- Muito mais rápido para cálculos

---

## 🔢 Dimensões de Arrays

### 📍 Array 1D
```python
d1 = np.array([1, 2, 3])
print(d1)

print(d1.ndim)  # Mostra a dimensão (1D)
```

---

### 📍 Array 2D (Matriz)
```python
d2 = np.array([[1, 2, 3], [4, 5, 6]])
print(d2)

print(d2.ndim)  # Mostra a dimensão (2D)
```

---

### 📍 Array 3D
```python
d3 = np.array([[[1, 2], [4, 5]], [[7, 8], [10, 11]]])
print(d3)

print(d3.ndim)  # Mostra a dimensão (3D)
```

---

## 📐 Shape (Formato do Array)

```python
d2 = np.array([[1, 2, 3], [4, 5, 6]])
print(d2.shape)  # (2, 3)
```

📌 Significa:
- 2 linhas
- 3 colunas

---

## ➕ Operações com Arrays

### Soma de arrays
```python
a = np.array([2, 3, 4])
b = np.array([2, 3, 4])

result = np.add(a, b)
print(result)  # [4 6 8]
```

📌 Soma elemento por elemento:
- 2 + 2
- 3 + 3
- 4 + 4

---

## 🔍 Seleção de elementos

```python
a = np.array([[2, 3, 4, 5], [2, 7, 8, 9]])
print(a)
```

Representação:
```
[[2 3 4 5]
 [2 7 8 9]]
```

Índices:
```
   colunas →  0 1 2 3
linhas
   0        [2 3 4 5]
   1        [2 7 8 9]
```

---

### 📌 Acessar um elemento específico

```python
a[1, 2]
```
Resultado:
```
8
```

---

### 📌 Mostrar uma linha inteira

```python
a[0, :]
```

📌 `:` significa "todas as colunas"

---

### 📌 Mostrar uma coluna inteira

```python
a[:, 1]
```

📌 `:` significa "todas as linhas"

---

## 📊 Axis (Eixo)

- `axis=0` → opera nas colunas
- `axis=1` → opera nas linhas

Exemplo:
```python
np.sum(a, axis=0)  # Soma das colunas
np.sum(a, axis=1)  # Soma das linhas
```

---

## 🚀 Resumo

- NumPy trabalha com arrays mais rápidos que listas
- Pode ter 1D, 2D, 3D ou mais dimensões
- Permite operações matemáticas eficientes
- Facilita manipulação de dados (base para análise de dados)

---
