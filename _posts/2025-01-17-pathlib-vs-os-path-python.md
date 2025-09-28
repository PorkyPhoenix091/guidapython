---
title: "pathlib vs os.path: La Rivoluzione dei Path in Python"
date: "2025-01-17"
categories: 
  - "toolkit-del-programmatore"
tags: 
  - "files"
  - "programming"
  - "python"
  - "pathlib"
  - "filesystem"
coverImage: "/assets/images/program-code-on-pc-screen-2021-08-28-12-44-05-utc-scaled.jpg"
---

## Quando usarlo

Stanco di `os.path.join()` e concatenazioni di stringhe per gestire file e cartelle? `pathlib` rende il lavoro con i percorsi molto più intuitivo e sicuro. Usalo per manipolare path, controllare esistenza file, navigare directory o qualsiasi operazione sui filesystem.

## Snippet

```python
from pathlib import Path

# Creazione di path cross-platform
progetto = Path("progetti") / "python" / "app.py"
print(progetto)  # progetti/python/app.py (o progetti\python\app.py su Windows)

# Operazioni comuni
config_file = Path("config.json")
if config_file.exists():
    contenuto = config_file.read_text()

# Navigazione intelligente
script_dir = Path(__file__).parent
data_file = script_dir / "data" / "input.csv"
```

## Perché funziona

`pathlib.Path` è un oggetto che rappresenta percorsi filesystem in modo orientato agli oggetti. L'operatore `/` sostituisce `os.path.join()`, i metodi come `.exists()`, `.read_text()`, `.mkdir()` sono integrati direttamente nell'oggetto. Funziona identicamente su Windows, Linux e macOS senza modifiche al codice.

## Attenzione a...

- Alcune librerie vecchie accettano solo stringhe - usa `str(path)` per convertire
- Non mescolare `Path` e stringhe negli stessi calcoli senza conversioni
- `.resolve()` può essere lento su filesystem di rete

## Vedi anche

- `os.path` per compatibilità con codice legacy
- `glob` pattern con `Path.glob()`
- [Documentazione pathlib](https://docs.python.org/3/library/pathlib.html)