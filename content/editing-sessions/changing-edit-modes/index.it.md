---
title: Cambiare la modalità di modifica
description: Modalità di modifica per le regioni in Ardour
weight: 7
cascade:
  type: docs
---

Abbiamo già imparato qualcosa sulla modalità _mano_ (selezionare/spostare oggetti) e sulla modalità _intervallo_. In 
questo capitolo vedremo una panoramica di tutte le modalità di _modifica_ e _cursore_ disponibili nella finestra _Edit_.

{{< figure alt="Modalità di editing" src="it/ardour8-edit-modes.png" >}}

## Modalità di modifica

Questi controlli definiscono il comportamento dello spazio di lavoro principale e le diverse funzioni del cursore.

Il menu a tendina della modalità _modifica_ contiene tre opzioni:

**Libero**
: Questa è la modalità standard. Consente di trascinare liberamente le regioni in orizzontale (all'interno della stessa 
traccia) e in verticale (tra le tracce).

**Scarto**
: Sposta automaticamente le regioni quando si taglia o si sposta una delle regioni. Ad esempio, se si taglia una parte 
di un'intervista audio che non è interessante, Ardour sposterà tutte le regioni in tutte le tracce verso sinistra in 
modo che non ci sia silenzio dove prima c'era il contenuto.

**Bloccato**
: Indipendentemente da come modifichi una regione, con questa modalità attivata, il contenuto della regione rimarrà 
sempre nella stessa posizione. Puoi solo spostare la regione verso l'alto o verso il basso tra le tracce, ma non a 
sinistra o a destra.

In questo tutorial utilizzeremo solo la modalità di modifica _Libero_.

## Punto di modifica

Il punto di modifica definisce dove avvengono le varie operazioni di modifica. Come quando ad esempio usiamo il 
taglio o la divisione...

**Testina**
: Le regioni saranno divise nella posizione del cursore di riproduzione.

**Marcatore**
: Le regioni saranno suddivise all'ultimo indicatore che si trova all'interno dell'intervallo della regione selezionata.

**Mouse**
: La regione selezionata verrà divisa esattamente sotto il puntatore del mouse.

## Modalità cursore

### Mano

{{< figure alt="G" src="it/ardour8-grab-edit-mode.png" >}}

Questa modalità cursore (scorciatoia **G**) consente di selezionare o spostare oggetti quali regioni e punti di 
interruzione (in una curva di automazione). Quando è selezionata questa modalità cursore, il puntatore del cursore 
assumerà l'aspetto di una piccola icona a forma di mano.

### Intervallo

{{< figure alt="R" src="it/ardour8-range-edit-mode.png" >}}

Questa modalità cursore (scorciatoia **R**) consente di cliccare e trascinare per definire o ridimensionare gli 
intervalli di tempo. Quando questa modalità cursore è selezionata, il puntatore del cursore apparirà come una linea 
verticale. Gli intervalli di tempo possono essere selezionati su una o più tracce, a seconda della selezione.

## Intelligente

{{< figure alt="3" src="it/ardour8-smart-mode.png" >}}

Quando questa modalità è abilitata, a seconda della posizione esatta del puntatore del mouse sopra la regione, Ardour 
fornirà funzioni di selezione (ad esempio, selezione e riposizionamento di una regione) o funzioni di intervallo 
(selezione di un intervallo).

### Forbice

{{< figure alt="C" src="it/ardour8-cut-edit-mode.png" >}}

Utilizza questa modalità cursore (scorciatoia **C**) per dividere le regioni in regioni più piccole. Il cursore assume 
la forma di forbici. Ciò consente di puntare e fare clic su una regione per dividerla in corrispondenza del cursore.

{{< callout type="info" >}}
È possibile tagliare le regioni anche direttamente dalla modalità _mano_ (a volte questo metodo può essere più pratico).
Senza uscire dalla modalità _mano_, è sufficiente posizionare il mouse nel punto desiderato della regione da tagliare e 
premere il tasto di scelta rapida **S** (per "split"). Importante: il punto di modifica (a sinistra della barra degli 
strumenti di _editing_) deve essere impostato su _Mouse_.
{{< /callout >}}

### Elastico (Allunga/Riduci)

