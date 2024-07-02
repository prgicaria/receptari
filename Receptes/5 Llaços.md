---
title: Llaços While i For
layout: default
nav_order: 5
parent: Receptes
---

# Llaços While i For

En general, és preferible un *while*. No es necessita conèixer per avançat el nombre d'iteracions i es poden posar condicions de sortida.

Un llaç *for* s'utilitza per recórrer una llista o quan coneixem el nombre d'iteracions.

## While

Llaç amb condició de sortida. L'ordre *'+= 1'* augmenta en  el valor del comptador:

```python
comptador = 0
while comptador < LIMIT:
    comptador += 1
    print(comptador)
```

Llaç indefinit per a diverses entrades:

```python
nombre = 42
while nombre != int(input("Entra un número: ")):
    print("No has encertat!")

print("Per fi has trobat el número 42!")
```

## For

Per recórrer una llista:

```python
valors = [-3, 4.3, 9.1]
for xi in valors:
    print(xi**2)
# Resultat:
# 9
# 18.49
# 82.81
```

Exemple amb un nombre conegut d'iteracions:

```python
for i in range(3):
    print(i)
# Resultat:
# 0
# 1
# 2
```

Exemple de llaços niats, un llaç dintre d'un altre llaç:

```python
for i in range(1,11):
    print(f"Taula del {i}:")
    for j in range(1,11):
        print(f"{i} x {j} = {i*j}")
```
