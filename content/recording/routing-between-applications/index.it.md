---
title: Routing tra applicazioni
description: Inoltro del segnale dai programmi ad Ardour
weight: 6
cascade:
  type: docs
---

A volte potrebbe essere necessario registrare l'audio di un altro programma in Ardour, ad esempio il suono di un video
di YouTube riprodotto in Firefox o l'output di SuperCollider o PureData. Questo capitolo mostra come farlo.

Gli esempi riportati in questa pagina sono stati creati su un computer con sistema operativo openSUSE Linux. Si prega di
notare che il funzionamento potrebbe variare se si utilizza un altro sistema operativo (in particolare se si utilizza un
Mac). Tuttavia, i principi generali rimangono sempre gli stessi.

## Dal tuo browser ad Ardour

I browser web (Firefox, Chromium, ecc.) non sono applicazioni compatibili con JACK. Fortunatamente, PipeWire ora rende 
abbastanza facile collegare qualsiasi applicazione che riproduce suoni a qualsiasi applicazione di registrazione 
compatibile con JACK, come Ardour.

Tutto quello che devi fare è avviare Qjackctl, avviare JACK, quindi iniziare a riprodurre suoni nel browser e infine 
collegare le uscite del browser a una traccia in Ardour. Per farlo, puoi utilizzare le finestre Patchbay o Grafico in 
Qjackctl, oppure puoi farlo direttamente in Ardour. A tal fine, nel Gestore dei collegamenti Audio passa alla scheda 
_Esterno_ in _Sorgenti_ sulla sinistra e collega l'uscita del browser a una traccia di Ardour chiamata _From YT_ qui:

{{< figure src="it/ardour8-youtube-connection-in-ardour.png" alt="Gestore dei collegamenti Audio" >}}

Poiché le applicazioni come i browser web non dispongono solitamente di porte di uscita audio permanenti, è necessario 
che il browser riproduca dell'audio affinché le porte possano essere create. Ciò significa solitamente riprodurre un 
video o avviare una videoconferenza.

Dopodiché, tutto quello che devi fare è attivare la traccia per la registrazione, quindi avviare la registrazione:

{{< figure src="it/ardour7-youtube-recording.png" alt="Inizia la registrazione" >}}

> [!IMPORTANT]
> Assicurati di aver scollegato tutte le altre uscite (come il microfono) dall'ingresso della traccia, altrimenti la 
> traccia potrebbe catturare più del necessario e mixarlo con l'audio del browser.

## Dalle applicazioni compatibili con JACK ad Ardour

Altri software musicali come SuperCollider, Hydrogen e PureData sono compatibili con JACK. Ciò significa che appariranno
direttamente come opzioni di origine e destinazione nel Gestore dei collegamenti Audio di Ardour. Non è necessario 
preoccuparsi di alcun bridge PulseAudio / Jack come nell'esempio YouTube sopra riportato.

La procedura è sostanzialmente la stessa: creare una traccia mono o stereo per registrare l'audio, impostare gli 
ingressi di quella traccia sulla sorgente desiderata e registrare come di consueto.

{{< figure src="it/ardour7-hydrogen.png" alt="Hydrogen" >}} 

Lo screenshot sopra è stato acquisito durante la registrazione di un pattern di batteria da Hydrogen direttamente in una
traccia Ardour denominata _Drum N_, dove N è un numero compreso tra 1 e 18. Per impostazione predefinita, Hydrogen crea 
un'uscita stereo dal proprio mix. Tuttavia, è possibile impostare la creazione di porte di uscita per singolo strumento 
(la casella di controllo si trova nella pagina _Audio System_ della finestra di dialogo _Preferences_).

La finestra di Hydrogen si trova sulla destra. La finestra patchbay di Ardour è stata lasciata aperta per la 
dimostrazione: si noti che l'applicazione _Hydrogen_ appare come sorgente nella scheda _Other_ (Esterno). Le sue porte sono collegate direttamente agli ingressi delle tracce.

**Continua**

Questo conclude il capitolo _Registrazione_. Ora che hai importato alcuni file audio, registrati da un ingresso di linea
o microfono, o anche da un'altra applicazione, passa alla sezione 
[disposizione delle tracce](/editing-sessions/arranging-tracks/) e impara come organizzare la tua composizione.
