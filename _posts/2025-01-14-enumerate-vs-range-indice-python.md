---
title: "enumerate() vs range(len()): Il Modo Giusto di Iterare con Indici"
date: "2025-01-14"
categories: 
  - "toolkit-del-programmatore"
tags: 
  - "loops"
  - "programming"
  - "python"
  - "iteration"
  - "best-practices"
coverImage: "/assets/images/program-code-on-pc-screen-2021-08-28-12-44-05-utc-scaled.jpg"
---

## Quando usarlo

Ogni volta che devi iterare su una lista e ti serve anche l'indice dell'elemento corrente. Invece di usare il vecchio `range(len())`, `enumerate()` è più leggibile, più sicuro, e più "pythonic". Perfetto per modificare liste, tracciare posizioni, o creare output numerati.

## Snippet

```python
frutti = ['mela', 'banana', 'arancia', 'kiwi']

# Modo antiquato (da evitare)
for i in range(len(frutti)):
    print(f"{i+1}. {frutti[i]}")

# Modo moderno e corretto
for i, frutto in enumerate(frutti, start=1):
    print(f"{i}. {frutto}")

# Modificare elementi usando l'indice
numeri = [1, 2, 3, 4, 5]
for i, num in enumerate(numeri):
    numeri[i] = num * 2  # raddoppia ogni elemento
```

## Perché funziona

`enumerate()` restituisce coppie (indice, valore) senza rischi di errori off-by-one o IndexError. È più efficiente perché non calcola la lunghezza né accede agli elementi per indice. Il parametro `start` permette di iniziare da qualsiasi numero, e il codice risulta più leggibile e manutenibile.

## Attenzione a...

- Non usare `list(enumerate())` se non necessario - consuma memoria extra
- `range(len())` può causare IndexError se la lista cambia durante l'iterazione
- Ricorda che `enumerate()` restituisce un iterator - riutilizzalo o ricrealo

## Vedi anche

- `zip()` per iterare su multiple sequenze
- `itertools.count()` per contatori personalizzati  
- [Documentazione enumerate](https://docs.python.org/3/library/functions.html#enumerate)