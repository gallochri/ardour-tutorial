---
title: Modifica non distruttiva
description: Che cos'è l'editing non distruttivo e come funziona in Ardour?
weight: 1
cascade:
  type: docs
---

In uno dei capitoli precedenti abbiamo già discusso del fatto che Ardour opera su sessioni che comprendono tutto il 
materiale a vostra disposizione: clip audio, clip MIDI, tutti gli effetti applicati alle tracce e ai bus, ecc. 
Prima di passare alla modifica vera e propria, parliamo delle basi della modifica non distruttiva, di come è 
implementata in Ardour e del motivo per cui dovrebbe darvi tranquillità quando effettuate modifiche complesse.

## Cosa significa realmente "editing non distruttivo"?

In poche parole, un approccio non distruttivo all'editing significa questo: qualunque cosa tu faccia, il materiale di 
partenza rimane sempre intatto. Invece di scrivere sui file originali, un programma descrive le modifiche applicate, 
le memorizza in un file di progetto e poi le "riproduce" quando carica quel progetto.

## Come funziona in Ardour?

Ecco un rapido esempio. Registriamo un breve clip audio, tagliamolo a metà e poi trasciniamo la metà destra verso destra
creando uno spazio vuoto:

{{< figure src="it/non-destructive-editing-cut-move-example.gif" alt="Taglio e spostamento di una regione audio" >}}

Ecco cosa succede effettivamente. Ardour crea una regione che fa riferimento al file audio originale e utilizza tutti i
suoi dati, dal primo all'ultimo campione.

Quando dividi il file in due, Ardour crea due regioni, entrambe riferite al file originale. Ma ora il file di progetto 
dice: la regione sinistra inizia in questo punto temporale, comincia con il primo campione del file originale e termina 
con quel campione al centro, mentre la seconda regione inizia in un punto temporale diverso con quel campione al centro 
del file originale, per poi terminare con l'ultimo campione del file originale.

È possibile tagliare una regione audio in tanti clip più piccoli quanti se ne desidera, spostarli tra le tracce, 
modificare i loro punti di inizio/fine, allungarli o accorciarli, ecc. Il file audio originale non subirà alcuna 
modifica sul disco.

Quando salvi un progetto, tutte queste informazioni vengono conservate nel file di sessione. Quando riapri la sessione, 
Ardour legge tutti questi riferimenti, carica i file originali e ricrea tutte le regioni audio modificate dai file audio
originali. Questo è ciò che significa realmente "riprodurre le modifiche".

Se non ti piace il modo in cui hai modificato una registrazione originale e sei troppo avanti con il montaggio per 
annullare le modifiche, puoi ricominciare da capo senza registrare una nuova traccia. Per farlo, puoi aprire la barra 
laterale destra premendo **Shift+L**, andare alla scheda _Sorgenti_, prendere il nome del file audio originale della 
registrazione, trascinarlo su qualsiasi traccia e poi spostarlo, tagliarlo, ecc.

{{< figure src="it/non-destructive-editing-redo-all-over-again.gif" alt="Rifare tutta la modifica da capo" >}}

Inoltre, anche gli effetti applicati a una traccia sono non distruttivi. Ardour li applicherà al flusso audio originale 
e riprodurrà il risultato in tempo reale.

Nel caso di clip MIDI riprodotte tramite un sintetizzatore, Ardour utilizzerà il sintetizzatore per rendere un flusso 
di dati audio mentre il cursore di riproduzione è in movimento, acquisirà tale flusso audio, applicherà effetti e 
quindi riprodurrà il flusso audio risultante man mano che procedi.

## Differenze tra regioni audio e MIDI

Come già sapete, i file audio rimangono sempre intatti. Ma le regioni MIDI sono diverse: è possibile modificarne il 
contenuto e le modifiche vengono salvate nei file MIDI sul disco.

Un caso in cui ciò è importante è quando si desidera combinare più regioni in una sola. È possibile farlo con le regioni
audio selezionando quelle che si desidera unire e utilizzando `Regione > Modifica > Combina`. In questo modo si creerà 
una sorta di meta-regione che fa riferimento a N file audio sul disco.

Tuttavia, non è possibile fare lo stesso con le regioni MIDI, principalmente perché sono modificabili su disco e quindi
combinare qualcosa che può cambiare fisicamente può compromettere la continuità dei dati.

## Dove viene archiviato il materiale sorgente di Ardour?

Consideriamo questo progetto generico. Abbiamo diverse tracce audio che rappresentano la batteria, due tracce audio per
il basso e la chitarra solista e una traccia MIDI per il pianoforte elettrico.

{{< figure src="it/non-destructive-editing-session-example.png" alt="Esempio di sessione" >}}

Se vai nella cartella della sessione, troverai una serie di sottocartelle, tra cui queste due:

- `interchange`, qui è dove vengono memorizzati i file audio e MIDI sorgente;
- `plugins`, Qui Ardour salva lo stato di ogni istanza di ogni plugin utilizzato nel progetto.

Quando registri uno strumento, ogni registrazione viene rappresentata da un file audio fisico per canale. Quindi, se hai
effettuato tre registrazioni in una traccia stereo, avrai 6 file audio.

## Ardour modifica mai i dati audio sul disco?

L'unica volta in cui Ardour interviene sui file audio effettivi presenti sul disco è quando gli si chiede esplicitamente
di rimuovere i file audio che non vengono utilizzati in nessuna parte del progetto. In genere ciò avviene quando si sono
effettuate decine di registrazioni, si è fatta la propria scelta e non si desidera più avere questi file sul disco 
perché occupano spazio.

Anche in questo caso, l'operazione si svolge in due fasi. Innanzitutto, vai su 
`Sessione > Pulizia > Pulisci sorgenti inutilizzate...` per spostare i file originali inutilizzati nel cestino, quindi 
vai separatamente su `Sessione > Pulizia > Svuota cestino` per indicare effettivamente ad Ardour di rimuovere 
fisicamente i file inutilizzati.

**Continua**

Ora che avete familiarità con le basi dell'editing non distruttivo, passiamo all'arrangiamento e all'editing vero e 
proprio.