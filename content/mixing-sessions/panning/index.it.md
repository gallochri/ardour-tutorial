---
title: Panning
description: Come usare il panning in Ardour
weight: 3
cascade:
  type: docs
---

Una volta stabilito un buon equilibrio dei livelli su tutte le tracce, puoi iniziare a pensare al panning.

Il panning aiuta a creare un _campo stereo_, uno spazio relativo tra gli altoparlanti in cui collocare i suoni e gli 
strumenti.

## L'interfaccia del panning

Il controllo del panning in Ardour si trova al centro della barra del mixer.

Una traccia mono avrà un panner mono con questo aspetto:

{{< figure alt="Mono panner" src="it/ardour7-mono-panner.png" >}}

Una traccia stereo avrà un panner stereo, come questo:

{{< figure alt="Stereo panner" src="it/ardour7-stereo-panner.png" >}}

### Panner Mono

Il panner mono predefinito distribuisce 1 ingresso a 2 uscite. Il suo comportamento è controllato da un unico parametro,
la *posizione*. Per impostazione predefinita, il panner è centrato. È possibile modificare la posizione cliccando e 
trascinando direttamente sul panner mono l'indicatore. Cliccare con il tasto destro del mouse sul panner per accedere ad
altre opzioni.

### Panner Stereo

Il panner stereo predefinito distribuisce 2 ingressi a 2 uscite. Per impostazione predefinita, anche il panner è 
centrato.

## Trucchi per il panning

Una discussione più approfondita sulla filosofia e sulle tecniche di panning va oltre lo scopo di questo tutorial, ma 
ecco alcune regole generali:

* Le chitarre tendono a essere posizionate a sinistra e a destra. 
* La voce e il basso tendono a essere posizionati al centro. È importante creare un equilibrio in modo che un lato 
non sia più forte dell'altro. 
* Le cuffie possono essere utili per determinare come posizionare gli strumenti e se il mix risulta sbilanciato perché 
un lato è troppo forte.

Altri due strumenti utili per creare un campo "spaziale" o stereo sono _Riverbero_ e _Delay_. Questi effetti possono 
essere utilizzati insieme ai send per creare un send di batteria che risulterebbe più arretrato nel mix con più 
riverbero, e un send vocale che potrebbe avere un po' più di delay ma suonare più vicino rispetto alla batteria. Per 
ulteriori informazioni, consulta le sezioni sull'uso dei plugin e dei send più avanti in questa parte del tutorial.

{{< callout type="info" >}}
Tieni sempre sotto controllo i livelli mentre esegui il panning delle tracce! Il panning di una traccia su un canale 
aumenta il livello di quel canale. Ciò potrebbe modificare il bilanciamento dei livelli impostato nel capitolo 
precedente e, in casi estremi, causare il clipping. Quando ciò accade, riduci i livelli complessivi di quella traccia e
ricontrolla come si inserisce nel mix.
{{< /callout >}}

## Multichannel Panning

Poiché Ardour supporta tracce multicanale, fornirà anche un'interfaccia utente di panning specifica per tali tracce. 
Ecco un esempio di traccia audio a 4 canali. È possibile notare una piccola interfaccia utente proprio nel mixer e una 
finestra di editing più grande a cui è possibile accedere facendo clic in un punto qualsiasi dello spazio vuoto 
all'interno dell'area di panning:

{{< figure alt="Panning multicanale" src="it/ardour8-multichannel-panning.png" >}}

A meno che non lavoriate su progetti che prevedono l'uso, ad esempio, dell'Ambisonics 
(https://en.wikipedia.org/wiki/Ambisonics), quando utilizzate i campionatori, in particolare quelli per 
batteria/percussioni, avrete probabilmente a che fare principalmente con tracce multicanale. Poiché i diversi strumenti
di una batteria tendono ad avere un trattamento diverso in post-produzione (ad esempio, il modo in cui vengono elaborati
con un compressore), i campionatori tendono a creare un canale per ogni strumento: uno per la grancassa, uno per ogni 
rullante, ecc. L'idea è quella di indirizzare un canale in un bus separato ed elaborarlo in modo diverso. In questo 
caso, è improbabile che si utilizzi un controllo panner.

## Continua

A questo punto dovresti avere una raccolta di tracce ben mixate e con un'immagine stereo entusiasmante. Nei capitoli 
seguenti impareremo a utilizzare i plugin per migliorare il suono del tuo mix.

Successivo: [Utilizzo dei plugin](../using-plugins)
