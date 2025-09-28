---
title: "JSON Sicuro in Python: load() e dump() Senza Sorprese"
date: "2025-01-18"
categories: 
  - "toolkit-del-programmatore"
tags: 
  - "data"
  - "programming"
  - "python"
  - "json"
  - "files"
coverImage: "/assets/images/program-code-on-pc-screen-2021-08-28-12-44-05-utc-scaled.jpg"
---

## Quando usarlo

Ogni volta che devi salvare configurazioni, scambiare dati con API, o persistere strutture dati semplici. JSON è il formato standard per lo scambio dati, e gestirlo correttamente evita errori frustranti e perdite di dati durante il salvataggio e caricamento.

## Snippet

```python
import json
from pathlib import Path

# Scrittura sicura
dati = {"nome": "Marco", "età": 30, "skills": ["Python", "SQL"]}
file_config = Path("config.json")

with open(file_config, 'w', encoding='utf-8') as f:
    json.dump(dati, f, ensure_ascii=False, indent=2)

# Lettura con gestione errori
try:
    with open(file_config, 'r', encoding='utf-8') as f:
        config = json.load(f)
except (FileNotFoundError, json.JSONDecodeError) as e:
    config = {}  # valore predefinito
```

## Perché funziona

`json.dump()` e `json.load()` lavorano direttamente con file, evitando di caricare tutto in memoria. L'encoding UTF-8 gestisce caratteri speciali, `ensure_ascii=False` preserva i caratteri non-ASCII, e `indent=2` rende il file leggibile. La gestione delle eccezioni previene crash del programma.

## Attenzione a...

- Sempre specificare `encoding='utf-8'` per evitare problemi con caratteri speciali
- JSON non supporta commenti, date native, o tuple (diventano liste)
- Non usare `json.loads(json.dumps())` per copiare oggetti - usa `copy.deepcopy()`

## Vedi anche

- `pickle` per oggetti Python complessi
- `configparser` per file di configurazione
- [Documentazione JSON](https://docs.python.org/3/library/json.html)