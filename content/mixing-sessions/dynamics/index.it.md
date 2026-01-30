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

{{< figure alt="Fast Lookahead Limiter" src="it/ardour8-fast-lookahead-lmiter.png" >}}

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

**Threshold** (Soglia)
: Imposta il livello al quale il compressore inizierà ad agire.

**Ratio** (Rapporto)
: Controlla quanto il compressore "comprimerà" il suono.

**Attack** e **Release** (attacco e rilascio)
: Controlla la velocità con cui il compressore influisce sul suono.

{{< figure alt="ACE Compressor" src="it/ardour8-ace-compressor.png" >}}

Il plugin _ACE Compressor_ nella schermata sopra riportata presenta due controlli aggiuntivi:

**Threshold level** (in dB)
: Imposta il livello al quale il compressore comprimerà o ridurrà il suono.

**Makeup gain** (in dB)
: Aumenta l'intero segnale dopo la compressione.

Per ammorbidire una voce, ad esempio, è possibile impostare il livello di soglia (Threshold level) a circa −10dB e un 
rapporto (Ratio) di 2,5, quindi riportare il volume al livello originale con il guadagno di compensazione (Makeup gain).
Gli altri tre controlli — tempo di attacco (Attack time), tempo di rilascio (Release time) e knee — consentono di 
controllare la forma della compressione.

Per una compressione vocale morbida, è consigliabile un tempo di attacco semi-veloce in modo che il compressore catturi 
l'inizio di ogni parola, un tempo di rilascio più lento per lasciare risuonare la voce e un raggio morbido per creare 
una forma delicata di compressione che non sia troppo evidente.

Se vuoi rendere il suono della batteria più potente, potresti provare un tempo di attacco lento in modo da non 
comprimere il suono della batteria, un tempo di rilascio veloce in modo che il compressore possa catturare il colpo 
successivo della batteria e un rapporto elevato per rendere simili le dinamiche tra l'inizio e la fine del colpo della 
batteria.

Di seguito è riportato uno screenshot di un compressore simile dalla [LSP plugins suite](https://lsp-plug.in/):

{{< figure alt="LSP Compressor Mono" src="it/ardour8-lsp-compressor-mono.png" >}}

Se vuoi imparare più velocemente come usare un compressore, una buona idea è quella di inserire un plugin di 
visualizzazione prima del compressore e uno subito dopo, aprire entrambi. 

## Gating

Il tipo più semplice di _gate_ consente il passaggio di un segnale quando supera un determinato livello e lo blocca 
quando è inferiore a tale livello.

I gate vengono spesso utilizzati come una sorta di riduzione del rumore. Ad esempio, il gate su un canale microfonico 
potrebbe aprirsi solo mentre il cantante sta cantando, impedendo che altri rumori di fondo vengano trasmessi quando non 
sta cantando. Anche i tamburi con gate sono un trucco di produzione in studio molto noto per renderli più "nitidi".

Qui, il plugin _Hard Gate_ (da una suite di plugin LADSPA chiamata [CMT](https://www.ladspa.org/cmt/overview.html)) 
visualizza un unico parametro di controllo, la _soglia_ (threshold) alla quale il gate si aprirà e lascerà passare il 
segnale.

{{< figure alt="Hard Gate" src="it/ardour8-hard-gate.png" >}}

Altri tipi di gate, come il plugin _LSP Gate_ nella schermata sottostante, sono più complessi. Consentono un controllo 
indipendente sulla velocità di apertura (_Attack_) e rilascio (_Release_) del gate, oltre ad altri parametri molto 
simili a quelli descritti sopra per il compressore SC.

{{< figure alt="LSP Gate" src="it/ardour8-lsp-gate-mono.png" >}}

## Continua

Ora che abbiamo esplorato alcuni strumenti per ottenere la gamma dinamica esattamente come desideri, è il momento di 
esaminare la regolazione del bilanciamento delle frequenze presenti in ogni singola traccia e nel mix complessivo. Nel 
prossimo capitolo impareremo come utilizzare l'equalizzatore per ottenere proprio questo risultato.

Successivo: [Equalizzazione](../equalizing)
