---
title: Llistes i diccionaris
layout: default
nav_order: 6
parent: Receptes
author: Luis Rey
---

# Llistes i diccionaris

## Llistes

Creació:

```python
nombres = ['zero', 2.0, 1, '3', 4]
# Resultat ['zero', 2.0, 1, '3', 4]

list(range(4))
# Resultat [0, 1, 2, 3]

list('Python') 
# Resultat ['P', 'y', 't', 'h', 'o', 'n']

llista_buida = []
```

Accés a un element:

```python
nombres = ['zero', 2.0, 1, '3', 4]
print(nombres[1])
# Resultat 2.0
```

Iteració:

```python
x = [-3, 8.5, 5, 3.5]
suma = 0
for valor in x:
    suma = suma + valor
print(suma)
## Resultat: 14.0
```

Calcula el nombre d'elements de la llista:

```python
x = [-3, 8.5, 5, 3.5]
n = len(x)
print(n)
# Resultat 4
```

Sumar:

```python
x = [-3, 8.5, 5, 3.5]
suma = sum(x)
print(suma)
# Resultat 14.0
```

Ordenar:

```python
x = [-3, 8.5, 5, 3.5]
y = sorted(x)
print(y)
# El resultat és: [-3, 3.5, 5, 8.5]
```

Alternativament, compte que l'ordre *sort* modifica la llista i no es pot recuperar l'ordre inicial:

```python
x = [-3, 8.5, 5, 3.5]
x.sort()
print(x)
# El resultat és: [-3, 3.5, 5, 8.5]
```

Dividir cadenes per aconseguir una llista:

```python
entrada1 = "Matemàtiques Castellà Català Informàtica"
materies = entrada1.split() 
print(materies)
# Resultat ['Matemàtiques', 'Castellà', 'Català', 'Informàtica']
```

De cadena de text a nombres:

```python
entrada2 = "2, 4, -3, 4.3, 9.1"
valors_text = entrada2.split(',')
valors_num = list(map(float, valors_text))
print(valors_num)
# Resultat [2, 4, -3, 4.3, 9.1]
```

## Diccionaris

Definició

```python
notes = {'mates': 6.4,
         'catala': 5.1,
         'informatica': 10.0
         }
```

Iteració

```python
suma = 0
for clau in notes:
    suma = suma + notes[clau]
print(suma)
# 21.5
```

Ordenar

```python
notes_ordenades = dict(sorted(notes.items()))
print(notes_ordenades)
# {'catala': 5.1, 'informatica': 10.0, 'mates': 6.4}
notes_ordenades = dict(sorted(notes.items(),
                              key=lambda x: x[1])
                              )
print(notes_ordenades)
#{'catala': 5.1, 'mates': 6.4, 'informatica': 10.0}
```

Diccionari buit i afegir element

```python
diccionari = {}
diccionari['Nom'] = 'Pere'
diccionari['Cognoms'] = 'García Ramon'
diccionari['Càrrec'] = 'Coordinadora'
print(diccionari)
# {'Nom': 'Pere', 'Cognoms': 'García Ramon', 'Càrrec': 'Coordinadora'}
```
