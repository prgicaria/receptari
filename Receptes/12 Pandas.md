---
title: Pandas
layout: default
nav_order: 10
parent: Receptes
author: Luis Rey
date: 2024/5/25
toc: true
---

# Pandas
{: .no_toc }

1. Índex
{:toc}

## Importació

```python
import pandas as pd
```

## Treball amb fitxers

Llegir un fitxer CSV i guardar el resultat en un *DataFrame*

```python
notes = pd.read_csv("nom_fitxer.csv")
```

Gravar un *DataFrame* en un fitxer Excel.

```python
notes.to_excel("Notes.xls")
```

## Descripció del *DataFrame*

```python
notes.describe()
```

||ID| Nota
|--|--|--
|count|1000.000000|1000.000000
|mean|104.004000| 6.621000
|std|59.103851| 2.167962
|min| 6.000000| 0.000000
|25%|48.000000| 5.000000
|50%| 104.000000| 7.000000
|75%| 157.000000| 8.000000
|max| 198.000000|10.000000

## Selecció de columnes

```python
sense_ID = notes[["Materia", "Nota"]]
print(sense_ID)
```

| |Materia|Nota
|--|--|---
|0|LC|6
|1|LS|5
|2|IA1|6
|..|...|...
|999|WPROG1|10

## Filtrat de dades

```python
notes_altes = notes[notes['Nota'] > 8]
print(notes_altes)
```

| |ID|Materia|Nota
|--|--|--|--
|9|122| RCA|10
|24| 176| IA1|10
|26| 176|FI| 9
|28| 176| ECO| 9
|29| 176| HMO|10
|..| ...| ...| ...
|999| 26|WPROG1|10

## Estadística d'una sèrie

### Paràmetres estadístics

```python
mitjana = notes["Nota"].mean()
print(f"Mitjana global: {mitjana:.2f}")

# Mitjana global: 6.62
```

Té moltes funcions estadístiques incorporades:

- mean(): mitjana aritmètica
- median(): mediana
- mode(): moda
- std(): desviació estàndard
- var(): variància
- ...

### Recompte de freqüències

```python
freq = notes["Nota"].value_counts()
freq = notes["Nota"].value_counts(normalize=True).sort_index()
```

|Nota|-
|-- |--
|0|0.005
|1|0.023
|2|0.022
|3|0.054
|4|0.059
|5|0.119
|6|0.138
|7|0.140
|8|0.241
|9|0.165
|10|0.034

Accés a l'index

Normalment, l'índex no és important... però en alguns casos com podrien ser els grups sí que porta una part molt important de la formació.

```python
freq = notes["Nota"].value_counts()
valors_notes = notes.index
# [8, 9, 7, 6, 5, 4, 3, 10, 1, 2, 0]
```

## Afegir columnes amb càlculs

```python
notes["Nota normalitzada"] = notes["Nota"]/mitjana
print(notes)
```

| |ID|Materia|Nota|Nota normalitzada
|--|--|--|--|--
|0|122| LC| 6| 0.906208
|1|122| LS| 5| 0.755173
|2|122|IA1| 6| 0.906208
|3|122| EF| 6| 0.906208
|4|122| FI| 6| 0.906208
|..| ...|...| ...|...
|999| 26|WPROG1|10| 1.510346

## Agrupacions

```python
desv_std_materia = notes[["Materia", "Nota"]].groupby('Materia').std()
```

|| Nota
|--|--
|Materia|-
|BI1| 1.629063
|CG1| 1.366260
|DT1| 3.464102
|ECO| 0.681460
|EF| 1.339126
|FI| 2.019668
|FI1| 1.824084
|HMO| 2.112235
|IA1| 2.154868
|LC| 1.585042
|LIU| NaN
|LS| 2.180827
|MA1| 2.689277

En l'exemple s'ha calculat la desviació estándard, però pot fer-se servir qualsevol funció. *max(), mean(), count(), etc.*

Per  convertir un índex d'una agrupació en columna:

```python
# Agrupacions
desv_std_materia = notes[["Materia", "Nota"]].groupby('Materia').std()
desv_std_materia = desv_std_materia.reset_index()
```

||Materia| Nota
|---|----|--
|0|BI1| 1.629063
|1|CG1| 1.366260
|2|DT1| 3.464102
|3|ECO| 0.681460
|4|EF| 1.339126
|5|FI| 2.019668
|6|FI1| 1.824084
|7|HMO| 2.112235
|8|IA1| 2.154868
|9|LC| 1.585042
|10|LIU| NaN
|11|LS| 2.180827
|12|MA1| 2.689277

## Treball amb gràfics

Millor treballar amb *matplotlib* que amb els mètodes propis.

```python
# Creació del gràfic
figura, eixos = plt.subplots()

# Diagrama de barres de la materia
freq = notes["Nota"=="IA1"].value_counts()
nota = freq_materia.index
eixos.bar(nota, freq_materia, color='gold')
```
