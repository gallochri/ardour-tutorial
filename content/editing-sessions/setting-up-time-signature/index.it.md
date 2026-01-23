---
title: Impostazione dell'indicazione metrica (time signature)
description: Come impostare l'indicazione metrica in Ardour
weight: 3
cascade:
  type: docs
---

L'impostazione dell' _indicazione metrica_ determina la velocità musicale del passaggio che stiamo componendo ed è 
espressa in _battiti_ per _battuta_.

Se stiamo componendo qualcosa di ritmico, ciò determinerà in una certa misura, anche la lunghezza dei campioni audio che 
utilizzeremo. È quindi importante poter impostare l'indicazione della metrica prima di continuare.

Per visualizzare le linee temporali relative all'indicazione della metrica per la sessione, è possibile fare clic con il 
pulsante destro del mouse in un punto qualsiasi dell'intestazione dei righelli e selezionare le seguenti opzioni: 
_Indicazione metrica_, _Battute:Battiti_ e _Tempo_.

{{< figure src="it/ardour8-ts-timeline.png" alt="Indicazione del tempo">}}

Nella sessione è sempre presente almeno un indicatore sia per l'indicazione della metrica che per il tempo, proprio 
all'inizio della timeline. È possibile modificare entrambi i valori nel corso della sessione. Per farlo, è necessario 
selezionare il tempo o Battute:Battiti sulla timeline, fare clic con il tasto destro del mouse sulla timeline, scegliere
_Nuova indicazione metrica_ o _Aggiungi nuovo tempo_ e inserire un nuovo valore nella finestra di dialogo appena aperta.

{{< figure src="it/ardour8-new-time-signature.png" alt="Nuova indicazione metrica" >}}

È anche possibile modificare facilmente l'ultima indicazione della metrica o il tempo anche se si è oltre il punto in 
cui è possibile vedere l'indicatore sulla timeline. È sufficiente fare clic sul pulsante tempo o M proprio sotto 
l'orologio secondario e inserire un nuovo valore nella finestra di dialogo appena aperta.

{{< figure src="it/ardour8-edit-TS-and-tempo.png" alt="Pulsanti Tempo e Metrica" >}}

Per il tempo (pulsante a sinistra), scegli il numero di battiti al minuto (bpm) per la tua sessione.

Per l'indicazione _metrica_ (pulsante con la dicitura "M" sulla destra), è possibile inserire nuovi valori per i 
_battiti per battuta_ e per il _valore delle note_.


## Continua

Successivamente, esploreremo l'uso degli intervalli per impostare un loop che possiamo ascoltare mentre arrangiamo il 
ritmo.

Successivo: [Utilizzo degli intervalli](../using-ranges)
