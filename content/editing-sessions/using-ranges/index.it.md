---
title: Utilizzo degli intervalli
description: Come creare e modificare gli intervalli in Ardour
weight: 4
cascade:
  type: docs
---

Un _intervallo_ è una selezione della timeline che può includere una o più tracce. Ha molti usi, come selezionare una 
porzione di dati audio/MIDI per tagliarla.

{{< figure src="it/ardour8-range-example.png" alt="Esempio di intervallo" >}}

## Creazione di intervalli

Esistono due modi comuni per creare un intervallo:

1. È possibile farlo con lo strumento _Mano_ (scorciatoia **G**) quando è abilitata la modalità _Intelligente_. In tal 
caso, è necessario posizionare il puntatore del mouse al centro di una traccia in verticale per iniziare a selezionare 
i dati, anziché selezionare e spostare una regione. Il puntatore del mouse che appare come una linea verticale indica 
che è possibile iniziare la selezione.

2. È anche possibile utilizzare lo strumento dedicato _Intervallo_ (scorciatoia **R**). In questo caso, è sufficiente 
fare clic e trascinare in un punto qualsiasi dell'area di lavoro per avviare la selezione.

È possibile selezionare i dati di più tracce contemporaneamente, come mostrato nella schermata sopra. Per farlo, basta 
trascinare il puntatore del mouse verso l'alto o verso il basso attraversando il confine tra le tracce.

Quando la _Lista dell'Editor_ è disponibile, è possibile visualizzare le proprietà dell'intervallo nella parte 
inferiore: i tempi di inizio/fine dell'intervallo e la sua durata. Quando viene creato un intervallo, la scheda 
_Tracks & Busses_ selezionerà anche le tracce che l'intervallo attraversa.

{{< figure src="it/ardour8-range-properties.png" alt="Proprietà intervallo" >}}

Può essere utile creare intervalli che si allineino con i bordi delle regioni sulla timeline. Per farlo, abilita 
l'opzione _Allineamento_ nella barra degli strumenti e seleziona _Nessuna griglia_ nell'elenco a discesa accanto ad essa.

{{< figure src="it/ardour8-snap-to-region-boundaries.png" alt="Aggancia ai confini della regione" >}}

## Modifica intervalli

Una volta creato un intervallo, puoi facilmente modificarne le posizioni iniziale e finale passando con il puntatore del
mouse sui confini dell'intervallo, selezionandoli e trascinandoli verso sinistra o verso destra.

{{< figure src="it/ardour7-editing-ranges.gif" alt="Modifica intervalli" >}}

Se hai dimenticato di includere una traccia in un intervallo, non è necessario ripetere la selezione dell'intervallo. 
Basta tenere premuto il tasto **Ctrl** e fare clic sull'intestazione della traccia nell'area di lavoro. In alternativa, 
tieni premuto **Ctrl** e fai clic sul nome della traccia nella scheda _Tracce e bus_ della _Lista dell'editor_.

{{< figure src="it/ardour7-adding-track-to-range.gif" alt="Aggiunta di traccia all'intervallo" >}}

## Riproduzione di intervalli in loop

Tornando al nostro esempio di passaggio ritmico, vorremo ascoltare il passaggio che stiamo componendo, magari in loop, 
mentre spostiamo i campioni. Per farlo, dobbiamo creare un intervallo di ascolto nella nostra sessione, in
modo da poter tornare esattamente a questo punto più e più volte.

{{< figure src="it/ardour8-loop-range-menu-command.png" alt="Intervallo di loop nel menu contestuale" >}}

Se necessario, ridurre lo zoom (**-**) per visualizzare le barre complete nella timeline. Utilizzare lo strumento 
_Intervallo_ per selezionare un'intera barra, quindi fare clic con il pulsante destro del mouse all'interno di un 
intervallo e scegliere uno dei due comandi:

1. _Riproduci l'intervallo_ (nella schermata sopra) per creare un loop e avviarne immediatamente la riproduzione.

2. _Ciclo sull'intervallo_ per creare solo indicatori di loop senza riproduzione immediata.

{{< figure src="it/ardour8-looped-range-playback.png" alt="Looped range playback" >}}

Finché sono presenti i marcatori di loop, è possibile riprodurre quella parte della timeline in loop ogni volta che lo 
si desidera (nell'immagine sopra). Per farlo, fare clic sul pulsante **Riproduci intervallo di ciclo** nella barra degli 
strumenti _Trasporto_ oppure premere il tasto di scelta rapida **L**.

{{< figure src="it/ardour8-play-loop-range-button.png" alt="Pulsante Intervallo loop in Trasporto" >}}

È anche possibile modificare la posizione dei marcatori di loop durante la riproduzione dell'intervallo in loop. Basta
selezionare un marcatore e trascinarlo verso sinistra o verso destra.

## Ulteriori opzioni di modifica degli intervalli

Ci sono altre operazioni che puoi fare sugli intervalli, tutte disponibili nel menu che si apre cliccando con il tasto 
destro del mouse:

- _Separa_ taglierà le regioni originali ai confini dell'intervallo. 
- _Duplica intervallo_ creerà una copia dell'intervallo e la posizionerà a partire dal confine destro dell'intervallo. 
Tutti i dati esistenti verranno sovrapposti, quindi potrai comunque accedervi. 
- _Ritaglia regione in base all'intervallo_ ritaglierà le regioni interessate all'estensione dell'intervallo.

È anche possibile controllare il volume e le caratteristiche spettrali dei dati in un intervallo o esportare solo i dati
all'interno di un intervallo anziché l'intera sessione (vedere 
[questo capitolo](../../exporting-sessions/exporting-a-range/) per ulteriori informazioni sull'esportazione di 
intervalli).

## Continua

Nel prossimo capitolo impareremo a lavorare con le regioni per comporre un ritmo con questi campioni.

Successivo: [Lavorare con le regioni](../working-with-regions)
