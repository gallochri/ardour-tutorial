---
title: Programmare sequenze
description: Il gruppo Follow Options nella finestra Cue è dove si programma la sequenza delle clip.
weight: 6
cascade:
  type: docs
---

{{< details title="Guarda il video" closed="true" >}}

{{< youtube Gg1eZK8n7P0 >}}

{{< /details >}}

Il gruppo _Follow Options_ (Opzioni Azioni a seguire) nella finestra Cue è dove si programma la sequenza delle clip.

{{< figure src="it/performing-live-follow-options.png" alt="Opzioni Follow" >}}

Un semplice esempio di sequenza è una clip che riproduce 4 battute di intro nel cue A, attiva la clip successiva dal 
cue B che riproduce otto battute due volte, quindi attiva la clip nel cue D che, dopo aver riprodotto quattro battute 
quattro volte, attiva nuovamente la clip nel cue B, e quindi il ciclo da B a D si ripete all'infinito.

<!-- FIXME SCREENSHOT -->

Si chiamano "Follow options" (Opzioni Azioni a seguire) perché queste impostazioni definiscono cosa succede dopo che una
clip è stata riprodotta una volta.

## Impostazione delle opzioni azioni a seguire

Esistono diversi modi per impostare un'azione a seguire.

1. Puoi farlo nell'elenco a discesa in basso:

{{< figure src="it/performing-live-set-in-follow-options.png" alt="Impostare le Follow Options" >}}

2. È possibile fare clic su questo widget a destra del nome del clip e selezionare un'azione:

{{< figure src="it/performing-live-set-in-clip-widget.png" alt="Impostare nel widget clip" >}}

3. È anche possibile selezionare in blocco un'azione a seguire per l'intero cue. Per farlo, cliccare con il tasto destro
del mouse sul nome del cue e selezionare **Setta tutte le azioni a seguire**.

{{< figure src="it/performing-live-set-all-in-cue.png" alt="Impostare tutte in un cue" >}}

## Azioni a seguire

Il comportamento predefinito è quello di riprodurre la stessa clip più volte fino a quando l'utente non attiva una clip
diversa in quella traccia o interrompe la riproduzione. Questa azione è denominata _Again_.

L'azione _Inverti_ avvia la riproduzione della clip che si trova nello slot precedente nella traccia. Quindi, una volta 
che una clip in Cue D è stato riprodotto un determinato numero di volte, Ardour attiva la clip in Cue C.

L'azione _Avanti_ fa il contrario e attiva la clip nello slot successivo, quindi da una clip in Cue D passerai alla clip
in Cue E.

È possibile utilizzare l'azione _Jump_ per saltare più cue in avanti o indietro e passare direttamente al cue 
desiderato. È quindi possibile passare dal cue F al cue M e poi dal cue M al cue B.

L'opzione _Follow Count_ consente di impostare il numero di volte in cui un clip viene riprodotto prima che la 
riproduzione si interrompa o che venga attivato un altro clip nella traccia. È anche possibile controllare la quantità 
di clip originale che viene riprodotta. A tal fine, attivare questo pulsante e modificare il numero di battiti che 
Ardour riprodurrà dalla clip nello slot di attivazione selezionato.

L'opzione _Follow Count_ è anche ciò che distingue l'azione _Nessuna_ dall'azione _Ferma_.

Se desideri che una clip venga riprodotta un determinato numero di volte e poi si interrompa, seleziona l'azione _Ferma_.

Ma se desideri interrompere temporaneamente il numero selezionato o le ripetizioni, ignorare la durata personalizzata 
della clip e interrompere la riproduzione dopo una sola volta, seleziona l'azione di follow _Nessuna_.
