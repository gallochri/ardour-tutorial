---
title: Eseguire a tempo
description: Come aiutarti a registrare a tempo con il resto del materiale della sessione
weight: 4
cascade:
  type: docs
---

Normalmente, per registrare uno strumento o una parte vocale dal vivo, si posiziona il cursore di riproduzione in una 
determinata posizione, si prepara una traccia per la registrazione, si attiva la modalità di registrazione generale e 
poi si avvia il trasporto quando si è pronti. La registrazione inizierà dalla posizione del cursore di riproduzione e 
si ascolterà la parte udibile del materiale della sessione che inizia anch'essa da quel punto. Ci sono due 
considerazioni importanti da fare a questo proposito.

## Usare un metronomo

Potresti non avere ancora la parte ritmica del materiale che ti guidi durante la registrazione. Quindi, se ti senti a 
tuo agio nell'eseguire un brano con il metronomo per regolare il ritmo, puoi attivare il metronomo sulla barra degli 
strumenti di trasporto (o premere il tasto di scelta rapida **\`**).

Se i clic del metronomo non sono udibili, vai su `Finestra > Connessioni audio`, clicca su _Ardour Varie_ a sinistra e 
verifica che le porte _Click out_ siano collegate alle uscite hardware corrette (o a qualsiasi uscita). In questo modo i
clic del metronomo saranno udibili durante la registrazione e la riproduzione, ma non nel mix finale.

{{< figure src="it/click-out-ports.png" alt="Collegare le porte del click al bus master" >}}

Ci sono anche alcune opzioni di personalizzazione per il metronomo nella finestra di dialogo omonima _Preferenze_: 
enfatizzare (o meno) il primo battito, regolare il guadagno dei clic del metronomo, caricare i propri clic regolari ed 
enfatizzati, abilitare il metronomo solo durante la registrazione.

## Ascolto preliminare del materiale della sessione

Per eseguire meglio una parte, è utile ascoltare la parte della composizione che precede direttamente la nuova parte 
strumentale/vocale che si sta per registrare. Hai tre opzioni a disposizione:

1. Registra con rincorsa.

2. Registra con pre-conteggio.

3. Inizia a registrare con largo anticipo.

Le prime due opzioni sono simili. Ecco cosa fanno.

Rincorsa (`Trasporto > Registra con rincorsa` o **Shift+<**) significa che Ardour inizierà a riprodurre il materiale 
udibile della sessione prima del punto in cui si desidera iniziare la registrazione, quindi quando il cursore di 
riproduzione raggiunge il punto originale in cui si trovava, inizia la registrazione effettiva. Per impostazione 
predefinita, Ardour torna indietro di 2 battute per la rincorsa. È possibile configurare questa opzione nella finestra 
di dialogo _Preferenze_ nella pagina _Trasporto_.

Pre-conteggio (`Transport > Registra con pre-conteggio` or **Shift+>**) significa che Ardour riprodurrà due battute di 
clic del metronomo, _poi_ inizierà la registrazione.

In entrambi i casi, è fondamentale suonare esattamente a tempo se ci sono note MIDI o contenuti audio proprio all'inizio
della prima battuta registrata. Se suoni anche solo leggermente in anticipo, qualsiasi contenuto a sinistra della 
posizione originale del cursore di riproduzione andrà perso perché inizia prima della creazione effettiva della regione 
audio o MIDI.

Se hai difficoltà a suonare a tempo, spostando il cursore di riproduzione verso sinistra per iniziare a registrare 
una nuova regione audio/MIDI avrai sia il tempo di sincronizzarti che un contenuto perfettamente 
conservato da modificare.

<!-- ## TODO: correzione della latenza??? -->

**Continua**

A questo punto, potresti voler passare direttamente alla sezione 
[Disposizione delle tracce](../../editing-sessions/arranging-tracks/) per imparare come disporre le regioni in una 
composizione. Se hai intenzione di effettuare registrazioni più complesse di quelle che abbiamo discusso qui, in 
particolare con una scheda audio multicanale o da altri programmi audio abilitati per JACK sul tuo computer, dovresti 
anche dare un'occhiata al capitolo [Comprendere il routing](../understanding-routing).
