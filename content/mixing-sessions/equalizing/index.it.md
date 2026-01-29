---
title: Equalizzazione
description: Applicazione dell'equalizzazione all'audio in Ardour
weight: 7
cascade:
  type: docs
---

Un _equalizzatore_ (_EQ_) consente di controllare separatamente il guadagno delle diverse gamme di frequenza di un suono.

Questo può essere utile non solo per modellare il timbro di un suono isolato (ad esempio, per renderlo più "nitido" o 
"morbido"), ma anche per integrare meglio nel mix suoni con timbri diversi.

Spesso, anche dopo aver regolato i livelli e il panning, può essere difficile distinguere nel mix tracce diverse con
contenuti di frequenza simili (ad esempio, un basso e una grancassa). Un equalizzatore è uno strumento utile per 
risolvere questo problema.

## Equalizzatore a 3 bande

Il tipo più semplice di equalizzatore è quello che conosciamo dai mixer analogici. Ha tre parametri che regolano i 
livelli di tre bande, o gamme di frequenza: uno per i bassi (frequenze basse), uno per le frequenze medie e uno per gli 
alti (frequenze alte). Il plugin _DJ EQ_ nella schermata qui sotto è proprio un equalizzatore di questo tipo. Se non 
avete questo particolare plugin sul vostro computer, cercate quelli che avete che contengono "EQ" nel nome; 
probabilmente troverete qualcosa di simile.

{{< figure alt="dj eq" src="it/ardour8-dj-eq.png" >}}

## Equalizzatore multibanda (o grafico)

Un equalizzatore multibanda (o grafico) più complesso spesso ha molte più bande.
Ogni banda è centrata su una frequenza e il livello di ciascuna banda può essere regolato in modo indipendente. In 
alcuni equalizzatori multibanda, come il plugin _LSP Graphic Equalizer_ mostrato di seguito, la frequenza centrale di 
ciascuna banda può essere definita dall'utente. Ciò consente di attenuare (o rimuovere) una frequenza indesiderata o di 
rafforzare (amplificare) quella desiderata.

{{< figure alt="tap eq" src="it/ardour8-lsp-graphic-16-band-eq.png" >}}

La "curva" complessiva delle bande può anche essere utilizzata per determinare il tono generale della traccia o del mix.
Nell'esempio sopra riportato, la parte inferiore delle frequenze medie è stata leggermente "scavata" (si noti come le 
bande 1,2 e 15,16 siano rimaste invariate a 0 dB, mentre le bande intermedie dalla 3 alla 14 disegnano una curva di 
attenuazione, con la banda 7 a -13,5 dB come punto più basso).

## Equalizzatore parametrico

L'equalizzatore parametrico è il tipo di EQ più versatile utilizzato per il mixaggio grazie al suo ampio controllo su 
tutti i tipi di parametri EQ. Ardour viene fornito con un plug-in equalizzatore parametrico chiamato ACE EQ. 
Ha questo aspetto:

{{< figure alt="ACE EQ" src="it/ardour8-ace-eq.png" >}}

Altri possono avere interfacce grafiche più accattivanti, come l'EQ _x42_ di Robin Gareus, ma in sostanza fanno tutti 
esattamente la stessa cosa. È possibile che sul tuo computer siano presenti plugin EQ dall'aspetto leggermente diverso 
rispetto a questi screenshot, ma i parametri che puoi controllare sono probabilmente molto simili.

{{< figure alt="x42 eq" src="it/ardour8-x42-eq.png" >}}

In entrambe le schermate sopra riportate (_ace-EQ_ e _x42 EQ_), sono presenti opzioni che è possibile regolare per 
ciascuna banda di frequenza. Ciascuna delle bande dispone di una regolazione _level_ (dB) per tagliare o amplificare 
le frequenze, una regolazione _frequency_ (Hz) per selezionare la frequenza centrale e una qualche forma di regolazione 
_Q_ che determina l'ampiezza della gamma di frequenze interessate.

#### High shelf, Low shelf (ripiano alto, ripiano basso)

Entrambi i plugin sopra indicati (_ace-EQ_ e _x42 EQ_) contengono anche uno _high shelf_ e uno _low shelf_. 
Uno _shelf_ taglia o amplifica tutto ciò che è al di sopra (high shelf) o al di sotto (low shelf) di una frequenza 
specifica. Ad esempio, un low shelf può essere utilizzato per rimuovere rumori indesiderati, mentre un high shelf può 
essere utilizzato per ridurre il sibilo. Il controllo di frequenza di uno shelf determina la frequenza di taglio. 
Ad esempio, un low shelf con frequenza di taglio di 200 Hz significa che l'equalizzatore attenuerà tutto ciò che è al di
sotto di quella frequenza. La quantità di attenuazione è controllata dalla manopola del livello.

Si noti che in ACE EQ non è presente il parametro _Q_ né per lo shelf alto né per quello basso, mentre in _x42 EQ_ è
presente.

## Un esempio di utilizzo di un equalizzatore

Per ottenere una migliore separazione dei due strumenti nel mix attraverso l'uso dell'EQ, è necessario innanzitutto 
individuare i punti in cui i due strumenti si sovrappongono.

Ecco un approccio possibile.

1. Utilizzando _ACE EQ_ o qualsiasi plugin EQ equivalente, selezionare una banda appropriata per uno degli strumenti. 
Nel caso di un basso elettrico, sarebbe una banda a bassa frequenza (iniziare, ad esempio, da 100 Hz).

2. Aumenta il guadagno a 10 dB, modifica il _Q_ (chiamato anche "larghezza di banda") in modo che sia un intervallo più
ristretto, quindi regola lentamente la frequenza verso l'alto e verso il basso. Sentirai un tono che sale e scende.

3. Abbassalo lentamente fino a sentire la gamma di frequenze in cui i due strumenti si sovrappongono. Ora riduci 
semplicemente il guadagno a -5dB e, se tutto va bene, sentirai gli strumenti un po' più chiaramente. Successivamente, 
applica lo stesso processo all'altro strumento.

Esistono molti approcci all'equalizzazione. Speriamo che questo articolo possa fornire un esempio di come iniziare a 
equalizzare le tracce nel vostro mix. Ma soprattutto, quando si tratta di equalizzazione, è meglio usare troppo poco 
piuttosto che troppo, a meno che non si stia intenzionalmente utilizzando un'equalizzazione estrema come parametro 
compositivo.

## Continua

Ora dovresti avere tutti gli strumenti necessari per creare un mix stereo pulito e ben bilanciato della tua sessione. 
Tuttavia, se desideri che i parametri dei tuoi fader, panning o plugin cambino nel tempo, ti consigliamo di approfondire
il prossimo capitolo sull'automazione. In caso contrario, passa alla sezione successiva per imparare come esportare 
le sessioni.

Successivo: [Utilizzo dell'automazione](../using-automation)
