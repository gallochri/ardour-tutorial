---
title: Avvio e arresto della riproduzione
description: Per avviare la riproduzione di un singolo clip, basta cliccare sul pulsante con l'icona a forma di 
  triangolo a sinistra del suo nome.
weight: 3
cascade:
  type: docs
---

{{< details title="Guarda il video" closed="true" >}}

{{< youtube EaNW104iEkM >}}

{{< /details >}}

Impariamo come avviare e interrompere singoli clip e interi cue.

## Avvio della riproduzione della clip

Per avviare la riproduzione di un singolo clip, basta cliccare sul pulsante con l'icona a forma di triangolo a sinistra 
del suo nome.

{{< figure src="it/launch-from-grid.png" alt="avvio dall'elenco" >}}

Il trasporto inizierà. Una volta che il cursore di riproduzione raggiunge l'unità di quantizzazione di lancio 
successiva, che è di 1 battuta per impostazione predefinita, Ardour inizierà a riprodurre la clip. Per impostazione 
predefinita, la clip verrà riprodotta in ripetizione fino a quando non la si interrompe.

## Interruzione della riproduzione della clip

Esistono due modi per interrompere la riproduzione di una singola clip:

1. Interrompi il trasporto. In questo modo anche la riproduzione verrà immediatamente interrotta.

2. Interrompi la riproduzione della clip cliccando su una clip vuota nella traccia con un'icona quadrata.

{{< figure src="it/stop-from-grid.png" alt="arresto dall'elenco" >}}

La riproduzione della clip verrà interrotta, ma il trasporto continuerà a funzionare.

## Avvio riproduzione cue

La riproduzione e l'interruzione di un intero cue funzionano in modo simile. Per riprodurre un intero cue, clicca 
sull'intestazione del cue:

{{< figure src="it/launch-entire-cue.png" alt="avvio intero cue" >}}

Se alcuni dei trigger slot hanno un'unità di quantizzazione di lancio più breve o più lunga, le rispettive clip 
potrebbero iniziare prima o dopo rispetto agli altri.

## Interruzione della riproduzione cue

Per interrompere la riproduzione di un cue, premi il pulsante di arresto situato proprio sotto l'elenco dei cue.

{{< figure src="it/stop-entire-cue.png" alt="arresto intero cue" >}}

Questo interromperà la riproduzione dele clip nella cue, ma il trasporto continuerà. Oppure interrompi il trasporto, 
e anche la riproduzione dei clip si interromperà immediatamente.