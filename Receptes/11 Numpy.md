---
title: Numpy
layout: default
nav_order: 11
parent: Receptes
author: Luis Rey
date: 2024/5/25
toc: true
---

# Numpy

Llibreria matemàtica, només treballa amb valors numèrics.

Importació:

```python
import numpy as np
```

1. Índex
{:toc}

## Arranjaments, *Array*


Arrays d'una i dues dimensions:

```python
u = np.array([2, -3.4, 0.5, -8])

m = np.array([
    [0, 1, -2],
    [4, 0, -2],
    [3, 6, -2]])
```

Matemàticament, serien un vector en un espai de 4 dimensions i una matriu bidimensional 3x3:

$$\vec{u}=(2, -3.4, 0.5, 8)$$

$$m=\begin{pmatrix}0 & 1 & -2\\
    4 & 0 & -2\\
    3 & 6 & -2\end{pmatrix}$$

## Operacions matricials

Element a element (+, -, *, /, %, **)

```python
m = np.array([
    [0, 1, -2],
    [4, 0, -2],
    [3, 6, -2]])

n = np.array([
    [0, 1, 0],
    [5, 7, 1],
    [3, -2, -2]])

suma = m + n
# [[ 0  2 -2]
#  [ 9  7 -1]
#  [ 6  4 -4]]

producte_elements = m*n
# [[  0   1   0]
#  [ 20   0  -2]
#  [  9 -12   4]]
```

$$
\begin{pmatrix}
    0& 1& -2\\
    4& 0& -2\\
    3& 6& -2
\end{pmatrix}
+
\begin{pmatrix}
    0& 1& 0\\
    5& 7& 1\\
    3& -2& -2
\end{pmatrix}
=
\begin{pmatrix}
    0&  2 &-2\\
    9 & 7 &-1\\
    6  &4 &-4
\end{pmatrix}
$$

Determinant, producte matricial, matriu transposada i matriu inversa.

```python
m = np.array([
    [0, 1, -2],
    [4, 0, -2],
    [3, 6, -2]])

determinant_m = np.linalg.det(m)
# -45.999999999999986

producte = m.dot(m)
# [[ -2 -12   2]
#  [ -6  -8  -4]
#  [ 18  -9 -14]]

transposada = m.T
# [[ 0  4  3]
#  [ 1  0  6]
#  [-2 -2 -2]]

inversa = np.linalg.inv(m)
# [[-0.26086957  0.2173913   0.04347826]
#  [-0.04347826 -0.13043478  0.17391304]
#  [-0.52173913 -0.06521739  0.08695652]]
```

$$\begin{pmatrix}
    0& 1& -2\\
    4& 0& -2\\
    3& 6& -2
\end{pmatrix}
\cdot
\begin{pmatrix}
    0& 1& 0\\
    5& 7& 1\\
    3& -2& -2
\end{pmatrix}
=
\begin{pmatrix}
    -2 & -12 & 2\\
    -6 & -8 & -4\\
    18 & -9 & -14
\end{pmatrix}
$$

$$
\begin{pmatrix}
    0& 1& -2\\
    4& 0& -2\\
    3& 6& -2
\end{pmatrix}
^{-1}=
\begin{pmatrix}
    -0.26086957 & 0.2173913 & 0.04347826\\
    -0.04347826 & -0.13043478 & 0.17391304\\
    -0.52173913 & -0.06521739 & 0.08695652\\
\end{pmatrix}
$$

Solució de sistemes d'equacions

$$
\left\{
\begin{array}{l}
y-2z=2 \\
4x-2z=3.4 \\
3x+6y-2z=0.5
\end{array}
\right.
$$

```python
u = np.array([2, -3.4, 0.5])

m = np.array([
    [0, 1, -2],
    [4, 0, -2],
    [3, 6, -2]])
solucio = np.linalg.solve(m, u))
# [-1.23913043  0.44347826 -0.77826087]
```

## Estadística

Nombre de dades, màxim, mitjana, mediana, variància, desviació estàndard:

```python
valors = np.array([1, 2, 1, 1, 2, 4, 4, 6, 2, 4])
n = valors.size()
# 10
maxim = valors.max()
# 6
lloc_maxim = valors.argmax()
# 7
mitjana = valors.mean()
# 2.7
mediana = np.median(valors)
# 2
variancia = np.var(valors)
# 2.6100000000000003
desv_std = valors.std()
# 1.6155494421403513
```

Recompte de freqüències

```python
valors = np.array([1, 2, 1, 1, 2, 4, 4, 6, 2, 4])
valors_unics, freq = np.unique(valors, return_counts=True)
# Valors únics [1 2 4 6]
# Freqüències [3 3 3 1]
```

## Creació de sèries de valors

Lineals. Calcula 10 valors entre 0 i 2.

```python
a = np.linspace(0, 2, 10)
# [0. 0.22222222 0.44444444 0.66666667 0.88888889 1.11111111
#  1.33333333 1.55555556 1.77777778 2.]
```

Creació de sèries i operacions element a element

```python
def taula_de_valors():
    x_min = 5
    x_max = -5
    n = 256

    x = np.linspace(x_min, x_max, n)
    y = x * np.exp(-x + 2) - np.pi / 2

    return x, y
```

Aleatoris. Calcula 5 valors aleatoris entre 0 i 1.

```python
# Valors aleatoris entre 0 i 1
b = np.random.rand(5)
print(b)
# [0.86358864 0.71676764 0.28196914 0.53730704 0.76879061]
```

Aleatoris segons la [distribució normal](<https://es.wikipedia.org/wiki/Distribuci%C3%B3n_normal>). Calcula 256 valors de la distribució de mitjana 2.5 i de desviació estàndard 0.33.

```python
c = np.random.normal(loc = 2.5, scale = 0.33, size = 256)
# [2.76860884 3.04145216 2.09841131 2.02484919 2.39297482 ...
```
