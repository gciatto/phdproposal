Proposta di dottorato
=====================
di Giovanni Ciatto

## Introduzione

Il progetto di ricerca nasce dalla presa di coscienza che i sistemi software distribuiti del futuro saranno sempre più *complessi*, sia rispetto al numero di componenti distribuite, sia in termini di interazioni possibili tra di esse.
La mia forte convinzione è che le seguenti caratteristiche avranno per tali sistemi un'importanza sempre maggiore:

- __Decentralizzazione__, cioè la capacità di un sistema di ottemperare ai propri requisiti funzionali senza la necessità che un suo componente abbia o possa avere una visione *globale* dello stato del sistema stesso, così da evitare la creazione *single-point-of-failure*.
Le interazioni tra i partecipanti al sistema distribuito hanno un effetto locale, secondo un qualche principio di *vicinanza* (logica o fisica), gli algoritmi messi in campo sono intrinsecamente distribuiti e concorrenti.
La nozione di "decentralizzazione" cui faccio riferimento rassomiglia quella de (i) l'*aggregate programming*, secondo il quale un numero teoricamente illimitato di dispositivi si comporta come una singola macchina "aggregata" che esegue algoritmi distribuiti basati su un insieme minimale di primitive ed assunzioni, come pure (ii) quella della *shared nothing architecture* che impone la totale mancanza di condivisione di stato tra i partecipanti al sistema distribuito.  

- __Scalabilità__, cioè la capacità di un sistema distribuito di mantenersi resiliente rispetto a variazioni anche significative del numero di partecipanti e/o del carico di lavoro.
La scalabilità non deve più basarsi *solo* sulla capacità infrastrutturale di allocare/deallocare automaticamente le risorse computazionali in funzione delle necessità contingenti --- rimanendo quindi nascosta tra il livello hardware e quello middleware ---  ma anche e soprattutto sulla collaborazione tra i partecipanti al sistema, tra i quali vanno ripartiti il carico di lavoro e l'informazione globalmente posseduta dal sistema.
A tal fine, bisogna esplicitare la scalabilità già a livello di modellazione dei moderni sistemi distribuiti, forneando astrazioni concettuali e costrutti linguistici atti a garantirla.

- __Auto-organizzazione__, cioè la capacità di un sistema di modificare il proprio funzionamento in risposta all'interazione con gli utenti (in modo da facilitarne le operazioni permesse ed ostacolarne quelle non ammesse), al riconoscimento di un qualche altro evento rilevante o ancora la capacità di mantenere una sorta di *omeostasi* interna (cioè il mantenimento di una qualche struttura nel tempo, anche a fronte dei cambiamenti e parturbazioni).
Il sistema auto-organizzante deve essere quindi in grado di decidere il *quando* e il *come* ri-organizzarsi e di deliberare in merito al *momento* ed alla *modalità* localmente migliori per farlo.

- __Semplicità di progettazione ed implementazione__, cioè la caratteristica per cui gli strumenti teorici e tecnologici forniti a progettisti, ingegneri e sviluppatori, che dovranno costruire sistemi siffatti, comprendano almeno:
    * un _modello computazionale di riferimento_, composto da un insieme limitato (e possibilmente minimale) di meccanismi di base atti a specificare il comportamento dei sistemi che li impiegano, la cui semantica operazionale, di natura inerentemente non-deterministica o, meglio ancora, stocastica, sia basata su solide basi teoriche;
    * meccanismi di _astrazione_, cioè quell'insieme di metodi atti a comporre i meccanismi di base a formare funzionalità più articolate, così che queste possano essere successivamente ri-usate, astraendo dal modo con cui siano state ottenute a partire da elementi più semplici. 
    Esempi di meccanismi di astrazione sono l'ereditarietà nel paradigma di programmazione ad oggetti, come anche le funzioni *high-order* nel paradigma funzionale;
    * strumenti di _supporto_, cioè quel corpus di tecnologie atte a facilitare la modellazione, progettazione, implementazione, collaudo e manutenzione dei sistemi. 
    Rientrano in questa categoria quegli applicativi che guidano i progettisti nella stesura dei modelli formali, o ne permettono un'analisi statica di correttezza formale e validità (e.g. *type checker* e *model-checker*), o un'analisi dinamica (e.g. simulatori, *model-checker* stocastici e *debugger*).
    * l'impiego, quanto più ampio possibile, di _protocolli e tecnologie standard_ e di larga diffusione, per tutto ciò che concerne l'implementazione e la manutenzione, al fine di permettere apertura ed interoperabilità --- due proprietà non-funzionali vitali per i sistemi distribuiti moderni --- e di abilitare la creazione di infrastrutture in grado di confrontarsi con le controparti industruali.




    <!--TODO commenti sulla non ortogonalità di questi aspetti-->

    <!--TODO chiave di lettura principale: l'interazione, la coordinazione e la concorrenza. 
    Nel momento in cui si parla di distribuzioe e decentralizzazione, la concorrenza è assunta implicitamente, come pure l'interazione. 
    Dove c'è interazione nasce l'esigenza di coordinazione.-->


