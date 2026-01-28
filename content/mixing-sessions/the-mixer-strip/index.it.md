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

### Nome traccia e pulsante di instradamento ingresso

Proseguendo dall'alto verso il basso, la sezione successiva della barra del mixer contiene tre piccole aree. 
La prima di queste aree mostra il nome della traccia (ovvero la parola "Audio 1" nell'immagine sottostante). L'area 
successiva, denominata "FL" nell'immagine sottostante, è un pulsante che consente di accedere al routing (instradamento)
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

### Solo e Muto

Le tracce e i bus possono avere due stati aggiuntivi correlati: solo e muto.

Qualsiasi traccia o bus su _muto_ non sarà udibile attraverso il bus _Master_ o l'_Audition_. Il mixer della traccia 
contiene anche un pulsante **Muto** in miniatura, situato sotto il pulsante **Iso** vicino al pulsante **Solo**. 
Cliccando con il tasto destro del mouse sul pulsante **Muto** si accede alle opzioni avanzate relative al comportamento 
del pulsante mute.

{{< figure alt="Pulsante Mute in stato attivo e disattivo" src="it/ardour8-mute.png" >}}

Quando una traccia o un bus sono in modalità _Solo_, tutte le altre tracce e i bus non sono udibili attraverso il bus 
_Master_ o l'_Audition_, a meno che non vengano messi in modalità solo. Quindi, se è necessario riprodurre solo due 
tracce su otto, non è necessario silenziare le altre sei tracce, ma è sufficiente mettere in modalità _Solo_ quelle due.
Si noti che mettere in modalità solo un bus non silenzierà alcuna traccia e viceversa.

{{< figure alt="Pulsante Solo in stato attivo e disattivo" src="it/ardour8-solo.png" >}}

Quando una traccia o un bus è in modalità solo, l'indicatore _Solo_ nel menu Controlli ausiliari lampeggerà in rosso. 
Cliccando sull'indicatore _Solo_ mentre lampeggia si disattiveranno tutte le modalità _Solo_ nella sessione.

{{< figure alt="Indicatore Solo lampeggiante" src="it/ardour8-soloing-flash-button.png" >}}

### Armare la registrazione

Il pulsante _Rec_ attiva la traccia per la registrazione, come illustrato nel capitolo _Registrazione audio_.

{{< figure alt="" src="it/ardour8-arm-rec.png" >}}

### Fader, Misuratori di attenuazione/picco

Il controllo più importante presente in una striscia del mixer è il _fader_, utilizzato per regolare il guadagno 
complessivo della traccia o del bus corrispondente. Il _misuratore di picco_ mostra il _valore di picco_ della traccia 
selezionata e si trova direttamente a destra del fader. Ogni misuratore di picco è costituito da un _grafico a barre_ 
nel caso di una traccia mono e da due grafici a barre nel caso di una traccia stereo. Il piccolo campo rettangolare 
sopra i misuratori mostra il valore di picco più alto che è stato riprodotto su quella traccia fino a quel momento.

{{< figure alt="strip 7" src="it/ardour8-mixer-strip-5.png" >}} 

Cliccando sul pulsante a destra nella parte inferiore della barra del mixer (nell'immagine sopra è indicato con la 
dicitura "post"), potrai selezionare il _punto di misurazione_, ad esempio l'ingresso diretto dalla scheda audio, il 
segnale "Pre" Fader o il segnale "Post" Fader.

Come puoi vedere nell'immagine sottostante, in ogni traccia è presente una versione ridotta della barra del mixer, 
chiamata _mixer di traccia_, che contiene un fader orizzontale, un misuratore di picco verticale e pulsanti in miniatura
per l'attivazione della registrazione, il muto e il solo. Tutti questi elementi rispecchiano quelli presenti nella 
striscia del mixer per quella traccia.

{{< figure alt="strip 6" src="it/Ardour4_Mixer_Strip_6.png" >}}

Per istruzioni più dettagliate sull'uso dei fader e dei misuratori di picco, consultare il capitolo sui 
_livelli di mixaggio_.

### Routing

Infine, arriviamo alla parte inferiore della striscia del mixer. Qui troviamo il pulsante **USCITA**, 
contrassegnato come "Master" nella schermata precedente, perché la traccia si collega al bus "Master". Questo argomento 
è stato trattato in precedenza nel capitolo _Comprendere il routing (instradamento)_.

## Continua

Ora che abbiamo dato un'occhiata alle principali aree della barra del mixer, possiamo passare al capitolo 
_Livelli di mixaggio_ per vedere come iniziare a utilizzarlo.

Successivo: [Livelli di Mixaggio](../mixing-levels)
