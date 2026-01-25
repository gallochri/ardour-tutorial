---
title: Creare sezioni in loop
description: Creazione e combinazione di regioni duplicate in Ardour
weight: 8
cascade:
  type: docs
---

È possibile ripetere facilmente sezioni audio nella sessione Ardour.

Qui prendiamo il breve passaggio ritmico che abbiamo creato in _Lavorare con le regioni_ e lo duplichiamo per creare un 
loop.

Prima di duplicare il passaggio, è consigliabile combinare le singole regioni della stessa traccia in un'unica regione: 
in questo modo è più facile spostarle e si evita, ad esempio, di spostare accidentalmente un singolo hihat fuori posto. 
Ci sono due modi per farlo: _Combina regioni_ (consente di "separarle" in un secondo momento) e _Consolida intervallo_ 
("lo rende definitivo", non consente di separarle in un secondo momento).

Se hai ancora intenzione di apportare modifiche al ritmo (aggiungendo, rimuovendo o spostando singole regioni), potrebbe
essere preferibile utilizzare l'opzione _Combina_ regioni. Se ti piace la sequenza così com'è e non desideri o non ti 
interessa avere la possibilità di separarle in un secondo momento, utilizza l'opzione _Consolida intervallo_.

## Combina regioni

Basta selezionare tutte le regioni che desideri combinare:

{{< figure alt="combina" src="it/ardour8-combine-regions-1.png" >}}

Quindi vai al menu `Regione > Modifica > Combina` (oppure fai clic con il tasto destro sulle regioni selezionate e trova
la stessa opzione nel menu contestuale, come mostrato di seguito):

{{< figure alt="combine2" src="it/ardour8-combine-regions-2.png" >}} 

Le regioni combinate avranno questo aspetto (si noti la parola "compound" aggiunta al nome):

{{< figure alt="combine3" src="it/ardour8-combine-regions-3.png" >}} 

Se in futuro dovessi separarli nuovamente, seleziona semplicemente l'area composta, vai allo stesso menu e scegli 
l'opzione _Scombina_.

## Consolidare l'intervallo

Un'alternativa più permanente a _Combina_ è l'uso di _Consolida_. Una volta disposte le regioni in un unico "ciclo loop"
e una volta soddisfatti del suono, creare un _intervallo_ con tutte le regioni che compongono il loop.

Per prima cosa, assicurati che tutte le tracce utilizzate nel loop siano selezionate. Le tracce non selezionate sono di
colore grigio, mentre quelle selezionate sono colorate (a seconda del tema dell'interfaccia utente). Se una delle tracce
utilizzate non è selezionata, tieni premuto il tasto **Shift** mentre clicchi su di essa per aggiungerla al gruppo 
selezionato. Infine, utilizza lo strumento Intervallo per selezionare l'intero loop.

Ancora una volta, l'impostazione _griglia_ ti aiuterà a impostare con precisione l'intervallo tra i punti iniziale e 
finale della barra metrica. Una volta selezionato l'intero loop, fai clic con il pulsante destro del mouse 
sull'intervallo e seleziona _Consolida_. Se desideri includere eventuali effetti di automazione o plugin aggiunti al 
loop, seleziona _Consolida (con elaborazione)_.

{{< figure alt="consolida" src="it/ardour8-consolidate-range-1.png" >}} 

Una volta consolidato l'intervallo, in ogni traccia appariranno nuove regioni, ciascuna contenente tutte le ripetizioni
dei campioni impostati nei passaggi precedenti. Ricordate che, una volta consolidato l'intervallo, non è possibile 
annullare questa operazione. In ogni caso, se ritenete necessario modificare il ritmo in qualche modo, potete sempre 
recuperare i singoli campioni originali dall'elenco delle regioni e ricostruire il pattern con essi.

{{< figure alt="consolida2" src="it/ardour8-consolidate-range-2.png" >}}

## Duplicazione dell'intervallo

Dopo aver unito le singole regioni che compongono il pattern (utilizzando _Combina_ o _Consolida_), è il momento di 
duplicare il pattern per ripeterlo su più battute.

La funzione _Replica_ (descritta nel capitolo [Lavorare con le regioni](../working-with-regions/)) è un ottimo modo per 
ottenere questo risultato. Torna alla modalità _mano_ (**G**), seleziona tutte le regioni e premi **Shift+D**. Scegli 
quante volte desideri duplicare il pattern (ad esempio, 16). Dopo la duplicazione, la nostra sessione apparirà simile a 
questa:

{{< figure alt="replica" src="it/ardour8-multi-duplicate.png" >}} 

Solo per completezza, altre opzioni che avresti potuto utilizzare per la duplicazione sono:

- Il comando _Riempi traccia_ dal menu `Regione > Duplica > Riempi traccia`. Questo riempirebbe l'intera traccia con 
copie delle regioni selezionate, fino al _marcatore fine_.

- Il comando singolo _Duplica_ dallo stesso menu (**Alt+D**). Questo ti permette di creare una sola copia alla volta.

- L'unica azione duplicata con **Ctrl+clic** sulla regione + _Trascina una copia_.

## Continua

Nel prossimo tutorial impareremo come allungare/accorciare le regioni che sono più lunghe o più corte di una battuta per
adattarle al ritmo del nostro brano.

Successivo: [Allungamento e accorciamento delle regioni](../stretching-shrinking-regions)
