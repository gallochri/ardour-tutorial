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

## Cambia intonazione

La funzione _Cambia intonazione_ (**Alt+8**) modifica l'intonazione di una regione senza alterarne la durata. La 
funzione applica un algoritmo di modifica dell'intonazione per creare una nuova clip audio basata sulla clip sorgente.

La finestra _Cambia intonazione_ consente all'utente di specificare l'entità e la direzione della trasposizione 
desiderata. La finestra include un'opzione denominata _Preserva timbro_. Quando si effettuano trasposizioni di entità 
rilevante, l'opzione "preserva timbro" può fornire risultati leggermente più naturali, in particolare se utilizzata su 
materiale vocale.

{{< figure alt="Cambia intonazione" src="it/ardour8-pitch-shift-window.png" >}}

## Normalizza

La funzione _Normalizza_ (scorciatoia **Alt+3**) aumenta in modo non distruttivo il livello della regione selezionata in
modo che i _picchi_ siano pari o inferiori a 0 dB. Quando si normalizza a 0,0, la regione avrà il volume massimo 
possibile evitando il clipping.  A volte può essere utile normalizzare una regione a un valore inferiore a 0, ad esempio
-1,0, -3,0 o -6,0 decibel, in modo che non diventi troppo forte.

{{< figure alt="Normalizza" src="it/ardour8-normalize-window.png" >}}

Altre due operazioni utili per le regioni sono _Aumenta guadagno_ (**Alt+6**) e _Riduci guadagno_ (**Alt+7**), che 
aumentano o diminuiscono il guadagno di 1dB. Provale!

## Inverti

La funzione _Inverti_ (**Alt+4**) inverte la regione audio selezionata, effettuando la riproduzione al contrario. 
L'inversione di una regione crea un nuovo file audio "dietro le quinte".

## Operazioni su due o più intervalli selezionati

Se viene selezionata più di una regione, l'operazione verrà applicata a tutte (ad esempio, _Normalizza_, _Inverti_, 
ecc.).

### Combina

Alcune operazioni dal menu contestuale saranno disponibili solo quando sono selezionate due o più regioni. Ad esempio, 
diamo un'occhiata alla funzione _Combina_, nel sotto-menu _Modifica_. Per prima cosa selezioniamo due regioni adiacenti:

{{< figure alt="Combina 1" src="it/ardour8-region-combine-1.png" >}}

Quindi selezioniamo _Combina_ dal menu contestuale del tasto destro del mouse o dal menu principale di Ardour 
`Regione > Modifica > Combina`:

{{< figure alt="Combina 2" src="en/ardour8-region-combine-2.png" >}}

Le regioni selezionate vengono unite in un'unica regione. Ciò è particolarmente utile quando si è individuata una 
sequenza esatta di regioni che funziona esattamente come desiderato e si desidera copiare e/o spostare l'intera sequenza
come gruppo.

Si noti che alla regione combinata risultante è stata aggiunta la parola "compound" al nome.

{{< figure alt="Combina 3" src="it/ardour8-region-combine-3.png" >}} 

## Continua

Nel capitolo seguente impareremo qualcosa in più sui potenti strumenti messi a disposizione da Ardour modificando le 
**modalità di editing**.

Successivo: [Cambiare la modalità di modifica](../changing-edit-modes)
