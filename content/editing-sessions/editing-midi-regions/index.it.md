---
title: Modifica delle regioni MIDI
description: Come modificare le regioni MIDI in Ardour
weight: 10
cascade:
  type: docs
---

Quasi tutte le operazioni di editing MIDI avvengono nella modalità _modifica interna_ (scorciatoia **E**). La maggior 
parte del lavoro consiste nel modificare la posizione e la durata delle note, regolare la velocità e modificare 
l'automazione. Ardour fornisce strumenti per modificare queste impostazioni sia in modo interattivo che numerico.

Rivediamo quindi gli strumenti disponibili e poi facciamo un breve esercizio.

La maggior parte delle operazioni di editing presuppone che sia selezionata almeno una nota in una regione MIDI. 
Inizieremo con la selezione delle note.

## Selezione delle note

Esistono diversi modi per selezionare le note nella modalità _modifica interna_, dipende davvero da cosa si desidera 
fare.

Per selezionare una nota, basta cliccarci sopra una volta. Per aggiungere un'altra nota alla selezione, tieni premuto 
**Ctrl** e poi clicca su quella nota. Per togliere una nota dalla selezione, di nuovo, tieni premuto **Ctrl** e poi 
cliccaci sopra.

Se devi estendere una selezione esistente a un'altra nota e includere tutte le note intermedie, tieni premuto **Shift**,
quindi fai clic sulla nota a cui desideri estendere la selezione.

Per selezionare più note adiacenti, è possibile utilizzare la selezione con l'elastico. Spostare il puntatore del mouse 
su una parte vuota dell'area di lavoro vicina a quelle note, tenere premuto il tasto sinistro del mouse, quindi 
trascinare il mouse per "disegnare" un'area rettangolare. Tutte le note all'interno di quell'area saranno selezionate. 
Rilasciare il tasto del mouse per completare la selezione.

{{< figure src="it/rubberband-selection.png" alt="Selezione con elastico" >}}

Infine, se devi selezionare tutte le note, basta premere **Ctrl+A**.

Una volta selezionate più note, è possibile modificarle in blocco in vari modi.

## Modifica dell'inizio e della fine delle note

Per modificare l'inizio o la fine della nota, passa con il mouse su un bordo della nota finché non vedi cambiare l'icona
del puntatore. Quindi tieni premuto il tasto sinistro del mouse, trascina verso sinistra o destra per modificare, 
rilascia il tasto del mouse per confermare la modifica.

Le opzioni di allineamento si applicano qui, quando l'allineamento è abilitato. Inoltre, se vengono selezionate più note, 
tutte verranno ridotte o estese.

{{< figure src="it/drag-note-ends.png" alt="Trascina la nota fino alla fine" >}}

La quantizzazione consiste nell'aggiustare i tempi di inizio e fine delle note in modo che si allineino a una griglia 
scelta. È una cosa che probabilmente userai dopo la registrazione in tempo reale. Ardour offre una certa flessibilità 
nell'applicazione della quantizzazione: puoi allineare alla griglia solo gli inizi, solo le fini o entrambi.

Un altro comando che regola efficacemente la durata delle note è _lega_. Quando si hanno due note che iniziano in 
posizioni diverse sulla timeline, _lega_ regola la fine della nota che inizia prima in modo che finisca esattamente 
dove inizia la seconda nota. Ciò potrebbe significare espandere o ridurre la durata della nota precedente:

{{< figure src="it/legatize.png" alt="lega" >}}

Come puoi vedere, la prima nota è stata allungata per unirsi alla seconda, la seconda è stata accorciata per unirsi alla
terza e la terza è stata allungata per unirsi alla quarta.

## Spostamento e trasposizione delle note

È possibile spostare e/o trasporre le note selezionate semplicemente premendo i tasti freccia sulla tastiera. In 
alternativa, è possibile posizionare il cursore al centro di uno dei nodi selezionati, premere il tasto sinistro del 
mouse, tenerlo premuto e quindi trascinare la selezione a sinistra/destra o su/giù (o entrambi).

