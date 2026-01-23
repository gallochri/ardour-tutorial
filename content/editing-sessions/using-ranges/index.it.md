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

## Editing ranges

Once you created a range, you can easily tweak it's start and end positions by
hovering range boundaries with the mouse pointer, grabbing them and dragging to
the left or to the right.

{{< figure src="it/ardour7-editing-ranges.gif" alt="Modifica intervalli" >}}

If you forgot to include a track into a range, you don't need to redo the range
selection. Just hold **Ctrl** button and click on the track's header on the
canvas. Alternatively, hold **Ctrl** and click on track's name in the _Tracks &
Busses_ tab of the _Editor List_ dock.

{{< figure src="it/ardour7-adding-track-to-range.gif" alt="Aggiunta di traccia all'intervallo" >}}

## Playing back ranges in a loop

Returning to our rhythmic passage example, we will want to hear the passage we
are composing, perhaps as a loop, while we are moving the samples around. To do
that, we must create a range to listen to within our session, so that we can
return to exactly this point in the session again and again.

{{< figure src="it/ardour8-loop-range-menu-command.png" alt="Intervallo di loop nel menu contestuale" >}}

Zoom out if needed (**-**) to see full bars in the timeline. Use the _Range_
tool to select an entire bar, then right-click inside a range and pick one of
the two commands:

1. _Loop Range_ (on the screenshot above) to create a loop and start playing it
immediately.

2. _Set loop from selection_ to only create loop markers without immediate
playback.

{{< figure src="it/ardour8-looped-range-playback.png" alt="Looped range playback" >}}

As long as loop markers are there, you can start playing back that portion of
the timeline in a loop whenever you like (on the screenshot above). To do that,
either click the **Play loop range** button in the _Transport_ toolbar or press
the **L** shortcut.

{{< figure src="it/ardour8-play-loop-range-button.png" alt="Pulsante Intervallo loop in Trasporto" >}}

You can also tweak the position of loop markers while playing the range in a
loop. Just grab a marker and drag it to the left or to the right.

## More editing options for ranges

There are more operations you can do on ranges, all available in the right-click
menu:

- _Separate_ will cut the original regions at range borders.
- _Duplicate_ will create one copy of the range and place it starting at the
right border of the range. Any existing data will be overlaid, so you can still
access it.
- _Crop Region To Range_ will trim affected regions to the extent of the range.

You can also inspect loudness and spectral characteristics of data in a range or
export just the data inside a range rather than the entire session (see [this
chapter](../../exporting-sessions/exporting-a-range/) for more info on exporting
ranges).

## Continuing

In the next step, we will learn about working with regions to compose a rhythm
with these samples.

Next: [WORKING WITH REGIONS](../working-with-regions)
