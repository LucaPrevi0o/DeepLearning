# Uso di GitHub - Estensione Visual Studio Code
> Per utilizzare le funzionalità GitHub all'interno di VS-Code, è necessario effettuare l'accesso al proprio profilo GitHub all'interno del programma. Per effettuare l'accesso, vedere il [resto della guida](#accesso-a-github).

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

> IMPORTANTE: Ogni modifica e commit all'interno di qualsiasi branch è sempre *locale*. Prima dell'operazione di push, tutte le modifiche saranno invisibili ad altri utenti. Per questo motivo, è solitamente consigliabile utilizzare branch separati per ogni utente, evitando conflitti tra le modifiche in fase di push.

Una volta eseguito il push, l'albero delle versioni nel repository remoto avrà registrato la creazione del branch, con tutte le modifiche effettuate. Tuttavia, il ramo <code>main</code> sarà ancora alla versione precedente, poichè le modifiche sono ancora legate ai branch.

Per creare una nuova versione del codice, includendo le modifiche contenute in un branch, si esegue una **pull request**: con questa operazione, GitHub permette di aprire un'operazione di confronto tra la versione corrente del <code>main</code> e le modifiche contenute nel branch.
* Se non sono presenti conflitti, GitHub permette di eseguire il **merge** del ramo di modifica, creando un nuovo nodo nel ramo principale e aggiornando la nuova versione del codice.
* In caso di conflitti (modifiche non confermate, o diverse pull request aperte sulla stessa versione del <code>main</code>), è necessario risolvere tutte le sovrapposizioni, valutando manualmente quali modifiche mantenere e quali scartare.

<hr/>

## Integrazione con Visual Studio Code
VS-Code permette di lavorare con GitHub nativamente, offrendo tutte le operazioni di gestione delle versioni attraverso la GUI del programma ed evitando la necessità di passare per i comandi da terminale.

### Accesso a GitHub
Per utilizzare GitHub nell'ambiente di Visual Studio Code, è necessario accedere al proprio profilo:
* Selezionare il menu *Accounts*