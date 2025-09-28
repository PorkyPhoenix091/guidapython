---
title: "Come usare enumerate() in Python: Guida Pratica con Esempi"
date: "2025-09-28"
categories: 
  - "toolkit-del-programmatore"
tags: 
  - "data"
  - "programming"
  - "python"
  - "loops"
  - "iteration"
coverImage: "/assets/images/program-code-on-pc-screen-2021-08-28-12-44-05-utc-scaled.jpg"
---

La funzione `enumerate()` è uno degli strumenti più utili di Python per chi lavora con le iterazioni. Questa funzione built-in permette di iterare attraverso una sequenza ottenendo contemporaneamente sia l'indice che il valore di ogni elemento.

## Sintassi Base

```python
enumerate(iterable, start=0)
```

Il parametro `start` è opzionale e definisce da quale numero iniziare il conteggio degli indici.

## Esempi Pratici

### Esempio 1: Lista Semplice

```python
frutti = ['mela', 'banana', 'arancia']

for indice, frutto in enumerate(frutti):
    print(f"{indice}: {frutto}")

# Output:
# 0: mela
# 1: banana
# 2: arancia
```

### Esempio 2: Iniziare da un Numero Diverso

```python
studenti = ['Marco', 'Laura', 'Giovanni']

for numero, nome in enumerate(studenti, start=1):
    print(f"Studente {numero}: {nome}")

# Output:
# Studente 1: Marco
# Studente 2: Laura
# Studente 3: Giovanni
```

### Esempio 3: Trovare l'Indice di un Elemento

```python
colori = ['rosso', 'verde', 'blu', 'giallo']

for i, colore in enumerate(colori):
    if colore == 'blu':
        print(f"Il colore blu si trova all'indice {i}")
        break
```

## Perché Usare enumerate()?

Invece di usare `range(len())`:

```python
# Modo meno elegante
lista = ['a', 'b', 'c']
for i in range(len(lista)):
    print(i, lista[i])

# Modo migliore con enumerate
for i, elemento in enumerate(lista):
    print(i, elemento)
```

La funzione `enumerate()` rende il codice più leggibile e pythonic, eliminando la necessità di gestire manualmente gli indici. È particolarmente utile quando si deve processare dati mantenendo traccia della posizione di ogni elemento nella sequenza originale.

Utilizzala ogni volta che hai bisogno sia dell'indice che del valore durante l'iterazione!