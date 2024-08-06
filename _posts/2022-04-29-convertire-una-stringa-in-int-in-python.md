---
title: "Convertire una stringa in int in python"
date: "2022-04-29"
categories: 
  - "toolkit-del-programmatore"
tags: 
  - "data"
  - "datamanipulation"
  - "python"
  - "strings"
  - "technology"
coverImage: "images/program-code-on-pc-screen-2021-08-28-12-44-05-utc-scaled.jpg"
---

Ti serve convertire una stringa in un intero? Se può esservi utile in un vostro progetto, come l'implementazione da zero di RSA, questo è il posto giusto per saperlo.

![](images/writing-programming-code-on-laptop-2021-08-30-05-42-12-utc-960x302.jpg)

Per convertire una **stringa in int** si possono usare due modi:

## Int.from\_bytes

Questo metodo è integrato nella libreria standard di python ed è quello che consiglio

```
print(int.from_bytes("Ciao".encode(),"big")) #1130979695
```

Si passa il primo argomento come stringa codificata in bytes (usando .encode()), nel secondo argomento si passa invece l'ordine dei bytes (molto semplificato)

La differenza tra i due sistemi è data dall'ordine con cui i byte costituenti il dato da immagazzinare vengono memorizzati o trasmessi:

- big-endian: memorizzazione/trasmissione che inizia dal byte più significativo (estremità più grande) per finire col meno significativo, è utilizzata dai processori [Motorola](https://it.wikipedia.org/wiki/Motorola);
- _little endian_: memorizzazione/trasmissione che inizia dal byte meno significativo (estremità più piccola) per finire col più significativo, è utilizzata dai processori [Intel](https://it.wikipedia.org/wiki/Intel);

(Grazie Wikipedia)per saperne di più [leggete qui](https://it.wikipedia.org/wiki/Ordine_dei_byte)

## bytes\_to\_long

A differenza del metodo sopracitato, questo si deve importare dalla libreria Crypto (scaricando pycryptodome)

Un vantaggio è che converte automaticamente la stringa in bytes

```
from Crypto.Util.number import bytes_to_long 
print(bytes_to_long("string")) #126943972912743
```

##### A presto!
