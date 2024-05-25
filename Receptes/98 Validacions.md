---
title: Validacions
layout: default
nav_order: 98
parent: Receptes
author: Luis Rey
date: 2024/5/25
toc: false
---

# Validacions

Especialment a l'entrada de dades.

## Elements a considerar

### Com validar

1. Fer validacions pròpies
2. Gestionar excepcions

Moltes vegades és convenient utilitzar les dues.

### Com corregir

1. Demanar una nova entrada
2. Assignar un valor per defecte. Perillós.

### Com avisar de l'error

1. No avisar
2. Missatge
3. Aixecar excepció

### Flux del programa

1. Ha d'aturar-se en l'error
2. Ha de continuar

## Estratègies a seguir

### No validar

Suposem que l'entrada és correcta. Ja saltarà si hi ha algun programa...

Fàcil i perillós. Només per als nostres programes. En anglès *quick and dirty*.

### Validar i corregir

Es fan les comprovacions oportunes i després s'actua per corregir l'error dintre del mateix programa/funció.

Interessant si nosaltres control·lem tot el programa. En la major part de programes de Python no paga la pena.

### Validar i actuar

Es fan les comprovacions, s'avisa i s'atura el programa.

Molt interessant. També per als nostres programes. Tampoc sense dedicar molts recursos.

### Validar i avisar

L'avís pot ser en forma de missatge (perillós) o s'aixeca una excepció.

És la forma de treballar en projecte complexos. Ens assegurem que cada part del programa funciona correctament i si ha algun error s'avisa per a que altres parts gestionin l'error.