{{< figure alt="T" src="it/ardour8-stretch-shrink-edit-mode.png" >}}

Questa modalità cursore (scorciatoia **T**) consente di trascinare e ridimensionare la durata di un'intera regione senza
modificare l'intonazione. Questa operazione è talvolta denominata "time stretching", da cui la scorciatoia **T**. Per 
ulteriori dettagli, consultare il capitolo _Allungamento e accorciamento delle regioni_. Quando è selezionata questa 
modalità cursore, il puntatore del cursore assumerà l'aspetto di una freccia diagonale.

### Griglia

{{< figure alt="D" src="it/ardour8-grid-mode.png" >}}

Questa modalità (scorciatoia **Y**) consente di modificare il tempo per adattarlo alle fluttuazioni di una sessione live
registrata come traccia audio. In questo modo la traccia audio diventerà il riferimento e le regioni MIDI create sulla 
base di questo tempo si sincronizzeranno perfettamente con l'audio originale. 

Cliccando sopra una linea di misura si inserisce un nuovo indicatore di tempo e trascinandolo immediatamente a sinistra 
o a destra si aumenta/diminuisce il suo valore.

Cliccando e trascinando tra le linee di misura a sinistra o a destra si crea una "rampa di tempo", ovvero una variazione 
graduale del tempo tra due indicatori di tempo.

### Disegno

{{< figure alt="D" src="it/ardour8-draw-edit-mode.png" >}}

Questa modalità (scorciatoia **D**) ha 4 casi d'uso:

1. Disegnare nuovi punti di automazione (l'automazione sarà discussa in dettaglio nel capitolo 
[Utilizzo dell'automazione](../../mixing-sessions/using-automation/)). 
2. Disegnare nuove regioni MIDI. 
3. Disegnare nuove note MIDI nelle regioni MIDI. 
4. Modificare le note MIDI e i punti di automazione esistenti quando una regione è sufficientemente ingrandita.

Se lo zoom non è sufficiente, è facile creare una nuova nota MIDI o un nuovo punto di automazione che non ti servono. 
Se questo diventa un problema, dovresti usare la modalità successiva che ti permette solo di modificare i punti e le 
note esistenti, senza crearne di nuovi.

Per disegnare note MIDI, la barra degli strumenti dispone inoltre di controlli per la lunghezza predefinita delle note, 
il canale MIDI e la velocità.

### Modifica interna

{{< figure alt="E" src="it/ardour8-internal-edit-mode.png" >}}

Utilizza questa modalità (scorciatoia **E**) per modificare i punti di automazione o le note MIDI esistenti.

Per i punti di automazione, il cursore assume la forma di una mano e si trasforma in una piccola croce quando si trova 
sopra un punto esistente. Fare clic, tenere premuto e trascinare per spostare i punti.

Per le note MIDI, il cursore appare come una mano con sopra una nota da semiminima quando si passa con il mouse sopra il
centro della nota. Ciò consente di selezionare una nota e spostarla. Passando con il mouse sul bordo sinistro o destro 
di una nota, il cursore cambia e consente di regolare la posizione iniziale e finale (e quindi la durata) di una 
nota.

Sia per i punti di automazione che per le note MIDI, è possibile premere **Ctrl** e fare clic su più elementi per 
aggiungerli a una selezione, quindi spostare più note o punti contemporaneamente.

{{< figure src="it/ardour7-internal-edit-mode-multiple-points.png" alt="Spostamento di più punti di automazione" >}}

Per le note MIDI in particolare, è anche possibile utilizzare la selezione con l'elastico: posizionare il cursore in un 
punto qualsiasi al di fuori delle note esistenti (il cursore perderà il simbolo della nota da un quarto), quindi premere
il tasto sinistro del mouse e iniziare a trascinare. Apparirà un riquadro di selezione. Tutte le note che tocca saranno 
selezionate.

{{< figure src="it/ardour7-internal-edit-mode-rubberband-selection.png" alt="Selezione delle note con l'elastico" >}}

## Continua

Nel capitolo seguente vedremo come prendere le regioni che abbiamo modificato e creare sezioni in loop da esse.

Successivo: [Creare sezioni in loop](../creating-looped-sections)
