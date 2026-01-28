---
title: Utilizzo dei plugin
description: Come utilizzare i plugin in Ardour
weight: 4
cascade:
  type: docs
---

I _plugin_ possono essere utilizzati per migliorare o trasformare il suono delle singole tracce.

Possono essere applicati direttamente a una singola traccia o a un gruppo di tracce utilizzando un _send_. Più avanti 
in questo tutorial, discuteremo alcuni plugin specifici per il processo di mixaggio, come _Compressori_, _Limitatori_, 
_Equalizzatori Parametrici_, _Riverberi_ e altri.

## Casella del processore

Nella terminologia di Ardour, un _processore_ è qualsiasi cosa che viene collegata a una barra del mixer e tratta il 
segnale in qualche modo. Ardour fornisce diversi processori integrati, come il fader o i panner. I processori possono 
anche essere plugin utilizzati per effetti o come strumenti, nonché invii o inserti che influenzano l'instradamento 
del segnale. La disposizione dei processori è arbitraria e non vi è alcun limite al loro numero.

{{< figure alt="Casella del Processore predefinita" src="it/ardour7-default-processor-box.png" >}}
 
Lo spazio principale mostrato nella schermata sopra è la _casella del processore_. Il fader della casella blu è in 
realtà un _processore_ che viene fornito di default all'interno della casella del processore. Rappresenta il fader che 
si utilizza per controllare il volume della traccia. Tutti i processori sono visualizzati come rettangoli colorati, con
un piccolo "LED" accanto che si illumina quando il processore è abilitato. Il colore del processore dipende dalla sua 
posizione nella sequenza; i processori pre-fader sono colorati in rosso, mentre quelli post-fader sono colorati in verde.

## Aggiungere un plugin a una traccia o a un bus

I plugin possono essere aggiunti facendo clic con il tasto destro del mouse nella casella del processore della traccia o
del bus. Viene visualizzato un menu di opzioni. Dal menu è possibile inserire nuovi processori.

{{< figure alt="plugins1" src="it/ardour8-plugin-selector-in-menu.png" >}}

Il _Selettore plugin_ è un modo pratico per sfogliare e scegliere i plugin:

{{< figure alt="plugins2" src="it/ardour8-plugin-selector.png" >}}

Dal _Selettore plugin_, è possibile cercare i plugin per nome, tipo o altri criteri disponibili dal menu a tendina. 
Aggiungiamo il plugin di riverbero chiamato _ACE Reverb_:

{{< figure alt="Selezione  ACE Reverb" src="it/ardour8-select-ace-reverb.png" >}}

Una volta selezionato, clicca su **+Add** e il plugin apparirà nell'elenco in basso dei "Plugin da collegare". 
Quindi clicca su **Inserisci plugin** e questi appariranno nella casella del processore.

{{< figure alt="Plugin riverbero" src="it/ardour8-ace-reverb-added-to-processor-box.png" >}}

## Modifica dei parametri del plugin

Fai doppio clic su un plugin per modificarne i parametri. In questo esempio, facciamo doppio clic sulla casella rossa 
"ACE Reverb" e otteniamo questa finestra:

{{< figure alt="Impostazioni ACE Reverb" src="it/ardour8-ace-reverb-settings.png" >}}

Qui è possibile controllare i parametri del riverbero, come _Blend_ e _Room Size_. L'effetto verrà applicato a tutti i 
suoni contenuti nella traccia.

{{< callout type="info" >}}
Fai doppio clic su un cursore per passare alla modalità di immissione numerica, digita il nuovo valore, quindi premi 
**Invio** per confermare la modifica o **Esc** per annullarla.
{{< /callout >}}

## Bypassare i plugin

Per bypassare il plugin, premi il pulsante **Bypass** nella finestra delle impostazioni del plugin, oppure clicca 
semplicemente sul LED del plugin nella casella del processore. In questo modo il plugin viene disattivato e il segnale 
lo attraversa senza subire alcuna modifica. Ciò è utile quando si desidera confrontare il suono di una traccia con e 
senza il plugin.

{{< figure alt="bypass" src="it/ardour8-ace-reverb-bypass-in-mixer-strip.png" >}}

I plugin bypassati vengono visualizzati con il LED spento. Nella schermata sopra, il fader è abilitato e il plugin 
_ACE Reverb_ è bypassato.

Cliccando con il tasto destro sui plugin apparirà un menu con diverse opzioni, tra cui _Elimina_.

## Pre-Fader contro Post-Fader

È possibile scegliere se aggiungere il plugin prima o dopo il fader nella _casella del processore_. I plugin pre-fader 
vengono inseriti nel percorso del segnale *prima* del fader, in modo che il fader controlli il livello del segnale in 
uscita dal plugin. I plugin post-fader vengono inseriti *dopo* il fader: il fader controlla il livello del segnale in 
entrata nel plugin.

Per alcuni plugin, il posizionamento pre o post fader non ha importanza. Per altri, la differenza è minima. Per altri 
ancora, inserirli nel posto giusto è assolutamente essenziale (per maggiori dettagli, vedere ad esempio 
[questo thread](https://discourse.ardour.org/t/fader-before-or-after-plugins/100666) sul forum di discussione di Ardour).

## Formati plugin

Per chi fosse interessato ad approfondire la conoscenza dei formati dei plugin, ecco una breve panoramica:

**Plugin LADSPA** sono un formato di plugin piuttosto obsoleto utilizzato principalmente su Linux.

**LV2** è un successore estensibile di LADSPA. I plugin LV2 sono disponibili su Linux, Windows e macOS, qualora i 
rispettivi sviluppatori decidessero di crearli per questi sistemi.

**Plugin AU** sono il formato plugin nativo per macOS e funzionano solo su quel sistema operativo.

**Plugin VST** è piuttosto comune sia su Windows che su macOS. Alcuni plugin VST creati per Windows possono essere 
utilizzati su Linux, tuttavia potrebbero non funzionare correttamente e richiedere software di terze parti per essere 
eseguiti. Altri sono creati in modo nativo per Linux e tendono a funzionare bene.

Maggiori informazioni sull'uso dei plugin con Ardour sono disponibili 
[nel manuale utente].(http://manual.ardour.org/working-with-plugins/).

## Continua

In questo capitolo abbiamo imparato come aggiungere un plugin a una singola traccia. Ciò è utile se quella traccia 
necessita di un plugin specifico, ma se avete un plugin che venga utilizzato per più tracce contemporaneamente, dovreste
passare al capitolo successivo sull'uso dei send. Potete anche passare ai vari capitoli specifici sui plugin, come 
_Dinamica_ ed _Equalizzazione_.

Successivo: [Utilizzo dei send](../using-sends)
