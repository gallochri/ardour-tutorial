---
title: Dinamica
description: Applicazione di limitatori, compressori e gate in Ardour
weight: 6
cascade:
  type: docs
---

Uno dei problemi che potresti incontrare in un mix è che, a seconda del materiale, le parti più forti sono troppo forti
e/o quelle più deboli sono troppo deboli.

Questo tipo di problema non può essere risolto facilmente utilizzando solo i fader per regolare i livelli. È possibile 
impostare livelli così alti da causare il clipping, oppure aggiungere rumori di fondo indesiderati semplicemente alzando
i livelli. Si tratta di problemi legati alla cosiddetta _gamma dinamica_, ovvero la differenza tra le parti più rumorose
e quelle più silenziose della sessione. Esistono diversi tipi di strumenti per regolare la gamma dinamica, disponibili 
principalmente come plugin di terze parti all'interno di Ardour, tra cui _limiting_, _compressione_ e _gating_.

## Limiting

Un _limiter_ è uno strumento che impedisce al volume di una traccia di superare un determinato livello, solitamente il 
livello di picco (0dB) o un valore simile. Molti limiter hanno la possibilità di aumentare i livelli del segnale in 
ingresso prima che vengano limitati, e in questo modo è possibile "colmare il divario" tra le parti più forti e quelle 
più deboli del mix. Un limiter può essere utilizzato anche sul bus _Master_ per impedire il clipping del mix 
complessivo. I limiter sono quasi sempre utilizzati post-fader.

Nell'esempio seguente viene utilizzato un plugin denominato _Fast Lookahead Limiter_ (se non lo trovate tra i plugin 
installati, cercate qualsiasi altro plugin denominato "Limiter"). Per impostare il livello di limitazione, è sufficiente
regolare il cursore _Limit (dB)_. Il _Fast Lookahead Limiter_ anticipa letteralmente il segnale di alcuni millisecondi 
e, quando rileva che il segnale sta per superare il limite impostato, abbassa automaticamente i livelli.

![limiter](en/ardour7-fast-lookahead-lmiter.png?width=500)

Il cursore _Input Gain (dB)_ determina di quanto vengono aumentati i livelli prima che raggiungano il limitatore, mentre
il misuratore _Attenuation (dB)_ sul lato destro mostra di quanto vengono ridotti i livelli in un dato momento. Mentre 
la riduzione del volume è quasi istantanea, il cursore _Release time (s)_ determina il tempo necessario al limitatore 
per tornare a 0dB di _Attenuation_.

Si noti che più si spinge il limiter (aumentando il guadagno in ingresso e/o diminuendo il limite massimo di picco 
consentito), maggiore sarà la riduzione che il limiter sarà costretto ad applicare e maggiore sarà la probabilità che si
verifichino artefatti di elaborazione (come distorsioni o variazioni irregolari del volume). Sul bus _Master_, in genere
è meglio evitare un limiting eccessivo.

## Compressione

Un _compressore_ aumenta il volume complessivo di un suono, ma poi lo "comprime" a seconda di quanto è forte. Questo può
rendere la voce più uniforme o la batteria più piena e forte. L'effetto finale è simile a quello di un limitatore che 
riduce la differenza tra il suono più basso e quello più alto, ma l'effetto è più selettivo quando si usa un compressore.

Un compressore tipico avrà questi comandi obbligatori:

**Soglia**
: Imposta il livello al quale il compressore inizierà ad agire.

**Rapporto**
: Controlla quanto il compressore "comprimerà" il suono.

**Attacco** e **Rilascio**
: Controlla la velocità con cui il compressore influisce sul suono.

![ACE Compressor](en/ardour7-ace-compressor.png?width=450)

The _ACE Compressor_ plugin on the screenshot above has two additional controls:

**Threshold level** (in dB)
: Sets the level at which the compressor will compress or squeeze the sound.

**Makeup gain** (in dB)
: Boosts the whole signal after the compression occurs.

To soften out a vocal, for example, you could set _Threshold level_ of −10dB or
so and a _Ratio_ of 2.5, and then bring the volume back up with the _Makeup
gain_. The other three controls — _Attack time_, _Release time_, and _Knee_ —
allow you to control the shape of the compression.

For soft vocal compression, you would want a semi-fast attack time so that the
compressor catches the beginning of each word, a slower release time to let the
voice ring out, and a soft knee radius to create a gentle form of compression
that isn't too noticeable.

If you want to make drums sound big, you might try a slow attack time so that
you don't compress the pop of the drum, a fast release time so that the
compressor can catch the next hit of the drum, and a large ratio to make the
dynamics between the beginning and end of the drum hit similar.

Below is a screenshot of a similar compressor from the [LSP plugins
suite](https://lsp-plug.in/):

{{< figure alt="LSP Compressor Mono" src="en/ardour7-lsp-compressor-mono.png" >}}

If you want to speed up learning how to use a compressor, a generally good idea
is to insert one scope visualization plugin before the compressor and one right
after, then open both 

## Gating

The simplest kind of a _gate_ allows a signal to pass through when it is over a
certain level, and blocks the signal when it is lower than that.

Gates are often used as a kind of noise reduction. For example, the gate on a
microphone channel might only open while the singer is singing, preventing other
background noises from coming through as well when she is not singing. Gated
drums are also a very well-known studio production trick to make them sound
"sharper".

Here, the _Hard Gate_ plugin (from a suite of LADSPA plugins called
[CMT](https://www.ladspa.org/cmt/overview.html)) displays a single control
parameter, the _Threshold_ at which the gate will open and let the signal
through.

![Hard Gate](en/ardour7-hard-gate.png?width=400)

Other kinds of gates, such as the _LSP Gate_ plugin on the screenshot below, are
more complex. They have independent control over how quickly the gate opens
(_Attack_) and closes (_Release_), as well as other parameters quite similar to
those described for the SC Compressor above.

{{< figure alt="LSP Gate" src="en/ardour7-lsp-gate-mono.png" >}}

## Continuing

Now that we've explored some tools for getting the dynamic range exactly where
you want it, it's time to look at adjusting the balance of frequencies present
in each individual track and in your overall mix. In the next chapter, we'll
learn how to use the equalizer to do just that.

Next: [EQUALIZING](../equalizing)
