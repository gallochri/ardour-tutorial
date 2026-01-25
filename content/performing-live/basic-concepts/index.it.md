---
title: Concetti di base
description: "Le basi di un sequencer cue non lineare"
weight: 1
cascade:
  type: docs
---

{{< details title="Guarda il video" closed="true" >}}

{{< youtube sQYT5f1Z6FQ >}}

{{< /details >}}

La finestra Cue fornisce strumenti per il sequencing non lineare, dove è possibile attivare la riproduzione di brevi 
clip audio e MIDI ripetibili.

## Organizzazione dell'interfaccia utente

La parte principale della finestra Cue è una griglia di clip raggruppate per tracce e cue.

{{< figure src="it/cue-window-matrix.png" alt="Griglia di clip" >}}

Le tracce sono disposte verticalmente e solitamente raggruppano clip con lo stesso tipo di strumento. È possibile avere 
una traccia per le linee di basso, una traccia per la batteria, una traccia per le progressioni di accordi di synth e 
così via. È possibile registrare nuovo materiale su queste tracce, quindi tagliarlo e caricarlo nel sequencer cue. 
Tuttavia, finché una traccia è visibile nella finestra Cue, questo materiale non verrà riprodotto. In un dato momento è
possibile riprodurre solo una clip in una traccia.

I cue, tuttavia, sono disposti orizzontalmente e organizzano le clip che devono essere riprodotte contemporaneamente.

Una struttura piuttosto comune è quella in cui uno strumento suona 4 battute di introduzione nel primo cue, poi c'è una
clip con una variazione di quella melodia nel secondo cue più la sezione ritmica. Nel terzo cue è possibile modificare 
leggermente il loop di batteria e la linea di basso e magari aggiungere la voce.

## Come funziona il sequencer non lineare

La natura non lineare dei cue entra in gioco quando si programma il sequencer per riprodurre un clip un certo numero di
volte, quindi attivare automaticamente la riproduzione di un altra clip in quella traccia. Il trasporto continuerà a 
funzionare, ma il sequencer passerà da una clip all'altra.

## Slot di attivazione vs clip

La cella della griglia che contiene una clip è chiamata slot trigger. È chiamata così perché risponde a un evento che 
attiva la riproduzione. In genere si tratta della pressione di un pulsante di riproduzione, della pressione di un tasto 
su un controller MIDI o di un comando nel sequencer.

Gli slot e le clip sono due concetti diversi. Il modo in cui la clip viene attivata, l'unità di griglia a cui è 
quantizzato, il numero di volte in cui una clip viene riprodotta o quale clip viene attivata automaticamente dopo: tutte
queste impostazioni appartengono a uno slot di attivazione. Questo è comodo perché, se si decide di sostituire una clip
con un altra, non è necessario reinserire tutte le impostazioni.