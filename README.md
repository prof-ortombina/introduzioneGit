# Introduzione a GIT

In questo repository terremo il materiale per il primo utilizzo di git. 
>Prima di proseguire leggi la seguente introduzione: [Come (e perché!) usare GitHub anche se non sei un programmatore.](https://github.com/marcogovoni/come-usare-github/blob/master/README.md)

Una volta letta l'introduzione ricordati di iscriverti con un nuovo profilo se non ce l'hai già :wink:

### Fatto??

Bene, ora è il momento di collegare il vostro account con una chiave SSH.
>Se non sai cos'è una chiave SSH dai un'occhiata al video [Come funzionano le chiavi SSH?](https://www.youtube.com/watch?v=6if7-0i1ykk)

Adesso occorre generare la chiave SSH. Attenzione, la chiave privata non deve essere data a nessuno per nessun motivo
Aprire il terminale UBUNTU e lanciare il seguente comando:
> ssh-keygen -o -t rsa -C “nome.cognome@iiseinaudiscarpa.edu.it”

Attenzione, se SSH non è un comando riconosciuto occorre installarlo tramite il seguente comando:
> sudo apt install ssh

Premere invio 3 volte

![Cattura](https://user-images.githubusercontent.com/123731204/233328150-e0b583fe-fddc-400e-915b-f7be529911d5.PNG)

Ora la chiave è stata generata.
Aprire la cartella SSH per copiare le chiavi generate.

- 1 - Aprire il file manager
- 2 - Aprire il menu a tendina
- 3 - Accertarsi che siano visibili i file nascosti
- 4 - Accedere alla cartella **.SSH**

![ssh](https://user-images.githubusercontent.com/123731204/233330103-e53ef957-f58c-4a35-b270-4312a4f74b8b.png)

- 5 - Copiare i 2 files contenuti nella cartella e portateli con voi sempre
> ATTENZIONE: il file .pub è pubblico e può essere condiviso, **l'altra chiave è strettamente privata**. Salvatela su una chiavetta ed abbiatene cura.

### Associare la chiave al vostro account.

Dopo aver fatto l'accesso al sito GitHub (versione web) caricare la chiave PUBBLICA seguendo questi passi:
- 1 - Nel menu personale (in alto a dx) selezionate la voce **SETTINGS**
- 2 - Nel menu di sinistra selezionate la voce **SSH and GPG keys**
- 3 - Cliccare su **New SSH Key**

![settings](https://user-images.githubusercontent.com/123731204/233333393-c3828b14-236a-4ebc-92c3-da81146f6c02.png)

Incollare la chiave PUBBLICA (più corta), darle un nome e salvare.

## Verifica connessione

provate a clonare il vostro primo repository con il seguente comando:

> $ ssh -T git@github.com

Attenzione. Nel caso sia presente un errore riportatelo nei commenti
