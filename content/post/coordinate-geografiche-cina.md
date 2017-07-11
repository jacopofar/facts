---
title: "La geodesia e le coordinate geografiche in Cina"
date: 2017-07-11T09:25:29+02:00
---
La Cina gestisce la cartografia elettronica sul proprio territorio nella stessa maniera in cui gestisce molte altre tecnologie: secondo procedure complicate, burocratiche e totalmente diverse dal resto del mondo.

Ma per capire bene la faccenda riassumiamo la situazione della geodesia. La geodesia (lett. "divisione della terra") è la scienza che si occupa del calcolo e della misura delle coordinate sulla Terra. Come saprete, la Terra non è neanche lontanamente una sfera ma ha una forma piuttosto bitorzoluta, chiamata "geoide", che però non ci aiuta dato che vuol dire proprio che la Terra ha la forma della Terra.

Se la Terra fosse una sfera, una volta individuati l'equatore e il meridiano di Greenwich o in generale due circonferenze non parallele di riferimento, si potrebbero definire le coordinate di qualsiasi punto con i due angoli rispetto al centro e a questi indicatori, la latitudine e la longitudine.

Invece, l'irregolarità della forma della Terra fa sì che, una volta ottenute latitudine e longitudine, le si debba riportare su un modello preciso del geoide, onde evitare errori che possono arrivare anche a una decina di km. Quindi, dagli inizi del '900, gli scienziati lavorano per affinare questi modelli combinando le diverse misurazioni e fare sì che siano condivisi. Con l'avvento dell'aereo e i primi esperimenti aerospaziali, l'esigenza è diventata ancora più pressante e così a metà del '900 l'esercito americano ha creato una commissione di scienziati da diverse nazioni per definire uno standard universale. Nacque così il WGS60 (World Geodetic System del 1960), rivisto poi varie volte fino alla versione del 1984, chiamata appunto __WGS84__.

Questo modello differisce dalla forma del geoide (ossia della Terra) di meno di un metro sul livello medio del mare in ogni punto della superficie. Quindi il problema delle coordinate è "risolto", salvo ulteriori perfezionamenti del modello (è stato infatti aggiornato nel 2002, ma l'ellissoide di riferimento non è cambiato), quindi ci si aspetta che tutti lo usino in modo che le coordinate possano essere scambiate in sicurezza. E invece __no__. Come avrete intuito dall'incipit, la Cina non ha adottato il WSG84 bensì un suo sistema chiamato __GCJ-02__. La documentazione ufficiale su questo standard è molto scarsa in inglese, e le coordinate sono "crittate", ossia non è possibile (almeno in teoria), convertire con sicurezza delle coordinate tra i due sistemi, con il risultato che una mappa fatta sfruttando GCJ02 può essere anche 1km "spostata" rispetto a una calcolata in base a WGS84.

In più, la Cina richiede un permeso per ogni attività di mappatura del proprio territorio, quindi è vietato circolare con un normale GPS e annotare le coordinate di edifici o strade se non si ha un'autorizzazione che viene concessa solo se si stabilisce una partnership con le aziende di stato che ovviamente usano GCJ02. Questo vale anche per i singoli individui, quindi un privato cittadino non può raccogliere questi dati legalmente e ci sono stati casi di [studenti multati](https://en.wikipedia.org/wiki/Restrictions_on_geographic_data_in_China).

Ma in cosa differisce davvero GCJ02 dallo standard WGS84 usato nel mondo libero? Innanzitutto, __GCJ02 è basato su WGS84__ a meno di un offset apparentemente casuale. Quindi si tratta di un meccanismo per "nascondere" le coordinate vere aggiungendo un valore che è calcolato con una formula segreta. Senza sapere la formula si subisce un errore non da poco nelle coordinate (anche 1 km) che rende inutilizzabili ad esempio i navigatori satellitari.

La formula è tenuta segreta dal governo Cinese, ma l'analisi incrociata dei dati nei due sistemi geodesici tramite trasformata di Fourier e del codice di alcuni software che eseguono la conversione ha portato alla scoperta della formula, al punto che sono ora presenti per molti linguaggi delle librerie che effettuano la conversione. L'uso di queste librerie è ovviamente illegale in Cina.

Approfondimenti:

* https://gis.stackexchange.com/questions/141542/what-causes-the-gps-offset-shift-in-china

* https://en.wikipedia.org/wiki/Restrictions_on_geographic_data_in_China
