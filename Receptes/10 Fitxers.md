---
title: Fitxers
layout: default
nav_order: 10
parent: Receptes
author: Luis Rey
date: 2024/5/25
toc: false
---

# Fitxers

Només treballarem amb fitxers de texts seqüencials.

Llegir fitxer i utilitzar les dades directament

***No recomanat!***

```python
suma = 0
nom_fitxer_entrada = "notes.txt"
with open(nom_fitxer_entrada, 'r') as fitxer_entrada:
    for linia in fitxer_entrada:
        suma = suma + int(linia)
```

Llegir i guardar en una llista

```python
notes = []
nom_fitxer_entrada = "notes.txt"
with open(nom_fitxer_entrada, 'r') as fitxer_entrada:
    for linia in fitxer_entrada:
        notes.append(int(linia))
print(notes)
#[4, 5, 7, 4, 10]
```

Escriptura simple

```python
nom_fitxer_sortida = "idees.txt"
with open(nom_fitxer_sortida, 'w') as fitxer_sortida:
    fitxer_sortida.write("Hola, món!\n")
    # "\n", salt de línia
    fitxer_sortida.write(mitjana)
    fitxer_sortida.write("\n")
    fitxer_sortida.write(f"Mitjana: {mitjana:.2g}\n")
```

Escriptura d’una llista

```python
notes = [4, 5, 7, 4, 10]

nom_fitxer_sortida = "notes.txt"
with open(nom_fitxer_sortida, 'w') as fitxer_sortida:
    for nota in notes:
        fitxer_sortida.write(nota)
```

## Estructura de fitxers

En el terminal sempre ens hem de fixar en el que ens indica el símbol del sistema o *prompt*.

En Windows sempre porta la ruta sencera acabada amb el símbol ">" i la separació entre directoris és una contrabarra "\\":

```txt
C:\Users\professor\Institut\Programació BATX>
```

En Unix/Linux/Mac podem veure la ruta sencera sense cap símbol afegit:

```txt
/home/professor/Institut/Programació BATX
```

O la ruta respecte al directori de l'usuari:

```txt
~/Institut/Programació BATX
```

Si la carpeta té la següent estructura:

```txt
/
|
├── tests/
|   ├── test_arrel.py
|   └── test_pi.py
|
├── arrel.py
├── calcul_pi.py
└── main.py
```

En Python per referir-se al directori actual s'utilitza "./". Per tant, a un fitxer que està en la mateixa carpeta on s'executa el programa ens podem referir de dues formes:

```python
fitxer_1 = "arrel.py"
fitxer_1 = "./arrel.py"
```

A un fitxer que està en un subdirectori sempre hem d'indicar el directori:

```python
fitxer_2 = "./test/arrel.py"
```
