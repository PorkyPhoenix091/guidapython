---
title: "functools.lru_cache: Accelera Python con una Riga di Codice"
date: "2025-01-23"
categories: 
  - "toolkit-del-programmatore"
tags: 
  - "performance"
  - "programming"
  - "python"
  - "optimization"
  - "functools"
coverImage: "/assets/images/program-code-on-pc-screen-2021-08-28-12-44-05-utc-scaled.jpg"
---

## Quando usarlo

Hai funzioni che fanno calcoli costosi con gli stessi parametri ripetutamente? `lru_cache` memorizza automaticamente i risultati, trasformando chiamate lente in lookup istantanei. Perfetto per ricorsioni, chiamate API, calcoli matematici complessi, o qualsiasi funzione "pura" che restituisce sempre lo stesso output per lo stesso input.

## Snippet

```python
from functools import lru_cache
import time

@lru_cache(maxsize=128)
def fibonacci(n):
    if n < 2:
        return n
    return fibonacci(n-1) + fibonacci(n-2)

@lru_cache(maxsize=None)  # cache illimitata
def calcolo_lento(x, y):
    time.sleep(1)  # simula calcolo pesante
    return x * y + x ** 2

# Prima chiamata: lenta
start = time.time()
result = calcolo_lento(5, 10)
print(f"Prima: {time.time() - start:.2f}s")

# Seconda chiamata: istantanea!
start = time.time()  
result = calcolo_lento(5, 10)
print(f"Seconda: {time.time() - start:.4f}s")
```

## Perché funziona

`lru_cache` implementa una Least Recently Used cache che memorizza risultati di funzioni usando parametri come chiave. Quando la funzione viene chiamata, controlla prima se il risultato è già in cache. Se sì, lo restituisce immediatamente; altrimenti calcola, memorizza e restituisce il risultato.

## Attenzione a...

- Funziona solo con parametri "hashable" (no liste, dizionari come argomenti)
- Può consumare molta memoria se `maxsize=None` con molti input diversi
- Non usare con funzioni che hanno side effects o dipendono da stato esterno

## Vedi anche

- `functools.cache` (Python 3.9+) per cache illimitata semplificata
- `functools.singledispatch` per overloading di funzioni
- [Documentazione functools](https://docs.python.org/3/library/functools.html)