- [How to create the website?](#how-to-create-the-website)
  - [What do we need?](#what-do-we-need)
- [Step by Step Guide](#step-by-step-guide)
  - [One-click installer](#one-click-installer)
- [How to manage the website?](#how-to-manage-the-website)
  - [Cloning locally](#cloning-locally)
  - [Manage the website](#manage-the-website)
  - [Website Structure](#website-structure)
    - [Theme](#theme)
  - [First modifications](#first-modifications)
  - [Home](#home)
  - [New contents](#new-contents)
    - [How to create a new content?](#how-to-create-a-new-content)
      - [Available templates](#available-templates)
      - [Link to other files](#link-to-other-files)
    - [Save and upload all modifications](#save-and-upload-all-modifications)
      - [Commit and Push](#commit-and-push)
  - [Useful Links](#useful-links)

# How to create the website?

Nella mia [breve introduzione](https://github.com/filippogambarota/hugo_tutorial) ad Hugo avevo suggerito di utilizzare **blogdown** e quindi RStudio per creare da zero il sito. Tuttavia essendo che partiremo da un **template modificato** utilizzeremo un approccio leggermente diverso.
Questo template è un semplice adattamento del tema **Academic** con alcune modifiche estetiche e di struttura:

* Sezioni per post, talk, poster e insegnamenti
* Una sezione specifica per Psicostat con link al sito web, feed di Twitter aggiornato e non per ultimo il nostro motto.

Inoltre molte funzioni e link sono stati rimossi (o meglio semplicemente disattivati) per semplificare l'interfaccia ed il funzionamento. Tuttavia il bello di questo framework è la totale personalizzazione, pur partendo però da un template semplice.

## What do we need?

* [GIT](https://git-scm.com/) e [Hugo](https://gohugo.io/) installati sul PC
* Un account [Github](https://github.com/).
* Un account [Netlify](https://www.netlify.com/).
* RStudio con il pacchetto Blogdown oppure un'altra IDE ([VSCode](https://code.visualstudio.com/) super raccomandato). 

Nel caso vogliate usare RStudio assicuratevi di aver correttamente attivato GIT in RStudio. In caso contrario, seguite le indicazioni contenute nella [documentazione ufficiale](https://support.rstudio.com/hc/en-us/articles/200532077?version=1.3.322&mode=desktop) e per ulteriori informazioni riguardanti l'utilizzo di GIT da RStudio consiglio il [presente link](http://r-pkgs.had.co.nz/git.html). Inoltre è consigliato installare il pacchetto **blogdown** (`install.packages("blogdown")`).

In alternativa, [VSCode](https://code.visualstudio.com/) è veramente un super software con un sacco di plugin per HTML, Markdown e CSS (oltre anche ad R e Python). L'integrazione con GIT e Github è molto più rapida ed efficiente di RStudio. 

Tuttavia, la modalità più efficiente di usare GIT e Github rimane l'utilizzo del terminale e questo ovviamente è possibile sia con RStudio che con VSCode.

# Step by Step Guide

## One-click installer

Una volta creato l'account Github e Netlify, il modo più semplice e veloce per creare il sito e collegarlo direttamente a Netlify è andare su [questo link](https://app.netlify.com/start/deploy?repository=https://github.com/filippogambarota/psicostat_template). 

In questo modo si crea automaticamente una repository (copiando il template `filippogambarota/psicostat_template`) sul proprio account Github e si connette direttamente su Netlify. In fase di creazione si potrà rinominare la repository e successivamente anche il dominio del sito dal pannello di controllo di Netlify.

All'interno della repository c'è un file `netlify.toml` che contiene tutti i settaggi che Netlify userà per i deploying. Di conseguenza non dovrebbe essere necessario modificare nessuna impostazione. Nella `fig.1` è si vede il pannello di controllo con il sito creato (se il nome non è stato modificato il sito avrà un nome strano autogenerato). Cliccando sul sito si accede (fig.2) al pannello di controllo dove modificare le impostazioni (non consigliato) e il dominio (`domain settings`).


<div class="row text-center"><img src="img/netlify1.png" alt="fig.1" width="500" align="middle"></div>

<div class="row text-center"><img src="img/netlify2.png" alt="fig.2" width="300" align="middle"></div>

# How to manage the website?

## Cloning locally

A questo punto è possibile modificare i file direttamente da Github per aggiornare il sito. Tuttavia, l'interfaccia di Github è molto scomoda. Per gestire il sito, è quindi preferibile utilizzare RStudio o VSCode che permettono di modificare i file localmente e poi fare il `push` delle modifiche a Github.

In RStudio, per copiare la repository localmente, è necessario creare un nuovo Project (`File`->`New Project`) selezionando l'opzione `Version Control` e come sistema GIT. Successivamente è necessario indicare l'URL della Repository, il nome della cartella del Project (di default viene usato lo stesso nome della repository) e dove si vuole creare il Project.

<div class="row text-center">
<img src="img/Rproject_version_control.png" width="30%" align="middle">
<img src="img/Rproject_git.png"  width="30%" align="middle">
<img src="img/Rproject_name.png"  width="30%" align="middle">
</div>

Per ottenere l'URL della repository, dalla pagina di Github premete il tasto verde `Clone or download` e copiate l'indirizzo. Una volta creato il progetto tutti la repository verrà automaticamente clonata localmente.

<div class="row text-center"><img src="img/Clone_Download.png" width="90%" align="middle"></div>

In alternativa utilizzando il terminale, è sufficiente posizionarsi nella cartella dove si vuole mantenere il sito e utilizzare il seguente comando (mettendo il proprio `#nomeutente` e `#nomerepository`):

```git
git clone https://github.com/#nomeutente/#nomerepository.git
```



## Manage the website


La documentazione di [Hugo](https://gohugo.io/documentation/) e del [tema Academic](https://sourcethemes.com/academic/docs/) sono veramente ottime e complete. Tuttavia, inizialmente la  struttura del sito risulta coplessa poichè vengono utilizzati molti files con diversi linguaggi (GO, TOML, HTML, CSS e Markdown).

Di seguito vengono quindi riportate le informazioni essenziali rispetto alla struttura, i comandi e le funzioni per inserire i propri dati e gestire quotidinamente il sito. Per chi fosse interessato ad approfondire questi aspetti oppure personalizzare ulteriormente il template, ulteriori link sono indicati nella documentazione e le principali risorse sono elencate nella [sezione finale](#useful-links).

Prima di cominciare a modificare il sito, ci sono due modi per capire se la procedura finora è andata a buon fine:

* Se il sito è online all'indirizzo di Netlify
* Da Rstudio premere il comando `Addins -> Serve Site` per creare e visualizzare automaticamente il sito.
<div class="row text-center"> <img src="img/serve_site.png" width="44%" align="middle"> </div>

* Da terminale, dopo aver clonato la repository localmente, posizionarsi nella `root` della cartella e utilizzare il seguente comando che permette di compilare il sito e fornisce un indirizzo locale per vedere il funzionamento.:
``` terminal
hugo server
```

Il fatto che il sito sia compilato senza errori e venga visualizzato significa che non ci sono problemi nella struttura.

## Website Structure

Nella cartella principale del sito troviamo:

* Il file `.Rproj` che permette di aprire e gestire il sito con RStudio essendo che è stato creato inizialmente con il pacchetto **blogdown**.
* Il file `config.toml` che contiene la configurazione di base del sito.
* Il file `netlify.toml` che contiene i settaggi per il deploying online
* La cartella `content` che contiene tutti i file e le immagini delle varie sezioni del sito del sito. Questa cartella sarà quella che maggiormente verrà modificata.
* La cartella `static` che contiene file e materiale che si vogliono visualizzare nel sito come ad esempio il proprio **CV**.
* La cartella `data` che contiene i file `.toml` del tema modificato,che determinano colori e  fonts dell'intero sito.
* La cartella `config` che contiene altri file di configurazione di base (simili a `config.toml`) del sito come la **lingua**, tutte le **informazioni di contatto**, le eventuali **mappe** da visualizzare, i **link ai social network** e sopratutto la **struttura del menu home**.
* La cartella `public` contiene la versione compilata del sito che viene mandata online (in altri termini le pagine scritte in Markdown o RMarkdown vengono compilate in HTML e inserite nella cartella per la visualizzazione da browser).

### Psicostat template and Academic Theme 

La cartella `theme` contiene la struttura di default del tema Academic. Questa cartella non va assolutamente modificata.

Le restanti cartelle (`archetypes`, `assets`, `i18n` e `layouts`) contengono i file utilizzati per definire i cambiamenti del template psicostat rispetto al tema Academic. Anche questi file non andrebbero modificati a meno che non si voglia modificare e personalizzare il funzionamento del sito.


<div style="color:red">
All'interno della cartella `theme/layouts` ci sono invece le tipologie di contenuti che possiamo creare (anche qui personalizzabili) come le pubblicazioni, i talk e cosi via.


se non per cambiare gli [archetypes](https://gohugo.io/content-management/archetypes/). Questi non sono altro che i template che verranno utilizzati quando si useranno i [comandi](#how-to-create-a-new-content) di `hugo` per la creazione di contenuti. 

</div>


## First modifications

Un buon modo di modificare il sito web è quello di compilare il sito con il comando `Serve Site` di Rstudio o da terminale eseguire `hugo server`. Questo, oltre a controllare la struttura, permette di avere un indirizzo locale dove tutte le modifiche vengono visualizzate in tempo reale. Così una volta soddisfatti possiamo effettuare il **commit** ed il **push**.

Le prime cose che consiglio di fare sono:

1. Aprire i vari file di configurazione `.toml` e cambiare le impostazioni desiderate come contatti, link e nome del sito. Il logo e in generale tutte le immagini sono contenute nella cartella `static/img` quindi è sufficiente cambiare l'immagine e inserire il nome nei file di configurazione per cambiare anche il logo. Se non è necessario per il momento non cambiare la struttura della home nel file `menus.toml`.
2. Prima dei contenuti veri e propri è utile aggiornare il proprio profilo come autore. Essendo che il sito supporta diversi autori con diversi profili se si modifica l'autore principale (`admin`) ogni volta che in un post o pubblicazione inseriamo `admin` come autore automaticamente si farà riferimento a quel profilo con le informazioni associate. Per modificare il profilo autore andare su `content/authors/admin/_index.md`. Ci sono varie informazioni da inserire come i link social con le icone.
3. E' inoltre possibile inserire l'immagine del profilo che appare nella pagina personale sostituendo e rinominando la foto come `avatar.jpg`.

## Home

A questo punto le informazioni di base nostre e del sito sono inserite. Il prossimo passo è capire il funzionamento della schermata home. Nella cartella `content/home` sono contenute le varie pagine `.md` con le informazioni che appaiono nella schermata home.

Le varie pagine sono create su dei `widget` base che fanno parte del tema e che sono il punto di partenza per creare delle sezioni personalizzate. Ad esempio la sezione **Psicostat** non è altro che un `widget blank` ([link alla documentazione per informazioni sui widget](https://sourcethemes.com/academic/docs/page-builder/)) dove sono stati inseriti il feed di twitter, un'immagine e un titolo.

I vari widget hanno delle caratteristiche di struttura, aspetto e funzionalità. Ad esempio la pagina `Skill` è basata sul widget `featurette` che permette di creare quelle icone a blocchi che indicano le nostre skills in modo grafico. All'interno delle pagine nella cartella home ci sono dei comandi di configurazione racchiusi tra `+++` (concettualmente è identico al codice YALM racchiuso tra `---`prima di un documento in KNITR) e il testo che viene scritto direttamente in Markdown ma anche in HTML (per alcune feature avanzate). Ogni funzione di configurazione è documentata con dei commenti dell'autore.

Un'aspetto importante è il parametro `weight =` che indica l'ordine di visualizzazione nella pagina. Diverse invece sono le sezioni in alto nella home. Sostanzialmente possiamo creare una nuova sezione della home, come **Psicostat** e collegarla ad un widget nella pagina principale.

Nel file `config/_default/menus.toml` abbiamo le sezioni che vengono visualizzate in alto dove `name` indica il nome da visualizzare e `#nome` indica il nome del file `.md` all'interno della cartella `content/home`. In questo modo quando viene premuto il collegamento in alto, il sito indirizza alla sezione corrispondente.
Ovviamente è possibile creare una sezione con un link esterno (un sito web) oppure,come indicato in fondo al file `menus.toml` ad un CV in formato pdf.

## New contents

Ora il sito è strutturato e organizzato. Per creare nuovi contenuti ci sono varie modalità e quindi vi presento la modalità che mi sembra più semplice ed efficace. All'interno della cartella `content` abbiamo tutti i vari tipi di contenuti disponibili. Il sito di base fornisce degli esempi che oltre a far capire cosa e come scrivere il contenuto vero e proprio fa vedere anche come organizzare le cartelle. Ad esempio la cartella `content/publication` contiene le varie pubblicazioni (una per cartella) che verranno poi visualizzate nella sezione **Publications** che abbiamo visto prima nella cartella `content/home`. Il file `index.md` contiene alcuni elementi tipici del template per le pubblicazioni già presente nel tema. Anche qui ci sono delle info di base contenute in linguaggio YAML `---` con inoltre dei link da mettere per altro materiale come poster, database, repository e così via.

### How to create a new content?

Per creare un nuovo contenuto sarebbe semplicemente necessario creare un nuovo file Markdown con l'intestazione uguale a quella di un articolo già presente e poi inserire le informazioni. Un modo più semplice però consiste nell'utilizzare le funzioni di Hugo per creare dei contenuti.

Se apriamo il terminale nella root del nostro sito e digitiamo:

```
hugo new --kind #tipo_template cartella/nome_file
```

Automaticamente si crea una cartella nel percorso selezionato con un file Markdown strutturato secondo il template indicato. Se vogliamo ad esempio creare una nuova pubblicazione possiamo digitare:

#### Available templates

Le tipologie di template disponibili (argomento #tipo_template) in questo adattamento del tema sono:
* publication
* talk
* poster (nuovo rispetto al tema standard)
* teaching (nuovo rispetto al tema standard)
* post

Sono disponibili anche altri contenuti come i projects ma per il momento sono stati disattivati.

#### Link to other files

Nei vari contenuti che scriviamo o a cui vogliamo collegarci con un link c'è la possibilità di inserire dei file che risiedono effettivamente nel sito come immagini, i full-text degli articoli o altro materiale.

Ad esempio se nell'articolo vogliamo inserire un link al pdf (`url_pdf =`)possiamo mettere un link web per esempio al full-text della rivista o al sito stesso del database oppure creare un link ad un file che effettivamente è memorizzato nel sito. 

Tutti i file sono contenuti nella cartella `static` oppure nella cartella specifica del contenuto.
* Se il file/immagine è contenuto nell cartella static: **inserire la path al file senza la cartella static** e quindi per esempio se abbiamo un pdf nella cartella static semplicemente inserire il link come `nome.pdf`. Nel caso fosse in sottocartelle inserire `folder/nome.pdf`.
* Se il file/immagine è all'interno nella cartella del contenuto specifico tipo: `post/il_mio_post` come nel caso precedente inserire direttamente `file.estensione` oppure `cartella/file.estensione` nel caso sia in una sottocartella.

### Save and upload all modifications

Questo è sicuramente lo step più importante. Tutte le modifiche che sono state fatte fino ad ora saranno state sicuramente visualizzate nella **versione locale** del sito (con il comando `hugo server`). Per salvare una modifica è sufficiente semplicemente salvare il file dove questa è stata fatta. **Se il sito viene compilato senza errori significa che anche la versione online non avrà problemi.**

Tutte le modifiche locali però devono passare per altri 2 importanti step per essere effettivamente online:

1. Deve essere effettuato un `commit` tramite GIT (quindi in locale) con un messaggio di commit sensato in modo da rendere più facile tornare indietro per eventuali errori.
2. Effettuare il `push` delle modifiche alla repository Github (quindi online). A questo punto Netlify rileverà le modifiche e il sito sarà aggiornato in qualche minuto.

#### Commit and Push

Per effettuare il commit e il push si possono utilizzare i comandi GUI del programma che usiamo oppure scrivere da terminale:

```git
git add -A #per aggiungere tutte le modifiche al commit
git commit -m "Message" #commit con messaggio
git push #mandare tutte le modifiche a Github
```
## Useful Links

Ci sono due fonti principali per approfondire la documentazione:

* [Documentazione Hugo](https://gohugo.io/documentation/)
* [Documentazione Academic Theme](https://sourcethemes.com/academic/docs/)

La documentazione di Hugo è molto approfondita (e anche complessa). Per gestire e modificare questo template ho trovato sufficiente quella del tema Academic e queste pagine della documentazione di Hugo:
* https://gohugo.io/content-management/archetypes/ (Archetipi)
* https://gohugo.io/content-management/types/ (Modificare e aggiungere tipologie di contenuti collegati agli archetipi)
* https://gohugo.io/commands/hugo/ (i comandi di hugo in particolare `hugo server` e le varie tipologie di `hugo new`)

Altre risorse utili sono:
* La [repository Github](https://github.com/gcushen/hugo-academic) di Academic in particolare la sezione [issues](https://github.com/gcushen/hugo-academic/issues) perchè ci sono molti problemi comuni.
* La [chat/forum](https://spectrum.chat/academic?tab=posts) degli utenti del tema.
* La documentazione del pacchetto [Blogdown](https://bookdown.org/yihui/blogdown/) sia per utilizzare il pacchetto ovviamente ma anche per capire la struttura di Hugo.