---
title: Proves pytest
layout: default
nav_order: 13
parent: Receptes
author: Luis Rey
date: 2024/8/9
---

# Proves pytest

## Noms de fitxers i estructura

Sempre han de començar amb el nom *"test_"*. Per exemple: *test_dni.py*.

Han d'estar en la mateixa carpeta que el programa (opció més senzilla).

```txt
dni.py
test_dni.py
```

O en una carpeta diferent acompanyats del fitxer  *\_\_init__.py* que està en blanc. Aquest fitxer només indica el punt de partida dels tests.

```txt
18_dni_rey/
├── test/
│   ├── __init__.py
│   └── test_dni.py
├── dni.py
├── dni_flux.pdf
└── dni_proves.pdf
```

## Importació de les funcions

Importa totes les funcions, quan voldrem utilitzar les funcions haurem de fer servir el prefix *dni.*, també és convenient importar la mateixa biblioteca *pytest* per utilitzar funcions específiques.

```python
import dni
import pytest
```

Importa totes les funcions i asigna un nom, quan voldrem utilitzar les funcions haurem de fer servir el nom indicat, *emb.*:

```python
import embassaments as emb
import pytest
```

## Funcions de prova

És convenient definir una funció de prova per cadascuna de les proves que consten en el nostre document de proves.

- Ha de començar amb la paraula *test_*.
- Ha de contenir una asserció que serà una comprovació lògica.

```py
def test_lletra_dni():
    # 12345678Z
    assert dni.lletra_dni(12345678) == "Z"
```

## Assercions

Igualtat:

```py
def test_lletra_dni():
    # 12345678Z
    assert dni.lletra_dni(12345678) == "Z"
```

Veritat o Fals, noteu que es poden fer servir negacions:

```py
def test_dni_valid_minuscula():
    assert dni.es_dni_valid("12345678z")

def test_dni_valid_incorrecte():
    assert not dni.es_dni_valid("12345678A")
```

Valors aproximats, molt importants quan tractem amb nombres de coma flotant.

```py
def test_double_floating_point():
    assert (0.1 + 0.2) - 0.3  == pytest.approx(0)
```

Comparació entre matrius

```py
import numpy as np

assert (np.array([1, 2]) + np.array([1, 4]) == np.array([3, 6])).all()
```
