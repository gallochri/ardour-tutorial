---
title: Impostazione delle opzioni di avvio
description: Ardour offre diverse opzioni che definiscono come viene attivata una clip, quando inizia la riproduzione dopo l'attivazione, ecc.
weight: 5
cascade:
  type: docs
---

{{< details title="Guarda il video" closed="true" >}}

{{< youtube TuZvUn311MQ >}}

{{< /details >}}

Ardour offre diverse opzioni che definiscono come viene attivata un clip, quando inizia la riproduzione dopo 
l'attivazione e se risponde all'attivazione della riproduzione di un intero cue a cui appartiene.

{{< figure src="it/launch-options.png" alt="Opzioni di avvio" >}}

## Stili di lancio

Supponiamo di avere una configurazione predefinita in cui la sensibilità della dinamica è impostata su zero, lo stile di
lancio è impostato su _Trigger_, l'unità di quantizzazione del lancio è 1 battuta, entrambe le opzioni _Legato_ e 
_Cue Isolate_ sono disabilitate e il trasporto è in esecuzione.

{{< figure src="it/launch-style-trigger.png" alt="Stile di lancio: Trigger" >}}

Quando clicchi sul pulsante di attivazione, Ardour attenderà l'inizio della battuta successiva e inizierà la 
riproduzione della clip. In questo caso, il pulsante di attivazione non risponderà a nuovi clic o eventi MIDI inviati. 
Inoltre, poiché la sensibilità alla dinamica è impostata su zero e stai utilizzando un mouse, la clip verrà riprodotta 
con il suo volume normale.

Ma se lo imposti al valore massimo e utilizzi un controller MIDI esterno con tasti sensibili alla dinamica o pad in 
silicone, il volume dipenderà dalla forza con cui premi il tasto o il pad.

## Quantizzazione di avvio

Quando imposti l'unità di quantizzazione di avvio su 4 battute, Ardour dividerà l'intera timeline di conseguenza. 
Quindi, se il cursore di riproduzione si trova alla battuta 6 e hai appena attivato la riproduzione di una clip, Ardour 
attenderà la battuta 9 e poi inizierà a riprodurre la clip. È anche possibile utilizzare unità molto più piccole, come 
un sedicesimo di battuta.

{{< figure src="it/launch-quantization.png" alt="Quantizzazione di avvio" >}}

Ma Trigger non è l'unico stile di lancio.

_Retrigger_ avvierà la riproduzione della clip e risponderà a nuovi clic o eventi MIDI. Quando lo si attiva nuovamente,
Ardour interromperà la riproduzione della clip, attenderà la successiva unità di quantizzazione di avvio e quindi 
riprodurrà la clip dall'inizio. È possibile ripetere questa operazione tutte le volte che si desidera.

_Gate_ riprodurrà la clip finché si tiene premuto il pulsante del mouse o il tasto o il pad MIDI.

Con _Toggle_, basta cliccare una volta sul pulsante di attivazione e il clip continuerà a essere riprodotto fino a 
quando non lo cliccherai di nuovo o non gli invierai un evento MIDI.

## Legato

Il _Legato_ è utile quando si passa spesso da un clip all'altro della stessa traccia. Supponiamo che abbiate un loop di 
batteria lungo 8 battute. E che abbiate due varianti di un loop di linea di basso, anch'esse lunghe 8 battute. Quindi, 
quando sei a due battute nel nuovo ciclo di ripetizione e attivi la seconda linea di basso, senza la modalità legato, 
la linea di basso inizia dall'inizio e quindi ottieni un offset di 2 battute, e il tuo loop di batteria e il tuo loop di
linea di basso sono ora fuori sincrono. Ma quando abiliti la modalità Legato, Ardour inizierà a riprodurre il secondo 
loop di linea di basso dalla terza battuta. E così la tua sezione ritmica sarà perfettamente sincronizzata.

<!-- FIXME SCREENSHOT -->

## Cue Isolate

La modalità _Cue Isolate_ è utile quando non è necessario riprodurre una clip particolare all'avvio dell'intero cue. In 
genere ciò accade perché è stata programmata una sequenza complessa per una determinata traccia e non si desidera che 
venga compromessa dall'avvio dei cue.