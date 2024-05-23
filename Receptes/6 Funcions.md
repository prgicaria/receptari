---
title: Funcions
layout: default
nav_order: 6
parent: Receptes
---

# Funcions

## Definició d'una funció i utilització

```python
def nom_funcio(argument1, argument2, ...):
    '''Nom de la funció. Descripció curta

    Descripció detallada

    Arguments:
        argument1: explicació argument 1
        argument2: explicació argument 3
        ...

    Retorna:
        valor1: explicació del valor retornat 1
        valor2: explicació del valor retornat 1
        ...

    '''
    # Operacions que fa la funció

    return valor1, valor2, ...


resultats = nom_funcio(argument1, argument2, ...)
```

## Exemple suma

Sempre amb docstrings. No cal que siguin súper detallats.

```python
def suma (a, b):
    '''Retorna la suma de a i b'''
    return a+b


# Ha d'imprimir el número 5
resultat = suma(2, 3)
print (f"La suma de 2 + 3 és: {resultat}")
```
