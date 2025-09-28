---
title: "Liste come Argomenti Default: L'Errore che Tutti Commettono"
date: "2025-01-22"
categories: 
  - "toolkit-del-programmatore"
tags: 
  - "functions"
  - "programming"
  - "python"
  - "debugging"
  - "gotchas"
coverImage: "/assets/images/program-code-on-pc-screen-2021-08-28-12-44-05-utc-scaled.jpg"
---

## Quando usarlo

Questo non è "quando usarlo", ma "quando NON usarlo"! Mai usare liste (o altri oggetti mutabili) come valori predefiniti nei parametri di funzione. È uno dei bug più comuni in Python che causa comportamenti inaspettati e difficili da debuggare, specialmente in codice condiviso tra più chiamate.

## Snippet

```python
# SBAGLIATO - non fare mai così!
def aggiungi_item(item, lista=[]):
    lista.append(item)
    return lista

# CORRETTO - usa None e crea una nuova lista
def aggiungi_item_corretto(item, lista=None):
    if lista is None:
        lista = []
    lista.append(item)
    return lista

# Test del problema
print(aggiungi_item("a"))  # ['a']
print(aggiungi_item("b"))  # ['a', 'b'] - Ops!

print(aggiungi_item_corretto("x"))  # ['x']
print(aggiungi_item_corretto("y"))  # ['y'] - Corretto!
```

## Perché funziona (male)

Gli argomenti predefiniti vengono valutati UNA sola volta quando la funzione viene definita, non ad ogni chiamata. Quindi la stessa lista viene riutilizzata tra chiamate successive, accumulando elementi. Con `None` e controllo `if`, creiamo una nuova lista fresca ad ogni chiamata che non specifica il parametro.

## Attenzione a...

- Vale per TUTTI gli oggetti mutabili: liste, dizionari, set, oggetti custom
- Il problema è invisibile nei test se non chiami la funzione più volte
- Anche le comprehension nel default hanno lo stesso problema

## Vedi anche

- `functools.partial()` per fissare parametri di funzioni
- `copy.deepcopy()` per clonare oggetti complessi
- [Python Common Gotchas](https://docs.python-guide.org/writing/gotchas/)