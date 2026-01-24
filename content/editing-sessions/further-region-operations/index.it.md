---
title: Ulteriori operazioni sulle regioni
description: Cambio dell'intonazione, normalizzazione e altre operazioni sulle regioni in Ardour
weight: 6
cascade:
  type: docs
---

In questa sezione imparerai alcune altre cose che puoi fare con le regioni.

Cliccando con il tasto destro su una regione selezionata si apre un menu contestuale. La prima voce del menu 
(contrassegnata dal nome della regione) contiene un ampio sotto-menu. Tutte queste operazioni sono disponibili anche dal
menu principale *Regione* di Ardour.

Questa sezione descrive alcune delle operazioni più comunemente utilizzate accessibili da questi menu.

{{< figure alt="Menu regione" src="it/ardour8-region-menu.png" >}}

**Riproduci**
: Riproduci dall'inizio alla fine di quella regione (scorciatoia **H**).

**Etichetta**
: Assegna a una regione una etichetta significativa, ad esempio "Buona", che aiuti a distinguerla dalle altre 
nell'elenco _Regioni_.

**Ciclo**
: Imposta l'intervallo di ripetizione in modo che corrisponda alla durata di quella regione e avvia immediatamente la 
ripetizione.

**Rinomina**
: Cambia il nome della regione selezionata.

**Proprietà**
: Molte informazioni sulla regione, oltre alla possibilità di modificarne il guadagno.

**Posizione**
: Tra le altre opzioni, in questo sotto-menu troverai la casella di selezione _Blocca_: blocca la regione in modo che 
non possa essere spostata o tagliata. Tuttavia, può ancora essere divisa e le regioni risultanti saranno sbloccate.

**Modifica**
: Questo sotto-menu contiene strumenti utili come _Cambia intonazione_ (**Alt+8**) e _Inverti_ (**Alt+4**). 
_Cambia intonazione_ altera l'intonazione di una regione senza modificarne la durata. _Inverti_ riproduce la regione al
contrario.

**Guadagno**
: Dispone di opzioni utili quali _Muto_ (**Alt+1**), _Normalizza_ (**Alt+3**), _Aumenta guadagno_ (**Alt+6**) e 
_riduci guadagno_ (**Alt+7**).

**Duplica**
: Include _Duplica_ (scorciatoia **Alt+D**), _Replica_ e _Riempi traccia_. Queste funzioni sono state spiegate in 
dettaglio nel capitolo [lavorare con le regioni](../working-with-regions).

**Analisi potenza**
: Stima il volume di una regione in LUFS, nonché i valori _Picco_ e _Picco reale_.

**Analisi spettrale**
: Finestra che mostra il contenuto di frequenza complessivo della regione.

Sentiti libero di esplorare da solo gli altri sotto-menu non menzionati sopra. Molti di essi rispecchiano le opzioni che
trovi nel menu *Regione* di Ardour. Di seguito approfondiamo alcune delle funzioni più utili.

## Pitch Shifting

The _Pitch Shift_ (**Alt+8**) function alters the pitch of a region without 
changing its duration. The function applies a pitch-shifting algorithm to
create a new audio clip based on the source clip.

The _Pitch Shift_ window allows the user to specify the amount and direction of
transposition desired. The window includes a _Preserve Formants_ option. When
pitch shifting by large amounts, the preserve formants option can give results
that sound slightly more natural, particularly when used on vocal material.

![Pitch Shift](en/ardour7-pitch-shift-window.png?height=30vh)

## Normalize

The _Normalize_ function (**Alt+3** shortcut) non-destructively boosts the level
of the  selected region so that the _peaks_ are at 0 dB or less. When
normalizing  to 0.0, the region will be as loud as possible while avoiding
clipping.  Sometimes you may find useful to normalize a region to a value less
than 0,  such as -1.0, -3.0, or -6.0 decibels, so it doesn't become too loud. 

![Normalize](en/ardour7-normalize-window.png?width=20vw)

Two other useful gain operations for regions are _Boost Gain_ (**Alt+6**) and
_Cut Gain_ (**Alt+7**), both incrementing gain by 1dB upwards or downwards.
Be sure to try them out.

## Reverse

The _Reverse_ (**Alt+4**) function reverses the selected region of audio, in 
effect causing it to play backwards. Reversing a region creates a new audio
file "behind the scenes".

## Operations On Two Or More Selected Ranges

If more than one range is selected, the operation will apply to all of them (for
example, _Normalize_, _Reverse_, etc.)

### Combine

Some operations from the context menu will only become available when two or
more regions are selected. For example, let's take a look at the _Combine_
function, under the sub-menu _Edit_. First we select two adjacent regions:

{{< figure alt="combine" src="en/ardour7-region-combine-1.png" >}}

Then we choose _Combine_ from the right-click context menu, or from Ardour's
main menu `Region > Edit > Combine`: 

{{< figure alt="combine 2" src="en/ardour7-region-combine-2.png" >}}

As a result, the selected regions are combined into one. This is particulary
useful when you have found an exact sequence of regions that works just as you
want, and then you would like to copy and/or move the whole sequence as group.

Notice that the resulting combined region has the word "compound" attached to
its name. 

{{< figure alt="combine 3" src="en/ardour7-region-combine-3.png" >}} 

## Continuing

In the following chapter, we will learn a bit more about the powerful
tools Ardour has available by changing **Edit Modes**.

Next: [CHANGING EDIT MODES](../changing-edit-modes)