Queste caratteristiche non sono affatto ortogonali tra loro. 
Decentralizzazione e scalabilità sono, ad esempio, fortemente interrelate: ipotizzando un sistema in grado di funzionare --- o magari auto-organizzarsi --- in maniera completamente decentralizzata, è lecito aspettarsi che l'aggiungersi di nuovi partecipanti al sistema vada ad impattare positivamente la potenza di calcolo del sistema distribuito anziché essere considerata una richiesta di allocazione di risorse cui far fronte.
L'auto-organizzazione permette che la decentralizzazione e la scalabilità si mantengano nel tempo stimolando, ad esempio, la continua redistribuzione del carico di lavoro e delle informazioni tra i vari partecipanti al sistema distribuito.
Ci si aspetta inoltre che sistemi siffatti, espongano una serie di caratteristiche fisiologicamente derivanti dalle precedenti, come ad esempio la __ridondanza__ dell'informazione, tipica dei sistemi decentralizzati in cui non esiste una singola base di conoscenza.
Questa, a sua volta, abilita un maggiore grado di __parallelizzazione__, tende a podurre l'assai desiderabile __resistenza ai guasti__ al prezzo dell'introduzione di problemi di __consistenza__ che vanno opportunamente gestiti.
La semplicità di progettazione e implementazione, infine, chiude il cerchio garantendo che sistemi di questa specie possano essere costruiti e controllati.

Risulta dunque evidente come il *focus* non sia sulla maniera con cui i vari partecipanti ai sistemi distribuiti computino, né sull'oggetto della loro computazione, bensì sui possibili modi in cui questi interagiscono e riescono, per mezzo della loro interazione, a funzionare in maniera __coordinata__, ovvero come un sistema.


### Sunto della proposta

<!--TODO Analizzare modelli proposti in letteratura e architetture di successo nel "mondo reale", sondarne punti di forza e di debolezza rispetto alle caratteristiche dette sopra, analogie e differenze tra i vari elementi selezionati, punti d'incontro e punti di divergenza.-->
Molti sono i modelli presenti in letteratura che dichiarano di catturare le astrazioni sufficienti per gestire sistemi caratterizzati dai tratti di decentralizzazione, scalabilità, auto-oganizzazione e semplicità qui evidenziati, o, almeno, parte di essi.
Molte sono altresì le architetture e le infrastrutture impiegate oggigiorno dai sistemi distribuiti industriali, che permettono loro di fregiarsi, *in toto* o in parte, dei tratti suddetti.

La mia proposta consiste, in primo luogo, nella valutazione dell'intersezione tra questi due mondi finalizzata alla comprensione di se e quanto gli sforzi della comunità accademica stiano portando in una direzione effettivamente percorribile.
In particolare sarebbe interessante valutare quali modelli, architetture e infrastrutture rimangano escluse da detta intersezione, onde individuare gli eventuali aspetti catturati dalle realtà industriali cui non corrisponda una adeguata modellazione di riferimento, o, viceversa, qualora si trovassero modelli che non siano riusciti ad impattare come originariamente sperato, comprendere le cause di tale insuccesso e proporre migliorie in grado di superarle.
In questa fase particolare attenzione sarà rivolta a quei modelli ed a quelle tecnologie che impiegano meccanismi di natura stocastica per fornire auto-organizzazione ed adattabilità, data la forte correlazione tra i primi e le seconde dimostrate da quasi due decenni di ricerca in tal senso.

