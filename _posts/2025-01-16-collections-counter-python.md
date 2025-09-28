---
title: "collections.Counter: Conta Tutto in Python Senza Stress"
date: "2025-01-16"
categories: 
  - "toolkit-del-programmatore"
tags: 
  - "data"
  - "programming"
  - "python"
  - "collections"
  - "analysis"
coverImage: "/assets/images/program-code-on-pc-screen-2021-08-28-12-44-05-utc-scaled.jpg"
---

## Quando usarlo

Devi contare elementi in una lista, analizzare frequenze di parole in un testo, o trovare gli elementi più comuni? `Counter` è il tuo miglior amico. È perfetto per analisi statistiche, elaborazione di dati e ogni situazione dove serve sapere "quante volte appare X".

## Snippet

```python
from collections import Counter

# Contare elementi in una lista
voti = ['A', 'B', 'A', 'C', 'A', 'B', 'A']
conteggio = Counter(voti)
print(conteggio)  # Counter({'A': 4, 'B': 2, 'C': 1})

# I 2 elementi più comuni
print(conteggio.most_common(2))  # [('A', 4), ('B', 2)]

# Contare caratteri in una stringa
testo = "python"
Counter(testo)  # Counter({'p': 1, 'y': 1, 't': 1, 'h': 1, 'o': 1, 'n': 1})
```

## Perché funziona

`Counter` è una sottoclasse di `dict` specializzata per conteggi. Gestisce automaticamente valori mancanti (li inizializza a 0), supporta operazioni matematiche tra contatori, e offre metodi utili come `most_common()`. È molto più veloce e leggibile rispetto a loop manuali con dizionari normali.

## Attenzione a...

- Non confondere `Counter()` vuoto con `Counter({})` - sono diversi
- I valori possono essere negativi, ma `most_common()` li ordina comunque
- `Counter` non preserva l'ordine di inserimento come i dict normali (prima di Python 3.7)

## Vedi anche

- `collections.defaultdict` per dizionari con valori predefiniti
- `statistics` module per calcoli statistici avanzati
- [Documentazione Counter](https://docs.python.org/3/library/collections.html#collections.Counter)