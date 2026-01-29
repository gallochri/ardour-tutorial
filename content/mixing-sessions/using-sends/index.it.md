---
title: Utilizzo dei send
description: Come utilizzare i send in Ardour
weight: 5
cascade:
  type: docs
---

Un _Send_ è semplicemente un'uscita aggiuntiva per una traccia o un bus con un proprio fader separato che può essere 
utilizzato per indirizzare il segnale verso altri punti in Ardour.

Conosciuti anche come _mandate ausiliarie_, prelevano il segnale in un punto specifico del flusso del segnale 
(pre-fader, post-fader, prima o dopo gli equalizzatori e altri plugin, ecc.) e inviano copia di quel segnale altrove, 
senza influire sul normale flusso del segnale verso il fader del canale.

In Ardour, puoi facilmente aggiungere _sends_ alle tracce e ai bus tramite la barra del mixer. I send sono processori, 
proprio come i plugin.

## Quando è utile utilizzare un send?

Nei capitoli precedenti abbiamo creato un pattern di batteria con quattro tracce separate: cassa (kick), rullante 
(snare), charleston (hihat) e clap. Supponiamo ora che tu voglia aggiungere un riverbero alla batteria. Ovviamente 
potresti aggiungere un plugin separato per ogni singola traccia e modificarne le impostazioni separatamente, ma questo 
metodo aumenta inutilmente la quantità di lavoro. Ogni volta che desideri modificare un'impostazione di riverbero per 
tutta la batteria, dovresti aprire tutti e quattro i plugin di riverbero e modificarli allo stesso modo.

È qui che i send tornano utili: puoi usarli per aggiungere un effetto particolare a una serie di tracce senza creare più
istanze dello stesso plugin.

Ecco una panoramica di come procederemo:

1. Crea un unico bus con il plugin desiderato.
2. Aggiungi un send a ciascuna traccia di batteria a cui desideri applicare l'effetto.
3. Indirizza questi send al bus.

## Creazione del bus e aggiunta di un plugin

Crea un bus (`Traccia > Aggiungi traccia, bus o VCA...` nel menu), assegnagli un nome appropriato e aggiungi un plugin 
nella regione pre-fader (clicca con il tasto destro del mouse appena sopra il rettangolo blu del fader nella casella del
processore), come descritto nel capitolo precedente, _Utilizzo dei plugin_.

In questo esempio abbiamo creato un bus stereo chiamato _Batteria_ e aggiunto il plugin _ACE Reverb_ al bus.

{{< figure alt="sends1" src="it/ardour8-ace-reverb-in-mixer-strip.png" >}}

### Ingressi Bus

Il segno "-" visualizzato nel pulsante di ingresso del bus indica che non è stato ancora indirizzato nulla a questo bus.
Ci occuperemo di questo più avanti.

### Uscita Bus

Prima di instradare un send a questo bus, assicurarsi che le uscite del bus siano instradate al bus _Master_, come 
mostrato di seguito (il pulsante in basso riporta la dicitura "*master*").

{{< figure alt="sends2" src="it/Ardour4_Sends_2.png" >}} 

Inoltre, apri la finestra del plugin (doppio clic sul rettangolo _ACE Reverb_) e imposta il mix del segnale del plugin 
sul valore _Blend_ a 1.

{{< figure alt="sends3" src="it/ardour8-ace-reverb-settings.png" >}}

Questo assicura che il bus trasporti tutto il segnale elaborato dal plugin e nessun segnale non elaborato al bus 
_Master_. Ricorda che i segnali non elaborati, "puliti", sono ancora disponibili dalle loro tracce originali, quindi non
è necessario duplicarli in questo bus.

## Creazione e instradamento dei send

Ora possiamo creare i send nelle altre tracce e indirizzarli agli ingressi del bus.

Come i plugin, anche i send vengono creati nella casella del processore. Vai su ciascuna delle tue tracce di batteria, 
fai clic con il tasto destro del mouse in uno spazio vuoto della casella del processore e crea un _Nuova mandata aux..._ 
indirizzata al bus appropriato (nel nostro caso, denominato _Batteria_).

{{< figure alt="sends4" src="it/ardour8-adding-aux-send.png" >}}

{{< callout type="info" >}}
Se *non* vedi l'opzione _Nuova mandata aux..._ nel menu, probabilmente è perché non hai ancora creato alcun bus. Torna 
al passaggio precedente per crearlo.
{{< /callout >}}

Ora dovresti vedere il messaggio visualizzato nella casella del processore:

{{< figure alt="post-fader" src="it/ardour8-post-fader-send.png" >}}

Il piccolo cursore _Invia_ che vedi appena sotto il rettangolo verde è il fader di invio, che controlla la quantità di 
suono che verrà inviata da questa traccia al bus.

### Send Post-Fader contro Pre-Fader

Si noti che l'immagine sopra mostra un send _post-fader_ (si trova _dopo_ il rettangolo del fader). Negli invii 
_post-fader_, il livello di invio è controllato _prima_ dal fader della traccia/bus e _poi_ dal fader di invio.

In un invio _pre-fader_, invece, il livello del send è controllato solo dal fader del send, indipendentemente dal fader 
della traccia/bus. Un invio _pre-fader_ avrebbe questo aspetto:

{{< figure alt="prefader" src="it/ardour8-pre-fader-send.png" >}}

È possibile trascinare il rettangolo di invio verso l'alto e verso il basso nella casella del processore per renderlo 
pre- o post-fader, a seconda delle necessità.

{{< callout type="info" >}}
La scelta tra pre-fader o post-fader dipende dal tipo di plugin di effetto utilizzato e dal risultato desiderato. Per 
questo esercizio, entrambi funzionano.
{{< /callout >}}

Un send si comporta esattamente come qualsiasi altro plugin nella casella del processore. È possibile disattivarlo 
temporaneamente cliccando sul piccolo LED, mentre cliccando con il tasto destro del mouse sul rettangolo è possibile 
accedere ad altre opzioni, tra cui _Delete_.

### Send Fader

To control the level of each send, simply click and drag the send fader to
increase or decrease its volume.

{{< figure alt="sendfader" src="en/Ardour4_Send_Fader.png" >}} 

The _Drums_ bus is now receiving the sum of all tracks, and applying the effect
to it. A single plugin applied to the bus controls the effect for the mix of all
drum sounds routed there. This way, you have independent control over the "dry"
sound of the original tracks, and the "wet" sound coming out of the bus. 

Because sends are very useful for this kind of work with effect plugins, they
are also commonly called "Effect Sends".

## Continuing

Now that you know how to add plugins to a track, as well as how to add sends
to tracks to create plugin busses usable by any number of tracks, it might be
helpful to learn about a few other plugins useful in the mixing process.
Please continue on to the following chapters covering _dynamics_ and
_equalizing_.

Next: [DYNAMICS](../dynamics)
