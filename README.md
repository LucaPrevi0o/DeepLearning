# Uso di GitHub - Estensione Visual Studio Code
Guida introduttiva al funzionamento di GitHub e all'utilizzo delle funzioni di gestione delle versioni all'interno di Visual Studio Code
> Author: Luca Previati (@[LucaPrevi0o](https://github.com/LucaPrevi0o))
>> [!NOTE] Per informazioni aggiuntive su come integrare le funzionalità di GitHub nell'ambiente di lavoro di VS-Code, seguire il [resto della guida](#integrazione-con-visual-studio-code).

<hr/>

## Funzionamento di GitHub
GitHub è un sistema di *versioni* del codice, che permette di aggiornare i file progressivamente e mantenere uno storico delle versioni del programma in base agli update.

Di conseguenza, è presente un **albero** delle versioni, il cui ramo principale è detto <code>main</code>. Le modifiche corrispondono solitamente ai **branch** di questo albero, e ogni nodo dell'albero corrisponde ad un **commit**. Il workflow generale di GitHub è quindi il seguente:
* si sincronizza la cartella locale con la versione più recente del <code>main</code>
* si crea un nuovo branch di lavoro, ovvero un ramo dell'albero principale dal quale dipenderanno tutte le modifiche
    * si eseguono le varie modifiche e test all'interno del proprio branch, senza intaccare la versione principale del programma
    * si esegue il commit all'interno del branch, creando un nuovo nodo nel proprio branch
    * è possibile anche creare più commit, uno di seguito all'altro, in maniera da tenere traccia di tutti gli update all'interno del branch di lavoro
* si esegue il **push** di tutte le modifiche, aggiornando l'albero delle versioni nel repository remoto

> [!WARNING]: Ogni modifica e commit all'interno di qualsiasi branch è sempre *locale*. Prima dell'operazione di push, tutte le modifiche saranno invisibili ad altri utenti. Per questo motivo, è solitamente consigliabile utilizzare branch separati per ogni utente, evitando conflitti tra le modifiche in fase di push.

Una volta eseguito il push, l'albero delle versioni nel repository remoto avrà registrato la creazione del branch, con tutte le modifiche effettuate. Tuttavia, il ramo <code>main</code> sarà ancora alla versione precedente, poichè le modifiche sono ancora legate ai branch.

Per creare una nuova versione del codice, includendo le modifiche contenute in un branch, si esegue una **pull request**: con questa operazione, GitHub permette di aprire un'operazione di confronto tra la versione corrente del <code>main</code> e le modifiche contenute nel branch.
* Se non sono presenti conflitti, GitHub permette di eseguire il **merge** del ramo di modifica, creando un nuovo nodo nel ramo principale e aggiornando la nuova versione del codice.
* In caso di conflitti (modifiche non confermate, o diverse pull request aperte sulla stessa versione del <code>main</code>), è necessario risolvere tutte le sovrapposizioni, valutando manualmente quali modifiche mantenere e quali scartare.

## Integrazione con Visual Studio Code
Per utilizzare efficacemente GitHub all'interno di VS-Code, è sufficiente seguire questi step:
> [!NOTE]: Il primo commit di modifica è quello necessario per la creazione del nuovo branch. Da quello successivo, VS-Code registrerà in automatico tutte le modifiche come appartenenti al branch di lavoro.
* Tramite la combinazione di tasti <code>CTRL+SHFT+G | G</code> è possibile aprire il menu *Source Control*, che permette di eseguire tutti i controlli sulle ultime versioni.
    * Il menu dovrebbe presentarsi con un pulsante *Sync Changes*, indicando che sono presenti nuovi update dalla versione locale del <code>main</code>.
    * Premere il tasto *Sync Changes* per sincronizzare la cartella di lavoro locale con l'ultima versione dell'albero.
* Creare il branch in cui effettuare il commit delle modifiche.
    * Dalla barra degli strumenti in basso, dovrebbe essere presente una serie di icone indicanti lo stato di lavoro di GitHub (sulla sinistra).
    * Tra queste, un'icona dovrebbe presentare anche il nome del branch corrente di lavoro (in questo caso, probabilmente, <code>main</code>).
    * Cliccando sull'icona, dovrebbe apparire un menu in alto contenente la lista di tutti i branch attualmente presenti nel repository.
    * Cliccare sul tasto *Create new branch* e inserire il nome.
* Eseguire la modifica necessaria ai file.
    * Dal menu *Source Control* si dovrebbe visualizzare una lista di tutti i file contenenti modifiche dalla versione remota nel <code>main</code>.
    * Inserendo un messaggio di descrizione delle modifiche effettuate, e cliccando il tasto *Commit* sottostante, è possibile inserire un nuovo nodo nel branch di lavoro, contenente tutte le modifiche eseguite.
* Continuare progressivamente ad apportare modifiche ai vari file durante la fase di lavoro.
    * Ricordarsi di apportare, periodicamente, alcuni commit intermedi, per spezzare il lavoro in più nodi e creare più sottoversioni distinte.
* Al termine delle modifiche necessarie, effettuare il push.
    * Quando non sono presenti modifiche da inserire in un commit, il menu *Source Control* dovrebbe presentare un tasto *Publish Branch*.
    * Cliccando questo pulsante, le modifiche locali sul branch di lavoro vengono sincronizzate nell'albero remoto.

## Creazione della versione
Una volta creato il branch di modifica, ed effettuato il commit degli aggiornamenti, è necessario eseguire una pull request per aggiornare il <code>main</code>.

Questa operazione è eseguita direttamente attraverso GitHub.