---
title: Arrangiamento delle tracce
description: Come organizzare le regioni sulla timeline in Ardour
weight: 2
cascade:
  type: docs
---

Nei capitoli seguenti useremo Ardour per creare un breve passaggio ritmico utilizzando diversi campioni di batteria.

Continueremo a lavorare su questo passaggio nei tutorial successivi, come _Lavorare con le regioni_ e 
_Creare sezioni in loop_. Partiamo dal presupposto che abbiate già letto i capitoli della sezione _Per Iniziare_ e che 
abbiate familiarità con _Importazione di audio_, _Tracce_ e _Timeline_.


## Importazione di campioni

Il primo passo consiste nell'aggiungere alcuni suoni, come descritto in dettaglio nel capitolo _Importazione di audio_.
In questo caso, utilizziamo la finestra di dialogo _Aggiungi media esistenti_ (**Ctrl + I**) per importare alcuni 
campioni di batteria come regioni. I campioni utilizzati in questo tutorial sono stati ottenuti da un pacchetto di 
campioni dal sito web [freesound.org](http://www.freesound.org/) (il pacchetto di campioni 
[Nord Drum Mini Kit](https://freesound.org/people/menegass/packs/10430/)).

{{< figure alt="FS1" src="it/ardour8-freesound-1.png" >}}

Dopo aver importato alcuni suoni dal pacchetto di campioni scaricato (grancassa, rullante, charleston, clap), la nostra 
sessione appare così (in questo caso abbiamo utilizzato l'opzione _Aggiungi file come nuove tracce_ e li abbiamo 
inseriti _all'inizio della sessione_. I campioni della batteria appaiono come nuove tracce individuali nella finestra 
_Editor_, ciascuna con il nome del file audio utilizzato. Se i nomi dei file sono troppo lunghi o poco chiari, è 
possibile rinominare le tracce per maggiore chiarezza.

{{< figure alt="FS2" src="it/ardour7-freesound-2.png" >}}

## Organizzazione delle tracce

Rinominiamo le tracce in modo da poter vedere rapidamente la posizione di ciascuno strumento. 
Per farlo, fai doppio clic sul nome della traccia per modificarlo.

{{< figure alt="FS3" src="it/ardour7-freesound-3.png" >}}

È anche possibile riorganizzare l'ordine delle tracce dall'alto verso il basso nella finestra dell'editor. Per farlo, 
cliccare sulla scheda _Tracce e bus_ all'estrema destra della finestra _Editor_ e trascinare le tracce nell'ordine 
desiderato.

{{< figure alt="FS4" src="it/ardour8-freesound-4.png" >}}

Un'altra opzione per riorganizzare le tracce è selezionare una traccia e utilizzare la scorciatoia 
**Ctrl+Freccia su/giù** per spostarla verso l'alto o verso il basso.

{{< callout type="info" >}}
È inoltre possibile utilizzare le caselle di controllo V in questa scheda per visualizzare o nascondere le tracce 
nell'area di lavoro principale.
{{< /callout >}}

Qui abbiamo ordinato la batteria in modo che la grancassa sia in basso, il rullante e il charleston siano al centro e il
clap sia in alto.

{{< figure alt="FS6" src="en/ardour7-freesound-5.png" >}}

## Continua

Nel prossimo passaggio impareremo come impostare il metronomo per organizzare questi campioni in un ritmo.

Successivo: [Impostazione del tempo musicale](../setting-up-time-signature)