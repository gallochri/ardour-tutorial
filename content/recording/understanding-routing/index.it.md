---
title: Comprendere il routing
description: Segnale di routing in Ardour
weight: 5
cascade:
  type: docs
---

Il routing di un segnale audio consiste nel trasmetterlo da un punto a un altro.

Oltre a gestire i segnali audio da e verso Ardour, il routing svolge un ruolo importante all'interno dello stesso Ardour. 
Esempi di utilizzo del routing all'interno di Ardour includono il routing dell'audio dalle tracce al bus _Master_ o ad 
altri bus, la creazione di "sends", il routing delle uscite dai bus al bus _Master_, ecc. 
(vedere il capitolo sulla **Creazione di una traccia** per una spiegazione delle tracce e dei bus). 
Tutto il routing, sia interno che esterno ad Ardour, è gestito dal server JACK.

## Routing in Ardour

Il routing standard di ingressi, tracce e bus in Ardour viene determinato quando si crea una nuova sessione nelle 
_Opzioni avanzate_ della finestra di dialogo _Nuova sessione_ (vedere la pagina 
[Avvio di Ardour](../../getting-started/starting-ardour/)). Per impostazione predefinita, il routing è il seguente:

- Gli ingressi del dispositivo audio vengono indirizzati agli ingressi delle tracce. 
- Tutte le uscite delle tracce e dei bus vengono indirizzate agli ingressi del bus master. 
- Le uscite del bus _Master_ vengono indirizzate alle uscite del dispositivo audio.

Si noti che quando viene creato un nuovo bus, nulla viene instradato al suo ingresso.

Questa configurazione di routing ha senso per sessioni contenenti solo tracce, ma per utilizzare qualsiasi bus 
(diverso dal bus _Master_) o per essere creativi con i percorsi dei segnali audio all'interno di Ardour, dobbiamo essere
in grado di modificare il routing.

La finestra _Audio Connection Manager_ (nota anche come patchbay) è lo strumento principale per effettuare connessioni 
da, verso e all'interno del mixer di Ardour. È possibile aprire questa finestra con la scorciatoia **Shift + Alt + A** o
tramite il menu `Finestre >> Connessioni audio`.

{{< figure alt="Audio Connection Manager" src="it/ardour8-audio-connections-in-menu.png" >}}

Il patchbay presenta due gruppi di porte: un set di sorgenti e uno di destinazioni. Le sorgenti e le destinazioni sono 
organizzate per schede. Le sorgenti disponibili sono visualizzate verticalmente sul lato sinistro, mentre le 
destinazioni sono visualizzate orizzontalmente nella parte inferiore.

Nello screenshot qui sotto, nota che la scheda _Hardware_ è selezionata in alto a sinistra (sorgenti) e che 
_*Tracce*_ è selezionato come destinazione in basso. Questo significa che la matrice che vedi mostra le 
connessioni dalle sorgenti audio hardware disponibili (per esempio, un microfono) alle tracce Ardour esistenti.

{{< figure alt="ACM 1" src="it/ardour8-audio-connection-manager-1.png" >}}

I punti verdi rappresentano una connessione. Lo screenshot sopra ci dice che i suoni in entrata da Alder Lake Digital Microphone 
_capture_FL_ (la prima sorgente di ingresso della scheda audio o il microfono integrato del laptop) vengono inviati alla
traccia Ardour denominata _Audio 1_, e che i suoni in entrata da Alder Lake Stereo Microphone _capture_FL_ e _capture_FR_ vengono inviati all'ingresso della traccia
Ardour denominata _Audio 2_.

Notiamo che _Audio 1_ è una traccia mono perché ha un solo slot di connessione, mentre la traccia _Audio 2_ è stereo 
perché ha due slot (sinistro e destro).

La schermata seguente mostra il percorso del segnale dalle tracce Ardour (scheda verticale selezionata) ai bus Ardour 
(scheda orizzontale selezionata). Come accennato in precedenza, l'impostazione predefinita per tutte le tracce Ardour è 
che il loro suono venga inviato al bus Master.

{{< figure alt="ACM 2" src="it/ardour8-audio-connection-manager-2.png" >}}

Nota: ricordi che _Audio 1_ è una traccia mono? Abbiamo visto nella schermata precedente che _Audio 1_ ha un solo slot 
di ingresso. Ma ora nella schermata sopra puoi vedere che "Audio 1" ha due uscite (sinistra e destra). Questo è normale:
definiamo se una traccia è mono o stereo in base al suo _numero di ingressi_, non alle uscite. Le tracce mono contengono
un solo canale audio, ma è comunque possibile scegliere di posizionare il suono sull'altoparlante sinistro o destro (o 
in qualsiasi punto intermedio). Per ulteriori informazioni al riguardo, consultare il capitolo _Panning_.

Infine, esploriamo un altro paio di schede nel _Gestore delle connessioni audio_ per vedere il suono che passa dal bus 
_Master_ alle uscite hardware effettive (altoparlanti o cuffie):

{{< figure alt="ACM 3" src="it/ardour8-audio-connection-manager-3.png" >}}