<!--Operativamente, ciò presuppone una cernita dei modelli e delle tecnologie messe in campo negli ambiti accademici e industriali per approcciarsi ai *desiderata* della sezione precedente, seguita da un'analisi di quali concetti, astrazioni e primitive stiano alla base di ogni modello o tecnologia, al fine di individuare similitudini nascoste da nomenclature differenti o potenzialità inespresse per mancanza di generalizzazione.-->

In una seconda fase, il focus si sposterà sull'integrazione di quei modelli e di quelle tecnologie che più si riveleranno adeguati a supportare *efficacemente* sistemi auto-organizzanti, decentralizzati e a larga scala, atta a sintetizzare un nuovo approccio che possa garantire un pieno adempimento dei *desiderata* della sezione precedente.
L'integrazione concettuale dovrà basarsi su solide basi teoriche, e l'espressività dovrà essere confrontanta con i modelli pre-esistenti sia in termini formali che in termini di semplicità con cui sia possibile governare il comportamento dinamico del sistema distribuito.
In questa fase sarà cruciale anche il confronto con la tecnologia esistente, la quale dovrà fungere al tempo stesso da sorgente di requisiti e di casi d'uso e da metro di paragone per valutare le prestazioni e l'usabilità.

<!--TODO i tool di supporto-->

## Stato dell'arte

<!--TODO Principali modelli di coordinazione:
    - Scambio di messaggi
    - Event-driven architectures
    - Linda: comunicazione generativa + semantica bloccante
    - Tucson/Respect:  comunicazione generativa + semantica bloccante + programmabilità del medium
    - Mok: com. gen. -> metafora biochimica
    -  -->

<!--Adottando la nomenclatura di Ciancarini [cit.] -->
Un sistema atto a governare le interazioni possibili tra i partecipanti (o __coordinabili__) al sistema distribuito è detto __medium di coordinazione__.
Esso impiegherà un particolare __modello/linguaggio di coordinazione__ per permettere ai progettisti di specificare le regole con le quali i coordinabili potranno interagire.

Negli anni, sono stati proposti diversi modelli di coordinazione che hanno avuto un forte impatto nel mondo informatico, a partire dai classici __middleware a scambio di messaggi__, in cui il *medium* ha la "sola" responsabilità di propagare i messaggi sulla rete, fino alle più evolute architetture __event-driven__, in cui ad essere propagata è la notifica degli eventi ed il *medium* offre la possibilità di ragionare sulla co-occorrenza di eventi e su eventuali pattern ricorrenti di sequenze di eventi.

In letteratura, una pietra miliare è rappresentata dall'introduzione di `Linda` [cit.] e, più in generale, della __comunicazione generativa__, in cui le *tuple*, cioé i quanti di informazione scambiati nell'interazione distribuita, godono di vita propria, indipendente dal coordinabile che li ha genereti.
Tale modello è poi stato ripreso ed esteso da `TuCSoN` / `ReSpecT` [cit.] in cui le tuple sono termini della logica del prim'ordine e il medium diventa programmabile dinamicamente per mezzo di reazioni che permettono di intercettare l'invocazione delle primitive del modello stesso.

Nella sua tesi di dottorato, Mariani [cit.] introduce Mok, un modello di coordinazione che eredita la comunicazione generativa e la possibilità di specificare reazioni combinandole con la metafora biochimica tipica del modello `Gamma` [cit.], in cui i quanti di informazione vengono immaginati come molecole e la computazione si evolve mimando il funzionamento delle reazioni chimiche, cioè trasformando continuamente tuple-reagenti in tuple-prodotto.
L'autore prende atto della maggiore espressività dei meccanismi stocastici rispetto al *don't care non-determinism* delle primitive `Linda`.
L'impiego di approcci probabilistici che si ispirano alla biologia ed alla chimica è ormai consolidato in molti ambiti dell'informatica, specialmente laddove siano richieste __resilienza__ ed __auto-organizzazione__.
<!--TODO citare ACO, la swam intelligence, etc. -->

## Il progetto di ricerca

## Casi di studio

## Risultati attesi

## Bibliografia