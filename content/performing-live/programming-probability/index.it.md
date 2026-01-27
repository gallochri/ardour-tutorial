---
title: Programmare la probabilità
description: Il gruppo Opzioni di follow nella finestra Cue è dove si programma la sequenza dei clip.
weight: 7
cascade:
  type: docs
---

{{< details title="Guarda il video" closed="true" >}}

{{< youtube _ET1YqbMPc0 >}}

{{< /details >}}

Ora che avete già familiarità con le azioni di base nella finestra Cue, parliamo della programmazione della probabilità.

In poche parole, la probabilità è il modo in cui puoi permettere ad Ardour di creare piccoli incidenti fortunati che ti 
consentono di esplorare nuove idee. Ci sono due modi per usare questa funzione.

<!-- FIXME SCREENSHOT -->

## Probabilità con azioni successive

Prima di tutto, puoi impostare due diversi tipi di azione a seguire per lo stesso slot di trigger. Supponiamo che 
l'opzione a sinistra attivi la clip precedente e quella a destra attivi la clip successiva.

{{< figure src="it/reverse-vs-forward-former.png" alt="Inverti a Avanti" >}}

Ora trascina il cursore (Left - Right) verso destra o fai scorrere la rotellina del mouse in modo che la seconda opzione
a destra abbia la possibilità di essere utilizzata.

{{< figure src="it/reverse-vs-forward-middle.png" alt="Cursore di probabilità al centro" >}}

Quando il cursore si trova esattamente al centro tra le azioni di sinistra e di destra, queste azioni hanno la stessa 
probabilità di essere utilizzate al termine della riproduzione della clip. È possibile trascinarlo più a destra per dare
all'azione di destra una maggiore possibilità di essere selezionata:

{{< figure src="it/reverse-vs-forward-latter.png" alt="Cursore di probabilità a destra" >}}

Oppure puoi trascinarlo completamente a destra in modo che l'azione a sinistra non possa essere utilizzata in alcun modo.

## Probabilità con azione Multi-Jump

Il secondo modo per programmare la probabilità è utilizzare l'azione a seguire Multi-Jump. Seleziona questa azione e poi 
attiva ogni slot trigger nella traccia che dovrebbe avere la possibilità di essere riprodotto in modo casuale.

{{< figure src="it/multi-jump.png" alt="Azione Multi-Jump" >}}

Ogni volta che Ardour finisce di riprodurre la clip in questo slot trigger, sceglierà in modo casuale uno degli slot che
hai selezionato in precedenza.
