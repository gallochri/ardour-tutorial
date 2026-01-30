---
title: Utilizzo dell'automazione
description: Come creare e modificare l'automazione in Ardour
weight: 8
cascade:
  type: docs
---

L'_automazione_ è un modo per modificare dinamicamente i parametri di elaborazione audio nel tempo.

Finora abbiamo utilizzato valori fissi per vari parametri delle nostre tracce, ad esempio un fader di traccia impostato 
su -3,0 dB o un panner mono impostato al 100% a sinistra. Questi valori fissi si applicano all'intera traccia per tutta 
la sessione.

Ma cosa succede se desideri che questi valori cambino nel tempo in modo predeterminato? Ad esempio, potresti voler 
ridurre gradualmente il guadagno di una traccia nell'arco di venti secondi. Oppure potresti voler spostare un suono da 
sinistra a destra nell'arco di due secondi.

Questo risultato si ottiene grazie all'automazione. Il fader, il panning e tutti i parametri dei plugin utilizzati in 
quella traccia possono essere automatizzati. Un parametro automatizzato viene visualizzato sotto la traccia principale 
nella propria _traccia di automazione_. I dati di automazione sono rappresentati visivamente come una 
_linea di automazione_, composta da una serie di _punti di automazione_. Ecco come appare una traccia con automazione:

{{< figure alt="Tipica linea di automazione" src="it/ardour8-automation-fader-1.png" >}}

Nell'immagine sopra, la traccia di automazione denominata _Fader_ è associata alla traccia principale denominata 
_kick_. La linea di automazione controlla le variazioni del fader (volume) nel tempo.

## Creazione di una linea di automazione del fader

Creiamo una semplice automazione del fader. Clicca sul pulsante **A** della traccia scelta. Apparirà un menu in cui 
potrai selezionare il parametro che desideri automatizzare. Scegli _Fader_.

{{< figure alt="Scegli Fader" src="it/ardour8-automation-button.png" >}}

Apparirà quindi una barra di automazione. Seleziona la modalità _Matita_ (scorciatoia **D**):

{{< figure alt="Modalità matita" src="it/ardour8-edit-modes-d.png" >}}

