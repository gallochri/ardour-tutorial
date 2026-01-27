---
title: La barra del mixer
description: Elementi della barra del mixer in Ardour
weight: 1
cascade:
  type: docs
---

Il _mixaggio_ è il processo di conversione di più tracce in un mix stereo o multicanale in cui tutti gli strumenti 
possono essere ascoltati chiaramente.

## Strumenti di mixaggio

_Livelli_, _panning_, _equalizzazione (EQ)_ e _compressione_ sono gli strumenti principali utilizzati per ottenere un 
buon mix. Oltre a questi strumenti fondamentali, è possibile utilizzare anche un'ampia gamma di effetti per migliorare 
il suono, come il riverbero e il delay.

## Presentazione della barra del mixer

La _barra del mixer_ è la colonna verticale che contiene vari controlli relativi al flusso del segnale. Ogni traccia e 
bus in Ardour ha una propria barra del mixer. La barra del mixer è anche lo strumento principale che useremo nel processo 
di mixaggio delle nostre tracce. In questo capitolo, forniremo una panoramica generale della barra del mixer, 
descrivendone ogni sezione. Forniremo anche riferimenti ai capitoli contenenti informazioni specifiche su ogni aspetto 
della barra del mixer.

## La Barra del mixer dall'alto verso il basso

