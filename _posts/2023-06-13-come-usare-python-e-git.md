---
title: "Come usare Python e Git"
date: "2023-06-13"
categories: 
  - "toolkit-del-programmatore"
  - "tools"
tags: 
  - "data"
  - "git"
  - "github"
  - "python"
coverImage: "images/copertina-git-python.jpg"
---

Python e Git sono due strumenti ampiamente utilizzati nel campo dello sviluppo software. Vediamo come usare Python e Git insieme al meglio per gestire i nostri progetti con un [Version Control System](https://it.wikipedia.org/wiki/Controllo_versione#Programmi_e_sistemi_utilizzati) (git)

Python è un linguaggio di programmazione ad alto livello, interpretato e orientato agli oggetti. È noto per la sua sintassi semplice e leggibile, il che lo rende una ottima scelta per chi è alle prime armi nella programmazione. Python viene utilizzato per una vasta gamma di compiti, che vanno dallo sviluppo web e scientifico all'automazione di compiti e all'intelligenza artificiale. Dispone di una vasta libreria standard e di una comunità attiva che contribuisce con pacchetti e framework aggiuntivi.

Git, d'altra parte, è un sistema di controllo di versione distribuito. Consente a più persone di lavorare contemporaneamente su un progetto software, mantenendo uno storico di tutte le modifiche effettuate.

Ecco un tutorial introduttivo su Python e Git:

### Inziamo con un introduzione a Python:

1. Installazione: Per iniziare, assicurati di avere Python installato sul tuo computer. Puoi scaricare l'ultima versione stabile di Python dal [sito ufficiale](https://www.python.org/) e poi seguire le istruzioni di installazione.

3. Per iniziare a familiarizzare con le librerie più importanti di python visita il nostro articolo [qui](https://avid3855894.altervista.org/strumenti-per-programmare-al-meglio-in-python/)!

5. Ambiente di sviluppo: Dopo aver installato Python, hai bisogno di un ambiente di sviluppo per scrivere il tuo codice. Puoi utilizzare un semplice editor di testo come Notepad++ o preferire un ambiente di sviluppo integrato (IDE) come PyCharm o Visual Studio Code, che offrono funzionalità avanzate di sviluppo.

7. Scrittura del codice: Apri il tuo editor di testo o l'IDE e crea un nuovo file con estensione ".py". Puoi iniziare scrivendo un semplice "Hello, World!" per verificare se tutto funziona correttamente. Ad esempio:

```
print("Hello, World!")
```

4. Esecuzione del codice: Salva il file con l'estensione ".py" e apri il terminale o la finestra dei comandi. Passa alla directory in cui hai salvato il file Python e esegui il seguente comando:

```
python nome_file.py
```

Dovresti vedere l'output "Hello, World!" nel terminale.

5. Imparare i fondamenti: Python offre molti concetti fondamentali come variabili, tipi di dati, operatori, condizioni, cicli, funzioni e molto altro. Puoi trovare numerosi tutorial online, documentazione ufficiale e risorse didattiche per apprendere i fondamenti di Python.

![la potenza di git non ha limite!](/assets/images/image-6-edited.png)

### Ora passiamo a Git:

1. Installazione: Per utilizzare Git, devi prima installarlo sul tuo sistema. Puoi scaricare l'ultima versione di Git dal sito ufficiale ([https://git-scm.com/](https://git-scm.com/)) e seguire le istruzioni di installazione appropriate per il tuo sistema operativo.

3. Inizializzazione di un repository: Per creare un repository Git, posizionati nella directory del tuo progetto e apri il terminale o la finestra dei comandi. Esegui il seguente comando per inizializzare un nuovo repository:

```
git init
```

Verrà creata una nuova cartella ".git" che conterrà tutte le informazioni di controllo delle versioni.

3. Aggiunta di file al repository: Dopo aver inizializzato il repository, puoi aggiungere i file che desideri tenere traccia delle modifiche. Esegui il seguente comando per aggiungere tutti i file presenti nella directory corrente:

```
git add .
```

Puoi anche specificare i file specifici invece di utilizzare il punto ".", ad esempio:

```
git add file1.py file2.py
```

4. Commit delle modifiche: Una volta aggiunti i file, puoi eseguire il commit delle modifiche per salvare uno snapshot del tuo repository. Esegui il seguente comando:

```
git commit -m "Descrizione del commit"
```

Sostituisci "Descrizione del commit" con una breve descrizione delle modifiche apportate.

### Ora vediamoli insieme, creando un progetto python e caricandolo su una repository Git:

1. Inizializzazione del repository: Posizionati nella directory principale del tuo progetto Python tramite il terminale o la finestra dei comandi. Esegui il comando `git init` per inizializzare un nuovo repository Git nella cartella del progetto. Questo creerà una nuova cartella `.git` che conterrà tutte le informazioni di controllo delle versioni.

3. Aggiunta dei file: Utilizza il comando `git add` per aggiungere i file del tuo progetto al repository. Ad esempio, se desideri aggiungere tutti i file presenti nella directory corrente, esegui `git add .`. Puoi anche specificare i file specifici da aggiungere, ad esempio `git add file1.py file2.py.`

5. Commit delle modifiche: Dopo aver aggiunto i file, esegui il comando `git commit` per salvare le modifiche nello storico del repository. Ad esempio, esegui `git commit -m "Descrizione del commit"` per eseguire un commit con una descrizione delle modifiche apportate.

Adesso facciamo un passo in più, le nostre repository create finora sono disponibi soltanto in locale, vediamo come fare per farle "Hostare" sul cloud per renderle disponibili ad eventuali collaboratori(o anche per averle disponibili su piu dispositivi).

1. Lavoro con un repository remoto: Puoi collegare il tuo repository locale a un repository remoto, ad esempio su [GitHub](http://www.github.com) o GitLab. Questo ti consentirà di collaborare con altre persone e tenere traccia delle modifiche in remoto. Per fare ciò, crea un nuovo repository vuoto sul servizio di hosting scelto e segui le istruzioni fornite per aggiungere un repository remoto. Di solito, dovrai eseguire un comando come `git remote add origin <URL_repo_remoto>` per collegare il tuo repository locale al repository remoto.

3. Push delle modifiche: Dopo aver collegato il repository remoto, puoi eseguire il comando `git push` per caricare le modifiche locali sul repository remoto. Ad esempio, esegui `git push origin master` per inviare le modifiche al ramo "master" del repository remoto.

Questi sono solo i passaggi di base per utilizzare Git con un progetto Python. Ci sono molte altre funzionalità di Git che puoi esplorare, come la creazione di branch, il merge delle modifiche e la gestione dei conflitti. È utile consultare la documentazione di Git o seguire tutorial più approfonditi per sfruttare al massimo le potenzialità di Git nel tuo progetto Python.
