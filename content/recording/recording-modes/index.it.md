---
title: Modalità di registrazione
description: Puoi scegliere cosa fare con Ardour quando sovraincidi materiale esistente.
weight: 3
cascade:
  type: docs
---

Quando si esegue il sovraincisione utilizzando il punch-in e il punch-out, tutte le modifiche avvengono in modo non 
distruttivo. Tuttavia, è possibile scegliere come Ardour deve comportarsi durante la sovraincisione. A tal fine, nella 
barra degli strumenti principale sono disponibili tre modalità di registrazione: **Stratificato**, **Non stratificato** 
e **Snd su Snd** (suono su suono).

{{< figure src="it/recording-modes-list.png" alt="Modalità di registrazione" >}}

## Stratificato

La modalità **Stratificato** è utilizzata per impostazione predefinita. Quando si esegue la sovraincisione in modalità 
stratificata, viene creata una nuova regione opaca sopra quella esistente.

Per visualizzare tutte le registrazioni sovrapposte come livelli, apri il menu contestuale sopra l'intestazione della 
traccia e passa dalla modalità **Sovrapposta** alla modalità **a strati**. Quando il cursore di riproduzione si trova
sopra questa nuova regione, sentirai solo il suono del livello superiore e non quello del livello inferiore.

{{< figure src="it/layered-mode-stacked.png" alt="Sovraincisioni MIDI in modalità Stratificata, vista a strati" >}}

**Quando utilizzarlo**: quando si desidera avere accesso a più registrazioni durante la sovraincisione.

## Non Stratificato

Nella modalità **Non stratificata**, Ardour ritaglia la regione esistente in modo che quella nuova si adatti perfettamente:

{{< figure src="it/non-layered-mode.png" alt="Sovraincisione audio in modalità Non Stratificata" >}}

Entrambe le regioni sono opache. Se non ti piace la registrazione, puoi ancora annullarla. Oppure, se hai apportato più 
modifiche dopo la sovraincisione e desideri annullarle, puoi selezionare la regione più recente, eliminarla dalla 
timeline e quindi modificare il bordo di una delle due regioni per rivelare l'audio o il MIDI originale.

**Quando utilizzarlo**: quando non si desidera conservare le singole registrazioni durante la sovraincisione.

## Suono su suono (Snd su Snd)

Quando si esegue un sovraincisione in modalità **suono su suono**, Ardour crea una nuova regione in un nuovo livello 
nella parte superiore, ma rende questa regione trasparente.

{{< figure src="it/sound-on-sound-overlaid.png" alt="Sovraincisioni in modalità Suono su Suono" >}}

**Quando utilizzarlo**: un uso comune è quello di costruire progressivamente una traccia di batteria aggiungendo 
grancassa, tom, rullanti e charleston in ogni singola registrazione.

> [!TIP]
È possibile attivare o disattivare l'opacità delle regioni sovrapposte in qualsiasi momento. Per farlo, selezionare una 
> regione, andare al menu principale e utilizzare il pulsante `Regione > Guadagno > Opaco`. È possibile eseguire la 
> stessa operazione dal menu contestuale sopra la regione. Oppure è sufficiente premere **Alt+0**.

**Continua**

Nel prossimo capitolo parleremo di come aiutarti a suonare in sincronia con il resto del materiale della sessione, sia 
che tu stia usando una tastiera MIDI per registrare una parte di synth solista o un basso elettrico.
