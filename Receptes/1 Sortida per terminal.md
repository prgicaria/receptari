---
title: Entrada per teclat
layout: default
nav_order: 1
parent: Receptes
---

# Sortida per terminal

Sortida senzilla de text per terminal:

```python
print("Missatge que es mostra per pantalla")
```

Sortida senzilla d'una variable per terminal:

```python
print(variable)
```

## Sortida amb format

Sortida amb format del valor d'una variable:

```python
print(f"Missatge que es mostra, {variable}")
```

Sortida amb format d'una variable amb decimals. S'indica el nombre de decimals a mostrar (en l'exemple 4 decimals):

```python
print(f"Missatge que es mostra, {variable:.4f}")
```

Sortida amb format d'una variable amb decimals. S'indica el nombre de xifres significatives a mostrar (en l'exemple 4 decimals):

```python
print(f"Missatge que es mostra, {variable:.4g}")
```
