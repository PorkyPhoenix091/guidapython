---
title: "dataclass vs namedtuple: Quando Usare Cosa in Python"
date: "2025-01-20"
categories: 
  - "toolkit-del-programmatore"
tags: 
  - "oop"
  - "programming"
  - "python"
  - "dataclass"
  - "namedtuple"
coverImage: "/assets/images/program-code-on-pc-screen-2021-08-28-12-44-05-utc-scaled.jpg"
---

## Quando usarlo

Serve una struttura dati semplice per raggruppare informazioni correlate? `namedtuple` è perfetto per dati immutabili e leggeri come coordinate o record di database. `dataclass` è ideale quando serve mutabilità, metodi personalizzati, o type hints avanzati per dati più complessi.

## Snippet

```python
from collections import namedtuple
from dataclasses import dataclass

# namedtuple - immutabile e veloce
Point = namedtuple('Point', ['x', 'y'])
p1 = Point(10, 20)
print(p1.x, p1.y)  # 10 20

# dataclass - mutabile e flessibile
@dataclass
class Person:
    nome: str
    età: int
    email: str = "non specificata"
    
    def is_adult(self) -> bool:
        return self.età >= 18

marco = Person("Marco", 25)
marco.età = 26  # mutabile!
```

## Perché funziona

`namedtuple` crea una sottoclasse di tuple con nomi per gli attributi, garantendo immutabilità e prestazioni ottimali. `dataclass` genera automaticamente `__init__`, `__repr__`, `__eq__` e altri metodi magici, riducendo il boilerplate. Supporta type hints nativamente e permette metodi personalizzati mantenendo la semplicità.

## Attenzione a...

- `namedtuple` è immutabile - usa `._replace()` per "modificare" valori
- `dataclass` di default è mutabile - aggiungi `frozen=True` per immutabilità
- `namedtuple` occupa meno memoria, `dataclass` è più flessibile

## Vedi anche

- `typing.NamedTuple` per namedtuple con type hints
- `attrs` library per funzionalità avanzate
- [Documentazione dataclasses](https://docs.python.org/3/library/dataclasses.html)