Ora è possibile creare punti di automazione facendo clic in qualsiasi punto della corsia di automazione. Una linea di 
automazione unisce i punti di automazione aggiunti. Il numero giallo (-18,72 dB nell'immagine sottostante) indica il 
livello di guadagno per il punto di automazione selezionato.

{{< figure alt="Indicazione del valore del punto di automazione" src="it/ardour8-automation-fader-2.png" >}}

È possibile tracciare liberamente linee di automazione nella modalità matita. Basta cliccare, tenere premuto e tracciare
una linea di automazione libera:

{{< figure alt="Disegnare liberamente in modo automatico, prima di rilasciare il pulsante del mouse" src="en/ardour8-draw-automation-freely-pre-release.png" >}}

Una volta rilasciato il pulsante del mouse, vedrai molti punti di controllo dell'automazione, perché Ardour cerca di 
conservare il movimento esatto che hai fatto quando hai tracciato la linea.

{{< figure alt="Disegnare in modo automatico, dopo aver rilasciato il pulsante del mouse" src="en/ardour8-draw-automation-freely-post-release.png" >}}

Lo si può vedere quando si ingrandisce l'immagine:

{{< figure alt="Disegno automatico libero, ingrandito" src="en/ardour8-draw-automation-freely-zoomed.png" >}}

È anche possibile premere **Ctrl** e cliccare per creare linee rette:

{{< figure alt="Disegno di segmenti rettilinei di linee di automazione, pre-rilascio" src="en/ardour8-draw-automation-lines-pre-release.png" >}}

Questo creerà la seguente linea di automazione:

{{< figure alt="Disegno di segmenti rettilinei di linee di automazione, post-rilascio" src="en/ardour8-draw-automation-lines-post-release.png" >}}

È anche possibile combinare il disegno automatico libero con il disegno di linee. Basta premere **Ctrl** quando si 
desidera disegnare un segmento rettilineo e rilasciare il tasto quando il segmento rettilineo deve terminare, quindi 
continuare a disegnare una linea libera:

{{< figure alt="Una combinazione di segmenti liberi e diritti" src="en/ardour8-draw-automation-freely-with-lines-pre-release.png" >}}

### Stati di automazione

La curva di automazione non verrà riprodotta finché non si imposta lo stato di automazione su _Leggi_.

{{< figure alt="stato dell'automazione" src="it/ardour8-automation-fader-3.png" >}}

**Manuale**
: Quando è impostato su _Manuale_, la traccia ignorerà qualsiasi dato di automazione. Verrà riprodotta semplicemente con
il volume impostato sul fader. In questa modalità, è possibile spostare manualmente il fader della traccia per impostare
un nuovo livello fisso. Questo è il comportamento predefinito di una traccia quando viene creata per la prima volta.

**Leggi**
: Quando è impostato su _Leggi_, la traccia modificherà automaticamente i livelli di guadagno seguendo la curva di 
automazione tracciata nella linea di automazione. Non sarà più possibile spostare manualmente il fader della traccia. 
Durante la riproduzione, vedrai il fader della traccia muoversi su e giù in base alla curva.

**Scrivi**
: Questa modalità registra continuamente le modifiche apportate dall'utente al parametro automatizzato durante la 
riproduzione, creando una linea di automazione. Ad esempio, è possibile avviare la riproduzione e quindi apportare 
modifiche in tempo reale al guadagno utilizzando il fader della traccia. Tutte le modifiche apportate verranno scritte 
(registrate) come una linea di automazione, che quindi potrai riprodurre in un secondo momento riportando la modalità di
automazione su _Leggi_.

**Tocco**
: Questa modalità è simile alla modalità _Scrivi_, ma non sovrascriverà i dati di automazione esistenti a meno che il 
parametro non venga modificato.

**Azione**
: Questa modalità è simile alla modalità _Tocco_, ma modifica anche l'automazione quando il controllo viene modificato 
in qualche modo durante la riproduzione della sessione. Inoltre, sovrascrive la curva di automazione con l'ultimo valore
modificato fino all'interruzione della riproduzione.

Se questi concetti sono nuovi per te, concentrati ora solo sulle prime due modalità (_Manuale_ e _Leggi_) ed esercitati
a creare automazioni disegnando a mano le curve di automazione.

## Creazione di un plugin per l'automazione

È possibile aggiungere l'automazione a qualsiasi plugin già aggiunto a una traccia. Nell'esempio seguente, abbiamo 
aggiunto il plugin _AM pitchshifter_ a una traccia.

{{< figure alt="automazione plugin 1" src="it/ardour8-automation-plugin1.png" >}}

Per selezionare un parametro del plugin per l'automazione, clicca sul pulsante sulla traccia contrassegnato con _a_. 
Apparirà il menu. Sotto _Processor Automation_ troverai un elenco dei plugin che hai aggiunto per quella traccia.

{{< figure alt="automazione plugin 2" src="it/ardour8-automation-plugin2.png" >}}

All'interno di ciascun plugin elencato, è possibile scegliere da un elenco il parametro che si desidera automatizzare. 
Nell'esempio, abbiamo scelto il parametro _Pitch shift_ del plugin _AM pitchshifter_. Viene visualizzata una traccia di 
automazione per quel parametro. Si noti che quando si aprono diverse tracce di automazione, queste appariranno una dopo 
l'altra sotto la traccia principale.

Disegna una curva di automazione per quel parametro. Non dimenticare di impostare lo stato di automazione su _Leggi_.

{{< figure alt="automazione plugin 3" src="it/ardour8-automation-plugin3.png" >}}

Nell'immagine sopra, il cambiamento di tonalità del suono ora varia nel tempo, controllato dalla curva.

{{< callout type="info" >}}
È possibile nascondere una traccia di automazione facendo clic sulla "X" nell'angolo superiore sinistro della traccia 
stessa. Si noti che una traccia di automazione nascosta continua a funzionare anche quando non è visibile. 
{{< /callout >}}

## Migliorare la risoluzione visiva nell'automazione

È possibile ottenere una maggiore precisione verticale aumentando l'altezza della corsia di automazione. Spostare il 
cursore vicino al bordo inferiore della traccia di automazione. Il puntatore si trasforma in una doppia freccia 
verticale. Trascinarlo verso il basso per aumentare l'altezza della corsia di automazione. Si noti che le altezze della 
traccia principale e della corsia di automazione sono indipendenti, quindi mentre si lavora sulle curve di automazione è
possibile impostarle in questo modo:

{{< figure alt="automazione plugin 4" src="it/ardour8-automation-plugin4.png" >}}

{{< callout type="info" >}}
Ricorda che puoi anche ingrandire e rimpicciolire l'immagine per aumentare la risoluzione sull'asse orizzontale.
{{< /callout >}}

## Working with Automation Points

There are several ways to adjust automation points, depending on the editing
mode you are in:

- An automation point can be dragged in any direction with the mouse (works in
_Grab_, _Draw_, and _Edit_ modes).
- To remove an automation point, hold down the **Shift** key while
right-clicking on it (works in _Grab_, _Draw_, and _Edit_ modes).
- _Edit_ mode only: any segment of the automation line between automation points
may be dragged vertically, affecting both end points at once, without affecting
their horizontal position. Simply click somewhere on the line between two
points, and drag up and down.
- How to delete multiple automation points at once (_Grab_ mode and _Edit_ mode
only): select multiple automation points by dragging a box starting on the track
background around the points. Then the selected points may be deleted by hitting
**Delete** (_not_ **Backspace**). If you are on a Mac and do not have a true
**Delete** key, try **Function + Backspace**.

After an automation curve ends, its value will stay at that level for all
subsequent regions, whether or not you have drawn a continuation of the curve.

{{< figure alt="end point" src="en/Ardour4_Automation_Fader_End.png" >}}

In the example above, the last point of the curve is at -23dB. That same level
will be kept for the remainder of the track, even though the line is not drawn
until the end.

## Moving Automation

Moving a region to a new location will automatically move the automation data
that might be aligned with it, as we can see in the following screen shots.

Before moving:

{{< figure alt="mv1" src="en/Ardour4_Automation_Moving_1.png" >}}

After moving:

{{< figure alt="mv2" src="en/Ardour4_Automation_Moving_2.png" >}}

You can change this behavior if you like. In other words, if you want automation
curves to stay where they are even when you move regions around, go to `Edit >
Preferences > Editor` and uncheck _Move relevant automation when audio regions
are moved_.

## Region-specific Gain Automation

There is a way to create a gain automation directly bound to a region. When you
select the _Draw_ mode, you should see a flat line on the top half of each
region rectangle:

{{< figure alt="gain-automation" src="en/Ardour4_Automation_Region_Specific_1.png" >}}

Click directly on that line to create automation points. These will be drawn
directly on the region itself, unlike fader automation which is drawn or
recorded in the automation lane. Region gain automation is separate from, and
in addition to, fader automation.

{{< figure alt="gain-automation2" src="en/Ardour4_Automation_Region_Specific_2.png" >}}

As with the automation lanes, a _gain automation point_ can be dragged in any
direction with the mouse. To remove a gain automation point, hold down the
**Shift** key while right-clicking on it.

### Deactivating and Removing Gain Automation

Gain automation can be reset or deactivated from the region context menu, which
is reached by right-clicking on the region.

{{< figure alt="gain-automation3" src="en/Ardour4_Automation_Gain_Tool_Reset.png" >}}

Here, the gain automation is referred to as the _envelope_:

- _Reset Envelope_ removes the gain automation points you have drawn in the
region.
- _Envelope Active_ toggles the gain automation envelope on and off.

### When should I use region Gain Automation or Track Fader Automation?

As seen above, both are very similar. With practice you will notice situations
in which one is more convenient than the other. Here are two examples:

* If all you need to do is a little touch up (cut or boost gain) in a specific
portion of a region, and you are otherwise happy with the level for the rest of
the passage or entire track, use the region-specific automation.

{{< figure alt="gain-example1" src="en/Ardour4_Automation_Region_Specific_2.png" >}}

* If you have a more complex track with crossfades over regions, and/or need to
shape a longer dynamic curve across several regions on the same track, use fader
automation.

{{< figure alt="gain-automation2" src="en/Ardour4_Automation_Gain_Comparison.png" >}}

The screenshot above shows a simple gradual fade starting from the first region
in the track, and ending at the last region. It's very straightforward to do
this with fader automation, but it would be much harder to do it using
region-specific automation.

## Continuing

Once you have your automation in place, you are just about ready to export your
stereo mix to an audio file which you can listen to or share on a website.
Please continue on to the next section to learn the different ways of doing
this.

Successivo: [Esportazione di una sessione](../../exporting-sessions/exporting-a-session)
