---
title: Livelli di mixaggio
#description: FIXME
weight: 2
cascade:
  type: docs
---

I _livelli_ sono i volumi di ciascuna traccia rispetto alle altre.

Se non riesci a sentire la linea di basso sopra gli altri strumenti, un'opzione ovvia sarebbe quella di alzare il volume
della linea di basso. I livelli possono essere regolati utilizzando il fader nella barra del mixer o in ogni traccia, 
proprio sotto il nome della traccia. Il primo passo nel missaggio è ascoltare tutto ciò che è stato registrato e 
regolare i livelli di tutte le tracce in modo da poter sentire tutto chiaramente, ma in modo appropriato per la canzone.
Ad esempio, la traccia vocale è normalmente più forte della chitarra ritmica perché la voce è il punto focale della 
canzone.

## Utilizzo del fader

Il fader è il controllo principale dei livelli per ogni traccia. Il valore esatto dei livelli della traccia è 
visualizzato nel piccolo campo rettangolare sopra il fader. È possibile modificare i livelli trascinando il cursore o 
digitando un nuovo numero direttamente nel rettangolo.

Per impostazione predefinita, il fader è impostato su −0,0 dB, il che significa che i livelli della traccia non vengono
modificati. Nella schermata sottostante, il fader della traccia denominata "kick" è impostato su -0,0 e il misuratore di
picco indica che il picco più alto raggiunto finora è stato di -8,3 dB.

{{< figure alt="levels1" src="it/ardour8-mixing-levels-1.png" >}} 

## Evitare il clipping

Un altro compito importante nel mixaggio è evitare il clipping. Il valore di picco sulla barra del mixer diventa rosso 
quando il segnale ha superato i 0,0 dB. È possibile utilizzare questo strumento per monitorare i livelli più alti della 
traccia durante il mixaggio. 

Nello screenshot qui sotto, la traccia clap ha appena raggiunto il clipping a +0.4. È anche possibile 
vedere dei piccoli bordi rossi sulla forma d'onda stessa, che indicano i punti esatti in cui il suono registrato ha r
aggiunto il clipping.

{{< figure alt="levels2" src="it/ardour8-mixing-levels-2.png" >}}

Clicca sul numero rosso nel misuratore di picco per azzerarlo.

{{< callout type="info" >}}
Ai fini dell'esercizio, prova a registrare la tua voce in modo che risulti distorta. Ascolta come viene riprodotta la 
registrazione.
{{< /callout >}}

È necessario assicurarsi che qualsiasi cosa inviata alla scheda audio o che verrà esportata come file audio (ad esempio 
per il mastering di un CD) non superi **mai** i 0,0 dB per evitare il clipping effettivo.

Se il clipping si verifica in un suono molto percussivo ed è quasi impercettibile, è possibile nasconderlo diminuendo 
il guadagno (ad esempio, normalizzando la regione a 0,0 dB o a un valore inferiore come -1,0 dB). Tuttavia, spesso il 
clipping provoca una distorsione udibile del suono registrato. La soluzione migliore in questo caso è semplicemente 
registrare di nuovo con livelli più bassi.

## Continua

Una volta completato questo capitolo del tutorial, dovresti avere una serie di tracce i cui livelli sono ben regolati 
tra loro e non si sovrappongono quando vengono aggiunte insieme nel bus _Master_. Una volta fatto questo, possiamo 
passare al capitolo successivo per imparare il panning, in modo che il nostro mix acquisisca un forte senso di spazio 
stereo.

Successivo: [Panning](../panning)
