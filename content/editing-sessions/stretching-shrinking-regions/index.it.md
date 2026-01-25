---
title: Allungamento e accorciamento delle regioni
description: Allungare e accorciare regioni in Ardour
weight: 9
cascade:
  type: docs
---

È possibile allungare o accorciare le regioni in lunghezza senza modificarne l'intonazione utilizzando lo strumento 
_elastico_ (scorciatoia **T**, per "Time-stretch").

{{< figure src="it/ardour8-stretch-shrink-edit-mode.png" alt="strumento elastico" >}}

Una piccola modifica alla lunghezza di una regione potrebbe non causare artefatti sonori evidenti. Tuttavia, più il 
cambiamento di lunghezza è estremo, più evidente sarà l'effetto dell'elaborazione sul suono.

Per utilizzare la funzione _elastico_, posiziona il cursore sopra la regione, quindi fai clic e trascina verso sinistra 
o destra. Durante il trascinamento, vedrai un'area evidenziata che rappresenta la nuova durata alla quale la regione 
verrà accorciata o allungata quando rilascerai il mouse nella posizione corrente. Ardour visualizzerà anche la nuova 
durata della regione accanto all'area evidenziata in unità dell'orologio primario.

{{< figure src="it/ardour8-stretch-shrink-highlight.png" alt="Modifica in evidenza" >}}

## Allungamento temporale di una regione per adattarla al loop

Nell'immagine sottostante abbiamo aggiunto un altro campione audio, questa volta una 
[linea di sintetizzatore tratta da freesound.org](https://freesound.org/people/walkerbelm/sounds/1168/) al passaggio 
ritmico che abbiamo composto nel capitolo _Creare sezioni in loop_.

Dopo aver importato questa linea di synth, noterai che la lunghezza della nuova regione non corrisponde al ritmo 
esistente che abbiamo già creato. È troppo lunga per essere una battuta e troppo corta per essere due battute. Ancora 
più importante, mentre la prima nota corrisponde all'inizio del suono della grancassa sopra, la seconda nota è 
chiaramente fuori tempo.

{{< figure src="it/ardour8-stretch-shrink-1.png" alt="Regioni non corrispondenti" >}}

Possiamo correggere questo problema utilizzando lo strumento _elastico_. Seleziona l'area che desideri allungare, 
passa allo strumento, clicca sul lato destro dell'area, quindi trascina il cursore fino a quando l'area evidenziata 
appena creata corrisponde alla nuova lunghezza, ovvero fino alla seconda barra (anche in questo caso con l'aiuto delle 
impostazioni _Griglia_).

{{< figure src="it/ardour8-stretch-shrink-action.png" alt="Allungamento" >}}

Quando rilasci il pulsante del mouse, viene visualizzata la finestra di dialogo _Cambio tempo audio_. Puoi provare 
diverse impostazioni per l'operazione _allungamento tempo_. Ciascuna di esse influirà sul suono in modo diverso. È 
consigliabile provare diverse impostazioni di stretch per scoprire quale ti offre il risultato che preferisci.

{{< figure src="it/ardour8-stretch-shrink-2.png" alt="Finestra di dialogo cambio tempo audio" >}}

Fare clic su **Allunga/Accorcia** nella finestra di dialogo _cambia tempo audio_ per avviare l'operazione.

Una volta completata l'operazione, la regione della linea del sintetizzatore avrà una lunghezza esattamente pari a due 
battute e dovrebbe adattarsi al ritmo che abbiamo già creato con i campioni di batteria.

{{< figure src="it/ardour8-stretch-shrink-3.png" alt="Regione audio estesa" >}}

## Continua

Ora parliamo della modifica delle regioni MIDI.

Successivo: [Modifica delle regioni MIDI](../editing-midi-regions/)
