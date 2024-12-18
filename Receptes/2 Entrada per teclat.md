---
title: Entrada per teclat
layout: default
nav_order: 2
parent: Receptes
---

# Entrada per teclat

## Entrada bàsica

Entrada de text:

```python
text = input("Missatge que es mostra en pantalla")
```

## Entrada i conversió

Entrada de nombres enters. Primer es fa l'entrada en forma de text i després es converteix a enter:

```python  
valor = int(input("Missatge que es mostra en pantalla"))
```

Entrada de nombres amb decimals:

```python
valor = float(input("Missatge que es mostra en pantalla"))
```

## Entrada d'una llista i conversió a nombres

Entrada d'una llista de nombres amb decimals separats per comes:

```python
entrada = input("Introduïu una mostra de nombres, separats per comes: ")
valors_text = entrada.split(",")
valors_num = list(map(float, valors_text))
```

## Entrades repetides

Es demana l'entrada d'un nombre i envia el nombre entrat a la funció *afegir*. El llaç s'acaba quan s'entra un punt.

```python
num = ""
while num != ".":
    num = input("Entra un valor, utilitza un . per acabar: ")
    # Afegir codi a repetir
```

## *NOTA Important!*

Cal fer notar que no es fa cap mena de comprovació respecte als valors entrats. Per tant, les funcions anteriors poden tenir errors en temps d'execució si l'entrada no és un nombre.
