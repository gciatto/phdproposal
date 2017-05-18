* Depersonalizzare l'introduzione e sintetizzarla

* Partire da knoledge intensive systems
    - includere data stream, data fusion, reti di sensori general purpose

0. Centralità degli eventi
0. Survey a caso di roba eventosa
    - distinzione tra stream di eventi e stream di dati
    - citare: A. Storm, A. Flink, RX, A. NiFi, A. Ignite
        + tutti sfruttano più calcolatori che collaborano in distribuito ma o hanno un approccio agnostico riguardo ai nodi della rete che li compone (i.e. l'utilizzatore deve istanziare la rete) oppure si basano sul clustering computing (i.e. approccio classico alla scalabilità: scala solo il server). Voglio sì avere gestione degli eventi ma vogliamo una effettiva computazione. Se una computazione può essere fatta sugli edge o vicino agli edge è bene ci sia fatta lì
    - intersezione con WSN
    - intersezione con IoT
    - intersezione con Field Calculus (per la propagazione)
    - intersezione con Respect/Tucson per workflow
    - intersezione con MAS
    - intersezione con Fog computing
    - intersezione con BIC (Behavioral implicit communication)
0. Integrazione concettuale tra stream di eventi e stream di dati
    - problematiche di livello basso
        + routing degli eventi data la decentralizzazione
        + gestione automatica della topologia dei nodi di elaborazione
        + Consistena
        + transazioni distribuite
        + eventi situati spazialmente
    - problematiche relative agli eventi: ogni evento dev'essere:
        + rilevato
        + rappresentato
        + propagato
        + filtrato
        + interpretato = che significato che per il ricevente
        + eventualmente integrato = integrare l'evento con altri eventi o dati
    - integrazione tra le architetture per gestire grandi moli dati ed architetture per gestione di eveti complessi CEP
        + confronto di tali architetture con Linda/Respect/Mok/Gamma e robe biochimiche
    - la questione del contesto: uno dei ponti possibili tra dati ed eventi è il contesto, ovvero l'insieme di informazioni relative all'evento
    - la questione semantica: si vuole essere in grado di dare semantica agli eventi, anziché basarsi sulla mera corrispondenza sintattica. Approccio classico: le notifiche degli eventi viaggiano codificate in linguaggio standard e i consimatori posso registrare dei mapper/traduttori per la conversione sintattica. Si vuole invece che i *prosumers* ed il MW siano in grado di comprendere e confrontare semanticamente gli eventi ed i dati mentre gli elaborano => ponte con semantica, web semantico, ontologie etc
    - la questione della rappresentazione della conoscenza: si vuole che i prosumers e il MW possano ragionare su eventi e dati, e fin lì va bene anche une rete neurale, ma si vuole anche che i ragionamenti siano esplicitabili, si vuole che il sistema sia in grado sia di apprendere da dati ed eventi, sia di sfruttare autonomamente ciò che ha appreso per funzionare, sia di motivare in termini umanamente comprensibili il perchè delle scelte fatte in autonomia.
0. Individuazione di scenari applicativi e.g., IoT, WSN, WfMS, Process-Mining, simulazione distribuita, e casi d'uso guida autonoma, domotica, smart environments.
