---
title: Lavorare con le regioni
description: Selezionare, dividere e spostare regioni in Ardour
weight: 5
cascade:
  type: docs
---

Le sezioni audio sono chiamate _regioni_ in Ardour. Per comporre il breve passaggio ritmico su cui stiamo lavorando, 
dovremo sapere come _selezionare_, _spostare_, _dividere_ e _tagliare_ queste regioni, nonché come _sfumare_ o 
_attenuare_ il loro volume e creare _dissolvenze incrociate_ tra di esse. Alcune di queste opzioni potrebbero dover 
essere applicate in specifici _punti di modifica_ della composizione, oppure in base al _metro_ musicale che possiamo 
definire con la _timeline_ e la _griglia_.

## Selezione delle regioni

La modalità _Mano_ (scorciatoia **G**) è lo strumento che consente di selezionare e spostare gli oggetti. Si trova 
appena sotto il menu di trasporto nella finestra _Editor_ (la piccola icona a forma di "mano"). Utilizzerete spesso 
questo strumento durante il vostro lavoro con Ardour.

{{< figure alt="Strumento mano" src="it/ardour8-grab-mode.png" >}}

Quando è attivo, il puntatore del mouse assumerà l'aspetto di una piccola icona a forma di mano.

Prova tutte le operazioni riportate di seguito, per fare pratica:

- Clicca sulla forma d'onda della regione per selezionarla. Clicca e trascina su una regione per spostarla (a sinistra e
a destra all'interno della stessa traccia, ma anche su e giù su altre tracce).

- Utilizza **Ctrl+clic** per creare e trascinare una _copia_ della regione.

- È possibile selezionare più regioni tenendo premuto il tasto **Shift** mentre si fa clic su ciascuna regione che si 
desidera selezionare.
    
- È anche possibile trascinare un riquadro di selezione su più regioni per selezionarle tutte.

{{< figure alt="Selezione oggetto" src="it/ardour8-object-selection.png" >}}

- Seleziona più regioni contemporaneamente e spostale tutte insieme.

- È possibile selezionare più regioni sequenziali su una traccia contemporaneamente tenendo premuto il tasto **Shift** 
mentre si selezionano la prima e l'ultima regione della sequenza (copiare alcune regioni sulla stessa traccia per 
provare questa funzione).

- Quando selezioni una singola regione, assicurati di cliccare sulla sezione della forma d'onda del suo rettangolo. La 
striscia inferiore con il nome della regione viene utilizzata per un'azione diversa (vedi la sezione _Rifilatura delle 
regioni_ più avanti).
    
- Utilizzare il tasto **Canc** per eliminare le regioni selezionate.

- Le operazioni standard di copia (**Ctrl+C**), taglia (**Ctrl+X**) e incolla (**Ctrl+V**) funzionano anche con le 
regioni.

## Muovendo le regioni

Durante lo spostamento di una regione, sullo schermo apparirà un _codice temporale_ in numeri verdi. Questo codice 
temporale è il punto di inizio della regione sulla timeline. L'unità di misura di questo codice temporale è la stessa 
dell'unità di misura dell'orologio principale, che è possibile modificare facendo clic con il tasto destro del mouse 
sull'orologio e selezionando una nuova unità di misura (_Minuti:Secondi_, _Battute:Battiti_, ecc.).

