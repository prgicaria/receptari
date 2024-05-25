---
title: Excepcions
layout: default
nav_order: 99
parent: Receptes
author: Luis Rey
date: 2024/5/25
toc: false
---

# Excepcions

## Captura i tractament

```python
try:
    # Operació que volem controlar
except:
    # Que hem de fer si hi ha un error
else:
    # Que fer si no hi ha error
finally:
    # Que hem de fer sempre
```

Les parts de *else:* i *finally:* són opcional i moltes vegades no es fan servir.

## Errors de conversió entre tipus de dades

```python
try:
    valor = int(input("Entra un nombre enter: "))
except ValueError:
    print("Valor incorrecte")
```

## Error de divisió entre zero

```python
try:
    quocient = dividend/divisor
except ZeroDivisionError:
    print("No es por dividir entre 0")
```

## Errors a l'obrir un fitxer

```python
try:
  fitxer = open("quixot.txt")
except FileNotFoundError:
  print(f"No s'ha trobat el fitxer")
else:
  text = fitxer.read()
  print(text)
finally:
  fitxer.close()
```

## Més informació

- Exemples en: <https://www.freecodecamp.org/espanol/news/sentencias-try-y-except-de-python-como-menejar-excepciones-en-python/>
- Llistat d'excepcions: <https://docs.python.org/es/3/library/exceptions.html#exception-hierarchy>
