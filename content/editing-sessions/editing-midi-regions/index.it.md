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

## Modificare la dinamica

Ardour utilizza due modi per rappresentare la dinamica di una nota: tramite codifica a colori e tramite un grafico 2D.

{{< figure src="it/velocities.png" alt="Velocità" >}}

Più chiara è la nota e più corta è la linea scura al suo interno, minore è la dinamica. Una nota di colore rosso intenso
e una linea scura che attraversa l'intera nota indicano che la dinamica è (quasi) al suo valore massimo.

Per modificare rapidamente la dinamica di una nota, posizionare il cursore al centro della nota, quindi iniziare a 
far scorrere la rotellina del mouse verso l'alto e verso il basso per modificare il valore della dinamica. Quando sono 
selezionate più note, ciascuna riceverà la stessa regolazione. Quindi è possibile selezionare, ad esempio, 3 note con 
valori di dinamica rispettivamente pari a 25, 50 e 100, incrementare ciascuna di esse di 20 e ottenere note con dinamica
pari a 45, 70 e 120.

{{< figure src="it/velocity-tooltip.png" alt="Suggerimento sulla velocità" >}}

Un modo semplice per modificare numericamente la dinamica (così come il canale MIDI, l'intonazione e la posizione) è 
quello di utilizzare la finestra di dialogo delle proprietà della nota. Fare clic con il tasto destro del mouse su una o
più note, quindi selezionare _Modifica…_.

{{< figure src="it/note-properties.png" alt="Modifica delle proprietà della nota" >}}

Se sono state selezionate più note, è possibile modificarle in blocco assegnando loro lo stesso valore. A tal fine, 
abilitare l'opzione _Imposta le note selezionate su questa dinamica_ prima di applicare le modifiche.

## Esempio di modifica dall'inizio alla fine

Diamo un'occhiata a questa acquisizione in tempo reale.

{{< figure src="it/example-original.png" alt="" >}}

Anche senza ascoltarlo, alcune cose saltano all'occhio:

- tempo di partenza sbagliato; 
- durate errate; 
- velocità completamente sballata.

Risolviamo il problema e iniziamo con le posizioni e le durate.

1. Premere **E** per passare alla modalità _Modifica interna_. Selezionare tutte le note visibili con la selezione a 
elastico.

{{< figure src="it/example-select-all.png" alt="" >}}

2. Clicca con il tasto destro del mouse e seleziona _Quantizza_ (oppure premi semplicemente **Q**). Usa _1/8 di nota_ o 
_Griglia principale_ per l'inizio e la fine delle note, perché in questo caso è la stessa cosa.

{{< figure src="it/example-quantize-dialog.png" alt="" >}}

Questo è già molto meglio:

{{< figure src="it/example-quantize-result.png" alt="" >}}

Ma ci sono alcune note che si sovrappongono.

3. Clicca con il tasto destro del mouse e seleziona _Lega_.

{{< figure src="it/example-legatize.png" alt="" >}}

4. Premere una sola volta il tasto **Freccia sinistra** per spostare tutte le note selezionate di un'unità della griglia
(ovvero _1/8 di nota_) in modo che inizino proprio all'inizio della battuta:

{{< figure src="it/example-shift-left.png" alt="" >}}

Le posizioni ora sono tutte a posto. Ma c'è dell'altro.

5. È ora di ripulire la dinamica. Seleziona tutte le note tranne la prima in ciascuna delle due battute. Puoi farlo 
premendo **Ctrl+A**, quindi tenendo premuto **Ctrl** e cliccando sulla prima nota di ciascuna battuta per 
deselezionarle. Oppure puoi selezionare la prima porzione (esclusa la prima nota) con la selezione elastica, quindi 
tenere premuto **Shift** e aggiungere la seconda porzione (esclusa anche la prima nota di quella battuta).

{{< figure src="it/example-select-all-but-firsts.png" alt="" >}}

6. Clicca con il tasto destro del mouse e seleziona _Trasforma_. Dobbiamo impostare più o meno la stessa dinamica 
inferiore, diciamo 60. Quindi impostiamo la dinamica un valore esatto e utilizziamo 60:

{{< figure src="it/example-transform-all-60.png" alt="" >}}

Questo, ancora una volta, è molto meglio:

{{< figure src="it/example-now-all-60.png" alt="" >}}

Ma se lo lasciamo così, sembrerà un po' troppo robotico.

7. Richiamiamo nuovamente la finestra di dialogo _Transforma_ e aggiungere una piccola variazione casuale:

{{< figure src="it/example-transform-variation-56-to-64.png" alt="" >}}

Data la ridotta ampiezza della variazione, la differenza non sarà molto evidente. Tuttavia, passando con il mouse sulle 
singole note, si noterà che le dinamiche delle note ora sono comprese tra 56 e 64.

8. Infine, clicca sulla prima nota della prima battuta e usa la rotellina del mouse per impostare la sua velocità a 82, 
poi ripeti l'operazione per la prima nota della seconda battuta. Ora avrai un pattern di velocità regolare in cui la 
prima nota di ogni battuta suona più forte rispetto alle altre note della stessa battuta.

{{< figure src="it/example-regular-velocity-pattern.png" alt="" >}}

## Continua

Questo era l'ultimo capitolo della sezione _Sessioni di editing_. Passiamo ora alla sezione _Esibirsi dal vivo_.

Successivo: [Esibirsi dal vivo](../../performing-live/)

<!-- ## Editing and creating automation -->
