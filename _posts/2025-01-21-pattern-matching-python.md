---
title: "Pattern Matching in Python: match/case Meglio di if/elif"
date: "2025-01-21"
categories: 
  - "toolkit-del-programmatore"
tags: 
  - "syntax"
  - "programming"
  - "python"
  - "match"
  - "pattern-matching"
coverImage: "/assets/images/program-code-on-pc-screen-2021-08-28-12-44-05-utc-scaled.jpg"
---

## Quando usarlo

Python 3.10+ introduce `match/case` per sostituire lunghe catene di `if/elif`. È perfetto per parsing di dati strutturati, state machines, o quando devi confrontare valori complessi. Rende il codice più leggibile e meno soggetto a errori rispetto ai classici if annidati.

## Snippet

```python
def elabora_risposta(response):
    match response:
        case {"status": "success", "data": data}:
            return f"Successo: {data}"
        case {"status": "error", "code": 404}:
            return "Risorsa non trovata"
        case {"status": "error", "code": code} if code >= 500:
            return f"Errore server: {code}"
        case {"status": status}:
            return f"Status sconosciuto: {status}"
        case _:  # default
            return "Formato non riconosciuto"

# Esempi d'uso
print(elabora_risposta({"status": "success", "data": "OK"}))
```

## Perché funziona

`match/case` fa pattern matching strutturale, non solo confronti di valori. Può estrarre parti di oggetti complessi, applicare condizioni con guard (`if`), e gestire tipi diversi in modo elegante. È più espressivo di `if/elif` e spesso più performante grazie alle ottimizzazioni del compiler.

## Attenzione a...

- Disponibile solo da Python 3.10+ - controlla la versione prima di usarlo
- I pattern sono valutati in ordine - il primo match vince
- Usa sempre `case _:` come fallback per evitare eccezioni non gestite

## Vedi anche

- `isinstance()` per controlli di tipo tradizionali  
- `typing.Union` per type hints con alternative
- [PEP 634 - Pattern Matching](https://peps.python.org/pep-0634/)