Come puoi vedere, la scheda sorgente selezionata ora è _Bus_, mentre la scheda di destinazione è _Hardware_. Questa 
sessione ha un solo bus, il "master out" predefinito. I punti verdi indicano che tutti i suoni provenienti dal bus 
_Master_ vengono inviati alle uscite di riproduzione 1 e 2 del sistema, che sono le uscite della tua scheda audio.

## Come collegarsi e scollegarsi?

Per creare una connessione, clicca sul quadrato vuoto desiderato nella matrice; apparirà un punto verde per indicare che
la connessione è stata creata.

Per annullare una connessione, basta cliccare su un punto verde esistente e questo scomparirà.

C'è un trucchetto che puoi usare quando devi mappare molte uscite mono/stereo su molte entrate mono/stereo: invece di 
fare tanti clic singoli, traccia una linea di connessione. Ecco come fare:

{{< figure alt="Drawing connection lines" src="it/ardour7-drawing-connection-lines.gif" >}}

## Esempio pratico di routing verso un bus

Nella seguente sessione di esempio, ci sono due tracce di chitarra e un bus inutilizzato chiamato _Bus chitarra_, tutti 
stereo.

{{< figure alt="ACM 4" src="it/ardour8-audio-connection-manager-4.png" >}}

Supponiamo che tu voglia inviare l'output delle due tracce di chitarra al bus _Guitar_ invece che al bus _Master_. 
Questo può essere utile per controllare il volume di entrambe le chitarre con un solo fader (in questo caso il fader del 
_Bus chitarra_) o per inserire due strumenti nella stessa stanza virtuale utilizzando un plugin di riverbero sul bus. 
Quindi l'output del _Bus chitarra_, che è la somma delle due chitarre, va direttamente al bus _Master_.

Ecco come modificare il gestore delle connessioni per ottenere il routing desiderato. Seleziona la scheda _Tracce_ da 
_Sorgenti_ (schede verticali) e _Bus_ dalle destinazioni (schede orizzontali in basso). Annulla le connessioni esistenti
da entrambe le tracce a _Master_. Quindi crea connessioni da entrambe le tracce al _Bus chitarra_. Il risultato finale 
sarà simile a questo:

{{< figure alt="ACM 5" src="it/ardour8-audio-connection-manager-5.png" >}}

Ora entrambe le tracce di chitarra sono indirizzate al _Bus chitarra_ e non sono più collegate direttamente al bus 
_Master_. Ci assicuriamo quindi che il _Bus chitarra_ sia a sua volta indirizzato al bus _Master_ (l'indirizzamento 
dell'uscita di un bus viene modificato allo stesso modo di una traccia), in modo da poter ancora ascoltare il suono di 
entrambe le tracce di chitarra. Ora possiamo controllare il volume di entrambe le tracce di chitarra insieme modificando
il fader del _Bus chitarra_. Inoltre, ora possiamo aggiungere plugin al _Bus chitarra_ per elaborare il suono di 
entrambe le tracce di chitarra insieme.

## Viste specifiche per traccia o bus del gestore delle connessioni

Il gestore delle connessioni audio (Patchbay) che si apre con **Alt + P** mostra la matrice completa di ogni singola 
sorgente e ogni singola destinazione disponibile in Ardour. A volte questo è eccessivo: si desidera solo modificare 
rapidamente il routing di un singolo ingresso o uscita di traccia. Ardour consente di accedere a un sottoinsieme 
rilevante delle connessioni Patchbay quando si fa clic direttamente sul pulsante **Inputs** o **Outputs** di una traccia
o di un bus nella striscia del mixer.

Il pulsante **Inputs** si trova nella parte superiore, mentre il pulsante **Outputs** si trova nella parte inferiore 
della striscia. Cliccando su uno dei due pulsanti verrà visualizzato un menu con le opzioni di connessione. Nello 
screenshot qui sotto, ad esempio, è necessario cliccare sul pulsante **Bus chitarra** proprio sotto il nome della bus 
_Master_ per accedere a questo menu:

{{< figure alt="Editor Mixer In Out" src="it/ardour8-editor-mixer-in-out.png" >}}

È possibile selezionare una connessione direttamente dal menu oppure scegliere _Cablaggio_ per visualizzare una versione
semplificata del _Manager delle connessioni audio_ con solo gli **Input** o gli **Output** della traccia o del bus 
selezionato.

## Tutte le connessioni Ardour sono connessioni JACK.

È importante rendersi conto che qualsiasi routing effettuato o disconnesso all'interno di Ardour è in realtà un routing 
JACK, che è possibile visualizzare da altre applicazioni come _Qjackctl_ o _Catia_, a seconda del sistema operativo in 
uso. Di seguito è riportato un esempio di una finestra _Catia_ (solo Linux) che mostra le stesse connessioni JACK 
discusse sopra:

{{< figure alt="Catia" src="en/Ardour4_Catia_Example.png" >}}

**Continua**

In questo capitolo abbiamo visto come gestire il routing all'interno di Ardour o tra Ardour e la scheda audio. Tuttavia,
uno dei punti di forza dell'utilizzo del sistema JACK è che può anche gestire le connessioni tra applicazioni sullo 
stesso computer. Per comprendere meglio come funziona, continua con il capitolo 
[routing tra applicazioni](/recording/routing-between-applications/). 
Se preferisci lavorare solo con Ardour, passa alla sezione [disposizione delle tracce](/editing-sessions/arranging-tracks/).
