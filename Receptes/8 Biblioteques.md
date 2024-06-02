---
title: Biblioteques
layout: default
nav_order: 8
parent: Receptes
author: Luis Rey
---

# Biblioteques

Importar i utilitzar només una funció de la biblioteca:

```python
from math import sqrt

base = 1
altura = 1

arrel = sqrt(base**2 + altura**2)

print(f"La diagonal mesura: {arrel:.2f}")
# La diagonal mesura: 1.41
```

Importar una biblioteca assignant-li un nom:

```python
import numpy as np

# Sistema de dos equacions i dues incognites
# 7x + 2y = 1
# -3x + 5y = 2

coeficients = np.array([[7, 2], [-3, 5]])
independents = np.array([1, 2])

solucio = np.linalg.solve(coeficients, independents)

print(f"x = {solucio[0]:.4f}, y = {solucio[1]:.4f}")
# x = 0.0244, y = 0.4146
```