È possibile spostare le regioni orizzontalmente (di lato) in un punto diverso della stessa traccia, oppure spostare la 
regione selezionata verticalmente (verso l'alto o verso il basso) in una traccia diversa.

Quando si seleziona un insieme di una o più regioni, è possibile spostare l'intero insieme trascinandolo con il mouse.

{{< callout type="info" >}}
Assicurati di selezionare la regione nella sezione della forma d'onda, perché selezionando l'area della barra del titolo
inferiore si attiva un'azione diversa (vedi _Rifilatura delle regioni_ di seguito).
{{< /callout >}}

## Duplicazione delle regioni

Oltre a **Ctrl+Clic+Trascina** e al copia/incolla standard, Ardour offre altri modi pratici per duplicare le regioni. 
Usa la modalità _mano_ (seleziona/sposta oggetti) per selezionare una o più regioni, quindi usa la funzione _Duplica_ 
per creare una o più copie (menu `Regione > Duplica`). Sono disponibili tre opzioni:

- _Duplica_ (scorciatoia **Alt+D**): crea una copia della regione selezionata sulla stessa traccia, immediatamente dopo
l'originale.

- _Replica_ (scorciatoia **Shift+D**): crea più copie della regione selezionata contemporaneamente (stessa traccia, 
in sequenza). È possibile specificare il numero di duplicazioni.

- _Riempi traccia_: crea tutte le copie della regione selezionata necessarie a riempire l'intera traccia, fino al 
marcatore _Fine_ sulla timeline.

Nella schermata seguente, le regioni sono state duplicate utilizzando i metodi sopra indicati.

{{< figure alt="Duplica" src="it/ardour8-region-duplicate.png" >}}

## Utilizzo dei punti di modifica

Quando si utilizzano i comandi standard copia/taglia/incolla, dove verranno incollate esattamente le regioni? La 
posizione esatta è determinata dal menu a tendina del punto di modifica.

{{< figure alt="Punto di Modifica" src="it/ardour8-edit-point-menu.png" >}}

Se _Mouse_ è selezionato come punto di modifica, la regione copiata verrà incollata nella posizione corrente del mouse.

Se _Testina_ è selezionato come punto di modifica, la regione copiata verrà incollata sulla linea rossa della testina 
nella stessa traccia in cui si trova la regione originale.

Infine, se _Marcatore_ è selezionato come punto di modifica, la regione copiata verrà incollata immediatamente dopo il 
_marcatore di posizione_ attualmente selezionato.

## Marcatori di posizione

È molto utile poter contrassegnare diverse posizioni in una sessione per poterle riutilizzare in seguito durante 
l'editing e il mixaggio. Ardour supporta diversi modi per farlo. Il metodo più comune è l'uso dei 
_marcatori di posizione_, che definiscono posizioni specifiche nel tempo.
 
È possibile aggiungere marcatori di posizione nella timeline facendo clic con il pulsante destro del mouse sulla barra 
_Marcatore di posizione_ e selezionando _Aggiungi_. Se la barra _Marcatore di posizione_ non è visibile, fare clic con 
il pulsante destro del mouse sulla timeline e selezionarla per renderla visibile. Gli indicatori di posizione possono 
anche essere selezionati con il mouse e spostati in nuove posizioni. Facendo clic con il pulsante destro del mouse su un
marcatore di posizione è possibile rinominarlo, oltre ad altre opzioni.

{{< figure alt="Marcatore di posizione" src="it/ardour8-location-marker.png" >}}

{{< callout type="info" >}}
Quando crei una nuova sessione, vengono aggiunti automaticamente due marcatori di posizione. Si tratta dei marcatori 
_inizio_ e _fine_ che vedi nella schermata sopra. Se non vedi l'indicatore _fine_, riduci lo zoom e lo troverai.
{{< /callout >}}

## Divisione delle regioni

_Dividere_ una regione significa semplicemente suddividere una singola regione in due regioni indipendenti. Ci sono due 
modi per farlo:

* È possibile utilizzare la modalità _forbice_ (scorciatoia **C**) per selezionare il punto in cui si desidera dividere 
il documento; oppure

* È possibile rimanere in modalità _mano_ e utilizzare la scorciatoia **S** (per "Split"). In quest'ultimo caso, il 
punto in cui una regione verrà divisa dipende dal punto di modifica attualmente selezionato. Se _Mouse_ è selezionato 
come punto di modifica corrente, selezionare una regione e posizionare il cursore nel punto in cui si desidera 
_dividere_, quindi digitare **S**" (come se si andasse al menu `Modifica > Dividi/Separa`).

{{< figure alt="Strumento forbice" src="it/ardour8-split-tool.png" >}}

Dopo la divisione, la regione singola originale diventa due regioni indipendenti, ciascuna con un nuovo nome, come 
nell'immagine sopra. Le due nuove regioni sono ora completamente indipendenti. È possibile spostarle e modificarle 
separatamente.

{{< figure alt="Dividi" src="it/ardour8-split-region-moved.png" >}}

Le regioni possono anche essere divise utilizzando la testina o un marcatore come punto di modifica.

Le regioni suddivise riceveranno un nome derivato dal nome originale della regione madre e questo sarà visibile 
nell'elenco delle regioni. Ad esempio, nell'immagine sopra sono presenti due regioni denominate _nord-drum-can_1.9_ e 
_nord-drum-can_1.10_, il che significa che sono state suddivise da una regione madre denominata "nord-drum-can" 
(non mostrata nell'immagine).

{{< callout type="info" >}}
La suddivisione delle regioni seguirà le impostazioni della griglia. Ad esempio, se è attiva una griglia impostata 
per le battute, la suddivisione avverrà ai confini delle battute. Se si seleziona _Nessuna griglia_, la suddivisione 
avverrà ovunque si trovi il punto di modifica, indipendentemente dalla griglia.
{{< /callout >}}

## Rifilature delle regioni

Se si sposta il cursore vicino al bordo sinistro o destro di una regione, si noterà che il puntatore assume la forma di 
una freccia. Clicca e trascina verso l'interno da entrambe le estremità della regione e questa verrà ridotta di 
conseguenza.
Questa operazione è chiamata _rifilatura_ della regione. Le regioni possono essere rifilate dall'inizio della regione 
(trascinando da sinistra a destra sul bordo) o dalla fine (trascinando da destra a sinistra).

Questa operazione non è distruttiva: nessun audio viene effettivamente eliminato. È come se si "nascondessero" quelle 
parti della regione che non si desiderano o non servono più. In seguito, è possibile "annullare il taglio" della regione
(ovvero, riportarla alle dimensioni originali), anche se è stata spostata o copiata su una nuova traccia.

{{< figure alt="Rifilatura" src="it/Ardour4_Trimming_Regions.gif" >}}

{{< callout type="info" >}}
Come la divisione, anche la rifilatura rispetta le impostazioni della griglia. Se non desideri che la rifilatura sia 
vincolata alla griglia, disattiva semplicemente la griglia (_Nessuna griglia_).
{{< /callout >}}

## Regioni eliminate

Appurato che Ardour non è distruttivo, le regioni eliminate dalle tracce non vengono rimosse completamente dalla 
sessione. È sempre possibile accedervi nuovamente dall'elenco delle regioni situato all'estrema destra della finestra 
_Editor_ (le regioni possono essere trascinate dall'elenco su qualsiasi traccia).

## Creazione di dissolvenze nelle regioni

La _dissolvenza_ è una variazione del volume di una regione, all'inizio o alla fine della stessa. Una dissolvenza 
all'inizio della regione è un chiamata _Dissolvenza in entrata_, mentre alla fine della regione è chiamata 
_Dissolvenza in uscita_. Ogni regione ha due piccole maniglie agli angoli superiori, che possono essere trascinate verso
l'interno da entrambi i bordi per creare una dissolvenza in entrata o in uscita. La schermata sottostante mostra una
dissolvenza in entrata(indicato dall'area ombreggiata).

{{< figure alt="Dissolvenza1" src="it/ardour8-fades-1.png" >}}

Infatti, ogni regione ha una dissolvenza in entrata e in uscita incorporata. Per impostazione predefinita, la 
dissolvenza della regione è molto breve e serve a evitare clic nelle transizioni all'inizio e alla fine della regione. 
Regolando la durata della dissolvenza delle regioni come mostrato sopra, è possibile ottenere una transizione più 
graduale.

Cliccando con il tasto destro del mouse su una delle dissolvenze (l'area ombreggiata), è possibile regolare anche la 
velocità della dissolvenza.

{{< figure alt="Opzioni dissolvenza" src="it/ardour8-fade-options.png" >}}

## Dissolvenza incrociata tra due regioni

Quando una regione sfuma mentre un'altra entra in dissolvenza, si parla di _dissolvenza incrociata_. Se le due regioni 
si trovano in tracce diverse, è possibile utilizzare il metodo descritto sopra con le maniglie di dissolvenza in entrata
e in uscita. La schermata seguente mostra un esempio.

{{< figure alt="Dissolvenza incrociata1" src="it/ardour8-crossfade-1.png" >}}

Tuttavia, se entrambe le regioni si trovano nella stessa traccia, è necessario sovrapporle per creare una dissolvenza 
incrociata. Quando le regioni si sovrappongono sulla stessa traccia, Ardour le tratta come *livelli*, ovvero una delle 
regioni viene considerata sovrapposta all'altra. La regola importante da comprendere è:

*La dissolvenza in entrata (o in uscita) della regione superiore rappresenta la dissolvenza incrociata tra le due 
regioni.*

Una volta compreso questo principio, è facile creare e controllare le dissolvenze incrociate tra le regioni. Ecco un 
esempio. Le due regioni separate visibili di seguito verranno sovrapposte per creare una dissolvenza incrociata.

{{< figure alt="Dissolvenza incrociata2" src="it/ardour8-crossfade-2.png" >}}

Si noti che non abbiamo aggiunto alcun dissolvenza in uscita alla prima regione, ma abbiamo aggiunto una dissolvenza in
entrata più lunga alla seconda regione. Quindi trasciniamo la seconda regione parzialmente sopra la prima:

{{< figure alt="Dissolvenza incrociata3" src="it/ardour8-crossfade-3.png" >}}

La dissolvenza in ingresso della seconda regione ora funziona come dissolvenza incrociata tra le due regioni. In altre 
parole, la prima regione svanirà in modo speculare mentre la seconda regione apparirà gradualmente.

Affinché ciò funzioni, però, dobbiamo assicurarci che la regione con la dissolvenza desiderata sia *in primo piano* nel
sistema di strati di Ardour. Per modificare la posizione degli starti delle regioni, seleziona una regione
e vai al menu `Regione > Strato`.

{{< figure alt="Menu Strato" src="it/ardour8-crossfade-4.png" >}}

La differenza potrebbe essere difficile da percepire se si utilizza uno dei suoni di percussioni molto brevi importati 
in precedenza. Per sentire davvero l'effetto, è necessario importare un paio di campioni più lunghi (ad esempio, un 
campione di rumore di pioggia e un altro di voce umana). Sovrapporre alcuni secondi dei campioni lunghi sulla stessa 
traccia. Sentirai la differenza quando sposti la seconda regione in basso (_Porta in fondo_) e poi di nuovo in alto 
(_Porta in cima_). Quando è in alto, sentiremo la dissolvenza incrociata desiderata. Quando è in basso, non sentiremo 
alcuna dissolvenza incrociata, ma solo un cambiamento brusco dalla prima alla seconda regione (supponendo che la prima 
regione non abbia una dissolvenza in uscita specificata, come negli screenshot sopra).

## Utilizzo delle impostazioni della griglia

Sperimenta con l'impostazione _Modo griglia_, come descritto nel capitolo _Impostazione della timeline_, per ottenere 
diversi tipi di quantizzazione, ovvero per limitare i confini di ciascuna regione a determinati punti della griglia.
In questo caso, la griglia è stata attivata e impostata su _1/16_, per quantizzare le regioni in sedicesimi all'interno 
di ogni battuta. Potresti voler tagliare i punti finali di alcuni campioni, come discusso in precedenza, per adattarli 
alla struttura metrica che hai impostato.

{{< figure alt="Battito" src="it/ardour8-beat.png" >}}

## Continua

Nel prossimo capitolo esploreremo alcune altre cose che è possibile fare con le regioni.

Prossimo: [Ulteriori operazioni sulle regioni](../further-region-operations)
