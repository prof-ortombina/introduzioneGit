# ATTIVAZIONE GIT

## Configurazione iniziale e primo utilizzo

Di seguito le istruzioni per il primo utilizzo di git in ambiente linux (ubuntu), con connessione tramite SSH.

## Introduzione

In questo repository terremo il materiale per il primo utilizzo di git. 

>Prima di proseguire leggi la seguente introduzione: [Come (e perché!) usare GitHub anche se non sei un programmatore.](https://github.com/marcogovoni/come-usare-github/blob/master/README.md)

Una volta letta l'introduzione ricordati di iscriverti con un nuovo profilo se non ce l'hai già :wink:

Per i minorenni: **Ricordatevi di chidere l'autorizzazione ai vostri genitori per iscrivervi**

Fatto?? Se hai già installato UBUNTU (o altra distribuzione linux) con git e ssh installati prosegui allo step di creazione del tunnel SSH.

## Installazione LINUX:
Potete trovare ovunque informazioni dettagliate su come installare ubuntu. Nel nostro corso utilizzaremo UBUNTU 20, preinstallato sulle nostre macchine virtuali vmWare (ambiente windows). Se non riuscite a creare un SO su macchina virtuale a casa allora potete provedere con delle alternative:
 - Installare il SO in versione portable su una chiavetta USB tramite il software [Linux Live USB Creator](https://www.linuxliveusb.com/)
 > NOTA: per far partire il SO da USB occorre avere accesso al bios ed attivare il boot da USB in via prioritaria rispetto al disco
 - [Installare il SO in dual boot](https://turbolab.it/dual-boot-778/come-installare-ubuntu-20.04-fianco-windows-10-guida-definitiva-dual-boot-video-81)

## Installazione SSH

Attenzione, se SSH non è un comando riconosciuto occorre installarlo tramite il seguente comando:
> sudo apt install ssh

## Installazione GIT

Attenzione, se git non è un comando riconosciuto occorre installarlo tramite il seguente comando:
> sudo apt install git

## Tunnel SSH

Bene, ora è il momento di collegare il vostro account con una chiave SSH.
>Se non sai cos'è una chiave SSH dai un'occhiata al video [Come funzionano le chiavi SSH?](https://www.youtube.com/watch?v=6if7-0i1ykk)

Adesso occorre generare la chiave SSH. Attenzione, la chiave privata non deve essere data a nessuno per nessun motivo
Aprire il terminale UBUNTU e lanciare il seguente comando:
> ssh-keygen -o -t rsa -C “nome.cognome@iiseinaudiscarpa.edu.it”

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

## Associare la chiave al vostro account.

Dopo aver fatto l'accesso al sito GitHub (versione web) caricare la chiave PUBBLICA seguendo questi passi:
- 1 - Nel menu personale (in alto a dx) selezionate la voce **SETTINGS**
- 2 - Nel menu di sinistra selezionate la voce **SSH and GPG keys**
- 3 - Cliccare su **New SSH Key**

![settings](https://user-images.githubusercontent.com/123731204/233333393-c3828b14-236a-4ebc-92c3-da81146f6c02.png)

Incollare la chiave PUBBLICA (più corta), darle un nome e salvare.

## Verifica connessione

provate a clonare il vostro primo repository con il seguente comando:

> $ ssh -T git@github.com

# LET'S GO

## Clonare un repository tramite SSH

Per clonare un repository tramite SSH occorre selezionare l'url del repository dal sito

![Immagine 2023-04-27 170825](https://user-images.githubusercontent.com/123731204/234906175-ec44956e-9e3a-4e52-a135-e2bd0e489e43.jpg)

Una volta copiato l'url basta lanciare il comando git clone

> git clone git@github.com:prof-ortombina/introduzioneGit.git

## Allineare il repository con la versione remota

Per allineare il repository con la versione remota (prendere le modifiche) lanciare il comando pull

> git pull

## I Branch

### Visualizzare i branch

Per visualizzare i branch in un repository Git esegui il comando:

>git branch

Per vedere sia i branch tracciati su remoto che i branch locali esegui il comando:

>git branch -a

Ci sarà un asterisco (*) a fianco del branch sul quale ti trovi attualmente.

### Passare da un branch a un altro

Per passare da un branch a un altro branch esistente (azione di checkout) esegui il comando:

>git checkout NOME-BRANCH

In genere Git non ti lascerà uscire per passare a un altro branch, a meno che la tua directory di lavoro sia pulita, in quanto perderesti qualsiasi modifica fatta che non sia stata soggetta a commit. Hai tre opzioni per gestire le tue modifiche:

 - sbarazzartene (vedi Git checkout per dettagli) oppure
 - effettuare un'azione di commit (vedi Git commit per dettagli) oppure
 - accantonarle (vedi Git stash per dettagli).

### Creare un nuovo branch

Per creare un nuovo branch esegui il comando:

> git branch NOME-NUOVO-BRANCH

Nota che questo comando crea solamente il nuovo branch. Per spostarti devi eseguire il comando git checkout NOME-NUOVO-BRANCH.
Quando crei un nuovo branch, verranno inclusi tutti i commit del branch genitore. Il branch genitore è quello nel quale di trovi quando crei il nuovo branch.

### Eliminare un branch

Git non ti consente di eliminare il branch sul quale ti trovi attualmente. Prima devi passare a un altro branch, quindi eseguire il comando:

> git branch -d BRANCH-DA-ELIMINARE

### Confrontare dei branch

Puoi confrontare dei branch con il comando git diff:

> git diff PRIMO-BRANCH..SECONDO-BRANCH

Vedrai un risultato con testo colorato per evidenziare le modifiche tra i branch. Per tutte le righe modificate, la versione SECONDO-BRANCH avrà una riga verde che inizia con un  ”+”, e la versione PRIMO-BRANCH avrà una riga rossa che inizia con un  ”-“. Se non vuoi che Git visualizzi due righe per ogni modifica, puoi usare l'opzione --color-words (colora parole), nel qual caso Git mostrerà una riga con il testo eliminato in rosso e il testo aggiunto in verde.

Se vuoi vedere un elenco di tutti i branch sui quali è stata eseguita un'azione di merge per tutte le modifiche verso il branch corrente (in altre parole se il tuo branch corrente include tutte le modifiche fatte negli altri branch in elenco), esegui il comando git branch --merged.

### Aiuto per Git branch

Se non ti ricordi come si usa un'opzione, oppure vuoi esplorare altre funzionalità del comando git branch, puoi eseguire uno qualunque di questi comandi:

> git help branch
> git branch --help
> man git-branch

## comando Git checkout

Nella pratica, il checkout di un branch aggiorna i file nella working directory in modo che corrispondano alla versione memorizzata in quel branch e istruisce Git di registrare tutti i nuovi commit su quel branch. Il comando git checkout in Git è particolarmente importante per poter lavorare con branch resi disponibili su repository remoti.

> git checkout NOME_BRANCH

## Aggiungere un file all'area di staging

Il comando git add aggiunge una modifica presente nella working directory alla staging area. È il modo per dire a Git quali particolari modifiche verranno inserite nel prossimo commit.

> git add NOME_FILE

## Il commit

Il comando git commit fissa nella history del progetto uno snapshot dello stato attuale, ovvero una versione “sicura” o “rilevante” del progetto stesso. Le modifiche incluse nel salvataggio sono quelle che sono state esplicitamente incluse nella staging area tramite il comando git add.

Se eseguito senza opzioni, viene aperto un editor di testo (configurabile tramite git config) per inserire il messaggio che descrive il commit. Una volta salvato il messaggio, viene creato il commit.

> git commit -a 

esegue il commit di tutte le modifiche presenti nella working directory (in pratica esegue anche il git add di tutti i file sotto controllo di versione che hanno modifiche)

> git commit -m "commit message"

indica il messaggio di commit, non verrà aperto l’editor di testo

> git commit -am "commit message" 

la combinazione dei due precedenti

>git commit --author="Jane Doe <jade.doe@example.com>"

permette di indicare l’autore delle modifiche, distinguendo tra autore (Jane Doe) ed esecutore del commit (il propio user.name e user.email)



BIBLIOGRAFIA/SITOGRAFIA:

github.com

aulab.it

freeCodeCamp.org (Traduttore: Roberto Pauletto)

Author: Ivan Ortombina
