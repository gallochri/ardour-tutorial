---
title: Creare sezioni in loop
description: Creazione e combinazione di regioni duplicate in Ardour
weight: 8
cascade:
  type: docs
---

È possibile ripetere facilmente sezioni audio nella sessione Ardour.

Qui prendiamo il breve passaggio ritmico che abbiamo creato in _Lavorare con le regioni_ e lo duplichiamo per creare un 
loop.

Prima di duplicare il passaggio, è consigliabile combinare le singole regioni della stessa traccia in un'unica regione: 
in questo modo è più facile spostarle e si evita, ad esempio, di spostare accidentalmente un singolo hihat fuori posto. 
Ci sono due modi per farlo: _Combina regioni_ (consente di "separarle" in un secondo momento) e _Consolida intervallo_ 
("lo rende definitivo", non consente di separarle in un secondo momento).

Se hai ancora intenzione di apportare modifiche al ritmo (aggiungendo, rimuovendo o spostando singole regioni), potrebbe
essere preferibile utilizzare l'opzione _Combina_ regioni. Se ti piace la sequenza così com'è e non desideri o non ti 
interessa avere la possibilità di separarle in un secondo momento, utilizza l'opzione _Consolida intervallo_.

## Combina regioni

Basta selezionare tutte le regioni che desideri combinare:

{{< figure alt="combina" src="it/ardour8-combine-regions-1.png" >}}

Quindi vai al menu `Regione > Modifica > Combina` (oppure fai clic con il tasto destro sulle regioni selezionate e trova
la stessa opzione nel menu contestuale, come mostrato di seguito):

{{< figure alt="combine2" src="it/ardour8-combine-regions-2.png" >}} 

Le regioni combinate avranno questo aspetto (si noti la parola "compound" aggiunta al nome):

{{< figure alt="combine3" src="it/ardour8-combine-regions-3.png" >}} 

Se in futuro dovessi separarli nuovamente, seleziona semplicemente l'area composta, vai allo stesso menu e scegli 
l'opzione _Scombina_.

## Consolidare l'intervallo

Un'alternativa più permanente a _Combina_ è l'uso di _Consolida_. Una volta disposte le regioni in un unico "ciclo loop"
e una volta soddisfatti del suono, creare un _intervallo_ con tutte le regioni che compongono il loop.

Per prima cosa, assicurati che tutte le tracce utilizzate nel loop siano selezionate. Le tracce non selezionate sono di
colore grigio, mentre quelle selezionate sono colorate (a seconda del tema dell'interfaccia utente). Se una delle tracce
utilizzate non è selezionata, tieni premuto il tasto **Shift** mentre clicchi su di essa per aggiungerla al gruppo 
selezionato. Infine, utilizza lo strumento Intervallo per selezionare l'intero loop.

Ancora una volta, l'impostazione _griglia_ ti aiuterà a impostare con precisione l'intervallo tra i punti iniziale e 
finale della barra metrica. Una volta selezionato l'intero loop, fai clic con il pulsante destro del mouse 
sull'intervallo e seleziona _Consolida_. Se desideri includere eventuali effetti di automazione o plugin aggiunti al 
loop, seleziona _Consolida (con elaborazione)_.

{{< figure alt="consolida" src="it/ardour8-consolidate-range-1.png" >}} 

When the range is consolidated, new regions will appear in each track, each
containing all the repetitions of the samples which you set up in the previous
steps. Remember, once the range is consolidated, there is no way to undo this
operation. In any case, if you find that you need to alter the rhythm in any
way, you can always retrieve the original individual samples from the region
List and rebuild the pattern with them.

{{< figure alt="consolidate2" src="en/ardour7-consolidate-range-2.png" >}}

## Duplicating the Range

After you have merged individual regions that form your pattern (using
either _Combine_ or _Consolidate_), it's time to duplicate the
pattern to make it loop for several bars.

The _Multi-Duplicate_ feature (seen in the [Working with
regions](../working-with-regions/) chapter) is a good way to accomplish this.
Go back to _Grab_ mode (**G**) , select all regions,  and hit
**Shift+D**. Choose how many times you want to duplicate the pattern (for
example, 16). After duplication our session looks something like this:

{{< figure alt="multi-dup" src="en/ardour7-multi-duplicate.png" >}} 

Just for review, other options you could have used for duplication are:

- The _Fill Track_ command from menu `Region > Duplicate > Fill Track`. This
would fill the entire track with copies of the selected regions, all the way up
to the _End Marker_. 

- The single _Duplicate_ command from the same menu (**Alt+D**). This
lets you make a single copy at a time. 

- The single duplicate action with **Ctrl+Click** on the region + _Drag a copy_.

## Continuing

In the next tutorial we will learn about stretching/shrinking regions that are
longer or shorter than one bar in order to fit the rhythm of our passage.

Next: [STRETCHING/SHRINKING REGIONS](../stretching-shrinking-regions)