È anche possibile trasporre di un determinato numero di ottave e semitoni in una sola volta. Fare clic con il tasto 
sinistro del mouse sulla regione in cui sono selezionate alcune note, scegliere _Trasponi..._. Quindi specificare il 
numero di ottave e semitoni da trasporre.

{{< figure src="it/transpose.png" alt="Trasporre note MIDI" >}}

## Editing velocity

Ardour uses two ways to represent a note's velocity: through color coding and
through a 2D chart.

{{< figure src="en/velocities.png" alt="Velocities" >}}

The paler the note and the shorter the dark line inside the note, the lower the
velocity. A deep red note and the dark line going through the entire note mean
the velocity is at (on near) its maximum value.

To quickly change a note's velocity, hover its middle on the canvas, then start
scrolling the mouse wheel up and down to change the velocity value. When
multiple notes are selected, each will receive the same amount of adjustment. So
you can select, let's say, 3 notes at 25, 50, and 100 velocity values
respectively, increment each one by 20, and end up with notes that have 45, 70,
and 120 for velocities.

{{< figure src="en/velocity-tooltip.png" alt="Velocity tooltip" >}}

A simple way to numerically change velocity (as well as MIDI channel, pitch, and
position) is to use the note's properties dialog. Right-click on a note or
multiple notes, then select _Edit…_.

![Editing note properties](en/note-properties.png?width=45vw)

If multiple notes have been selected, you can mass-change them to the same
value. For that enable the _Set selected notes to this velocity_ option before
applying changes.


## Editing example start to end

Let's have a look at this quick real-time performance capture.

{{< figure src="en/example-original.png" alt="" >}}

Even without listening to it, a few things stand out:

- wrong start times;
- wrong durations;
- velocity all over the place.

Let's fix it and start with positions and durations.

1. Press **E** to switch to the _Internal Edit_ mode.
Rubberband-select all visible notes.

{{< figure src="en/example-select-all.png" alt="" >}}

2. Right-click and select _Quantize_ (or just press **Q**). Use _1/8 Note_
or _Main Grid_ for note starts and ends, because in this case, it's the
same thing.

{{< figure src="en/example-quantize-dialog.png" alt="" >}}

This is already much better:

{{< figure src="en/example-quantize-result.png" alt="" >}}

But there are some overlapping notes.

3. Right-click and select _Legatize_.

{{< figure src="en/example-legatize.png" alt="" >}}

4. Press **Arrow Left** key just once to shift all selected notes by one grid
unit (it's _1/8 Note_) so that they start right at the beginning of the bar:

{{< figure src="en/example-shift-left.png" alt="" >}}

Positions are all fine now. But there's more.

5. It's time to cleanup velocity. Select all notes but the first one in each of
the two bars. You can do that by pressing **Ctrl+A**, then press and hold
**Ctrl** and click on the first note in each bars to deselect them. Or you can
rubber-band select the first portion (sans the first note), then press and hold
**Shift** and add the second portion (sans the first note in that bar as well).

{{< figure src="en/example-select-all-but-firsts.png" alt="" >}}

6. Right-click, select _Transform_. We need to set this to more or less the same
lower velocity, let's say, 60. So we set Velocity, we set it to an exact value,
and we use 60:

{{< figure src="en/example-transform-all-60.png" alt="" >}}

This, again, much better:

{{< figure src="en/example-now-all-60.png" alt="" >}}

But it's going to sound a little too robotic if we keep it that way.

7. Let's call the _Transform_ dialog again and add a tiny bit of random
variation:

{{< figure src="en/example-transform-variation-56-to-64.png" alt="" >}}

Given the small range of the variation, the difference won't be very visible.
But if you hover individual notes, you'll see that notes' velocities are now
somewhere between 56 and 64.

8. Finally, click the first note of the first bar and use mouse wheel scrolling
to set its velocity to 82, then repeat for the first note of the second bar. You
will now have a regular velocity pattern where the first note of each bar sounds
louder than the rest of the notes in each bar.

{{< figure src="en/example-regular-velocity-pattern.png" alt="" >}}

## Continuing

This was the last chapter of the _Editing Regions_ section. Next we go into
_Mixing_.

Next: [PERFORMING LIVE](../../performing-live/)

<!-- ## Editing and creating automation -->