È possibile accedere alle barre del mixer sia dalla finestra _Editor_ che dalla finestra _Mixer_ (scorciatoia **Alt+M** 
per passare da una all'altra). Le barre del mixer in entrambe le finestre (_Editor_ o _Mixer_) sono speculari: qualsiasi
azione eseguita su una barra del mixer nella finestra _Mixer_ si rifletterà nella barra corrispondente nella finestra 
_Editor_ e viceversa. La finestra _Editor_ e la finestra _Mixer_ sono spiegate più dettagliatamente nel capitolo 
_Panoramica dell'interfaccia_.

Nella finestra _Editor_, è possibile visualizzare la barra del mixer della traccia attualmente selezionata sul lato 
sinistro della finestra. Se non la vedete, premete **Shift+E** per visualizzarla.

### Panoramica

Qui vediamo l'intera barra del mixer, così come apparirebbe nella finestra _Editor_ o nella finestra _Mixer_.

{{< figure alt="strip1" src="it/ardour8-mixer-strip-1.png" >}}

### Modalità regolare e stretta

La barra del mixer può essere commutata tra una larghezza normale e una più ridotta per risparmiare spazio. Nella parte
superiore della barra del mixer, illustrata di seguito, è possibile commutare tra le modalità normale e ridotta 
utilizzando il pulsante sinistro. Il pulsante con l'icona a forma di occhio (a destra) nasconde completamente la barra 
del mixer (è possibile riattivarla in un secondo momento).

{{< figure alt="strip top" src="it/ardour8-narrow-wide-strip.png" >}}

È facile individuare le differenze tra la modalità stretta e quella normale: didascalie più brevi sui pulsanti, nessuna 
legenda per il misuratore di picco, ecc.

### Nome traccia e pulsante di instradamento

Proseguendo dall'alto verso il basso, la sezione successiva della barra del mixer contiene tre piccole aree. 
La prima di queste aree mostra il nome della traccia (ovvero la parola "Audio 1" nell'immagine sottostante). L'area 
successiva, denominata "FL" nell'immagine sottostante, è un pulsante che consente di accedere all'instradamento 
dell'ingresso. Per ulteriori informazioni sul routing degli ingressi, consultare i capitoli _Comprendere il routing_ e
_Registrare l'audio_. L'ultima area stretta controlla l'inversione di fase (non approfondiremo questo argomento in 
questo tutorial).

{{< figure alt="strip 2" src="it/ardour8-mixer-strip-2.png" >}} 

### Casella del processore

L'ampia area nera nella parte inferiore di questa sezione è la _casella del processore_. È qui che è possibile, ad 
esempio, aggiungere plugin. Il flusso del segnale nella striscia del mixer è dall'alto verso il basso. Inizia con 
l'ingresso in alto, il plugin più in alto nella casella è il primo nella catena degli effetti, quello in basso è 
l'ultimo applicato.

Il box del processore conterrà sempre un processore fader blu. Questo indica dove si trova il fader del canale 
principale nella catena del processore: si tratta del fader mostrato nella metà inferiore della barra. Per una 
discussione dettagliata su questo argomento, consultare _Utilizzo dei plugin_ e _Utilizzo dei send_.

{{< figure alt="vista e controlli in linea" src="it/ardour7-inline-views-and-controls.png" >}}

Nella casella del processore sono disponibili ulteriori visualizzazioni e controlli, come mostrato nella schermata sopra:

1. _Visualizzazione in linea_. Alcuni plugin possono visualizzare una mini-panoramica delle loro impostazioni, ad esempio un 
equalizzatore può visualizzare un'anteprima di come vengono influenzate le varie bande di frequenza. Alcuni plugin sono 
stati scritti proprio con questo obiettivo: fornire una rapida panoramica di qualcosa nella barra del mixer. Ardour è 
dotato di due plugin di questo tipo, uno scope in linea e uno spettrogramma in linea.

3. _Controlli plugin_. È possibile aggiungere controlli a vari plugin in una barra del mixer. In questo modo, per le 
impostazioni che modifichi più spesso, non è necessario aprire ogni volta la finestra di un plugin, ma è sufficiente 
trascinare un cursore verso sinistra o destra o scorrere la rotellina quando si passa con il mouse su un controllo. 
Premi **Ctrl** per ottenere incrementi più piccoli durante il trascinamento o lo scorrimento.

Per controllare entrambe queste funzioni, usa il sottomenu _Controlli_ nel menu contestuale di un plugin. Poiché le 
visualizzazioni in linea sono abilitate per impostazione predefinita, tutto ciò che puoi fare è disabilitarle 
(e poi riabilitarle). Per abilitare un controllo per un plugin, basta cliccare sul suo nome nel menu.

{{< figure alt="Sottomenu controlli in Ardour 8" src="it/ardour8-plugin-controls-submenu.png" >}}

{{< callout type="info" >}}
Per abilitare più controlli per un plugin, il modo più comodo è aprire il menu contestuale, posizionare il cursore su 
un controllo e premere **la barra spaziatrice** sulla tastiera, posizionare il cursore sul controllo successivo, premere
nuovamente **la barra spaziatrice** e così via.
{{< /callout >}}

La parte successiva della barra del mixer include, tra gli altri, controlli per il panning, la registrazione, il mute e 
il solo.

### Panning

Il panning riguarda comunemente il posizionamento dei suoni in qualsiasi punto tra gli altoparlanti sinistro e destro 
per aiutare a separare gli strumenti l'uno dall'altro collocandoli in diverse parti di una stanza virtuale.

A seconda del numero di canali presenti in una traccia, Ardour fornirà un'interfaccia utente dedicata per controllare il
panning. Nella schermata sottostante, una traccia mono è sulla sinistra e una traccia stereo è sulla destra:

{{< figure alt="Mono vs. stereo panning" src="it/ardour7-mono-vs-stereo-panning.png" >}}

Per ulteriori informazioni, consultare il capitolo _Panning_.

### Soloing and Muting

Tracks and busses can have two additional related states: soloing and being
muted.

Any track or bus on _mute_ will be inaudible through the _Master_ bus or the
_Audition_. The track mixer also contains a miniaturized **Mute** button, in
between the **Record Arm** button and the **Solo** button. Right-clicking on the
**Mute** button gives you advanced options for the behavior of the mute button.

![Mute button in on and off states](en/ardour7-mute.png?width=20vw)

When a track or a bus is _soloing_, all the other tracks and busses are
inaudible through the _Master_ bus or the _Audition_, unless you solo them. So
if you need to play just two tracks out of eight, you don't have to mute six
other tracks, you only need to solo those two. Please note that soloing a bus
will not silence any tracks and vice-versa. 

![Solo button](en/ardour7-solo.png?width=20vw)

When any track or bus is on solo, the _solo indicator_ in the _Auxiliary
Controls_ menu will flash red. Clicking the solo indicator while it is flashing
will deactivate every solo in the session.

![Soloing](en/ardour7-soloing-flash-button.png?width=40vw)

### Arm Record

The _Rec_ button arms the track for recording, as seen in the _Recording Audio_ chapter.

![Arm for recording](en/ardour7-arm-rec.png?width=20vw)

### Fader, Fade/Peak Meters

The most prominent control present in a mixer strip is the _fader_, used to
adjust the overall gain for the corresponding track or bus. The _peak meter_
shows the _peak value_ of the selected track, and is located directly to the
right of the fader. Each peak meter consists of one _bar graph_ in the case of a
mono track, and two bar graphs in case of a stereo track. The small rectangular
field above the meters shows the highest peak value that has been played on that
track so far.

{{< figure alt="strip 7" src="en/Ardour4_Mixer_Strip_5.png" >}} 

By clicking the right-hand button at the bottom of the mixer strip (it reads
"post" in the image above), you will be able to select the _metering point_, for
example the direct "in" from the sound card, the "pre" Fader signal, or the
"post" fader signal.

As you can see in the image below, there is a smaller version of the mixer strip
in each track, called the _track mixer_, which contains a horizontal fader, a
vertical peak meter, as well as miniature buttons for arm record, mute, and
solo. They all mirror those found in the mixer strip for that track.

{{< figure alt="strip 6" src="en/Ardour4_Mixer_Strip_6.png" >}} 

Please refer to the chapter on _Mixing Levels_ for more detailed instruction
about using the fader and peak meters.

### Routing

Finally, we reach the bottom of the mixer strip. Here we find the **Output
Routing** button, marked as "Master" in the earlier screenshot, because it
connects to a bus called "Master". This was discussed earlier in the
_Understanding Routing_ chapter.

## Continuing

Now that we've had a look at the main areas of the mixer strip, we can proceed
to the _Mixing Levels_ chapter to see how we can start to use it. 

Next: [MIXING LEVELS](../mixing-levels)
