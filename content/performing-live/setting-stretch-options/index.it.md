---
title: Impostazione delle opzioni di dilatazione
description: A volte un loop di batteria che vorresti davvero usare in una canzone ha un tempo più lento o più veloce 
  rispetto al tempo della tua sessione.
weight: 4
cascade:
  type: docs
---

{{< details title="Guarda il video" closed="true" >}}

{{< youtube _Pc7CHzewQ0 >}}

{{< /details >}}

A volte un loop di batteria che vorresti davvero utilizzare in una canzone ha un tempo più lento o più veloce rispetto 
al tempo della tua sessione. Le opzioni di dilatazione aiutano a mantenerlo perfettamente sincronizzato con il resto 
della canzone.

## Come Ardour gestisce il tempo delle clip per impostazione predefinita

Per impostazione predefinita, Ardour stimerà il tempo effettivo di un file audio. Quindi, durante la riproduzione, 
allungherà o comprimerà il file audio al volo per adattarlo al tempo della sessione corrente. Questo funziona anche 
all'interno di una rampa di tempo, quindi il tempo della clip seguirà l'accelerazione e la decelerazione.

È possibile sovrascrivere questo comportamento predefinito per scopi artistici e riprodurre una clip col suo tempo 
originale disabilitando l'allungamento di questa nel pannello **Opzioni di dilatazione**.

{{< figure src="it/stretch-options.png" alt="Opzioni di dilatazione" >}}

## Sovrascrivere il tempo della clip

È anche possibile aumentare o diminuire facilmente il tempo della clip di due, quattro, otto o più volte cliccando su 
questi due pulsanti.

{{< figure src="it/stretch-multiply-divide.png" alt="Moltiplicare o dividere il tempo della clip" >}}

Supponiamo che il tempo della clip originale sia 120 bpm e quello della sessione sia 140 bpm. Ciò significa che la clip 
verrà riprodotta solo con una velocità superiore del 14%. Ma se si fa supporre ad Ardour che il tempo originale sia 
60 bpm, allora Ardour dovrà compensare la differenza di 80 bpm anziché 20 bpm. E quindi riprodurrà il clip più di due 
volte più velocemente.

È possibile aumentare o diminuire il tempo della clip in piccoli incrementi modificando il numero di battiti in cui è 
misurata la clip. Quindi, se si desidera che questa clip venga riprodotta in 14 battute, il suo nuovo tempo presunto 
sarà di 105 bpm.

<!-- FIXME SCREENSHOT -->

## Opzioni specifiche dal tipo di materiale audio

Non è possibile allungare o comprimere i loop di batteria e quelli di pianoforte allo stesso modo, quindi Ardour offre 
tre opzioni.

{{< figure src="it/stretch-presets.png" alt="Preimpostazioni di dilatazione" >}}

- Il preset _Crisp_ funziona al meglio con loop di batteria e altro materiale caratterizzato da attacco veloce, 
decadimento elevato e sustain e rilascio rapidi.
- Il preset _Liscio_ funziona al meglio con note lunghe e sostenute che hanno un attacco lento, come un pad sintetizzato
o archi suonati con l'archetto.
- E il preset _Mixed_ è per qualcosa a metà strada tra questi due casi, come la voce o gli accordi di pianoforte.