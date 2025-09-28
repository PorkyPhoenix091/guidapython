---
title: "zip() e zip_longest(): Unire Liste in Python come un Pro"
date: "2025-01-15"
categories: 
  - "toolkit-del-programmatore"
tags: 
  - "data"
  - "programming"
  - "python"
  - "itertools"
  - "lists"
coverImage: "/assets/images/program-code-on-pc-screen-2021-08-28-12-44-05-utc-scaled.jpg"
---

## Quando usarlo

Hai mai dovuto combinare due o più liste elemento per elemento? La funzione `zip()` è perfetta quando devi processare liste parallele, come nomi e cognomi, coordinate x-y, o dati correlati. Usa `zip_longest()` quando le liste hanno lunghezze diverse e non vuoi perdere informazioni.

## Snippet

```python
from itertools import zip_longest

# zip() - si ferma alla lista più corta
nomi = ['Marco', 'Anna', 'Luigi']
età = [25, 30, 28, 35]
for nome, eta in zip(nomi, età):
    print(f"{nome}: {eta} anni")

# zip_longest() - include tutti gli elementi
for nome, eta in zip_longest(nomi, età, fillvalue="N/A"):
    print(f"{nome}: {eta} anni")
```

## Perché funziona

`zip()` crea un iteratore che combina elementi dalle sequenze finché la più corta non si esaurisce. È efficiente in memoria perché genera coppie una alla volta invece di creare una lista completa. `zip_longest()` va oltre, riempiendo i valori mancanti con un valore predefinito, garantendo che nessun dato venga perso nel processo.

## Attenzione a...

- `zip()` si ferma alla lista più corta - potresti perdere dati senza accorgertene
- Non usare `list(zip())` con dataset enormi - consuma molta memoria
- Ricorda di importare `zip_longest` da `itertools`

## Vedi anche

- `itertools.chain()` per concatenare sequenze
- `enumerate()` per aggiungere indici
- [Documentazione ufficiale itertools](https://docs.python.org/3/library/itertools.html)