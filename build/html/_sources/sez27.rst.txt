.. _sezione27:

Ciclo di vita di una API  (*API lifecycle*)
===========================================

.. raw:: html

  <style> p,td,li,ol {text-align:justify; word-wrap:break-word} </style>

  <style> p.caption {text-align:center;} </style>

Si riportano nella tabella seguente i campi del descrittore dell’API che indirizzano direttamente gli aspetti legati al ciclo di vita dell’API.

.. _sezione271:

Gli aspetti relativi al lifecycle all’interno del descrittore dell'API
-----------------------------------------------------------------------



.. list-table:: Campi del descrittore relativi all'API lifecycle
   :align: center
   :header-rows: 1

   * - Campo
     - Descrizione
   * - Versione dell'API
     - Identificativo della versione dell’API all’interno dell’Ecosistema.
   * - Riferimento ad altre versioni dell'API altre versioni dell'API
     - Riferimento ad eventuali altre versioni dell’API pubblicate all’interno dell’ Ecosistema. Per ogni riferimento viene fornito un changelog delle diverse versioni.

.. _sezione272:

Il ciclo di vita delle API di E015 Digital Ecosystem
----------------------------------------------------

Le API di E015 Digital Ecosystem rappresentano dei “building-block” riusabili messi a disposizione degli App provider per le realizzazione delle applicazioni. 

Al fine di consentire l’erogazione di applicazioni di qualità è importante che:

* L’API Provider comunichi *Major Change* non retrocompatibili (cambio tracciato dati, cambio policy, dismissione dell’API) con almeno 6 mesi di preavviso. In questo modo, chi realizza le applicazioni ha la garanzia del  periodo temporale nel corso del quale le API utilizzate saranno effettivamente erogate con continuità.
   
* Le API pubblicate nell’Ecosistema siano il più possibile stabili, non solo da un punto di vista tecnico, ma anche e soprattutto da un punto di vista della continuità del “business”; un’API nata per esigenze temporanee e che molto probabilmente verrà dismessa nel giro di qualche mese può provocare un significativo impatto sulle applicazioni che ne fanno uso; per questo motivo non potrà essere pubblicata all’interno di E015 Digital Ecosystem, non essendo considerata “stabile”, ovvero non potendo garantire un significativo orizzonte temporale di erogazione.




Al fine di soddisfare questi importanti requisiti è necessario che tutte le API dell’Ecosistema siano erogate in accordo al *“lifecycle”* descritto nel seguito:


1. Una volta valutata positivamente l’opportunità di pubblicare una API all’interno dell’Ecosistema, l’ API Provider compila il descrittore dell’ API; 

2. Successivamente alla pubblicazione e all’approvazione del descrittore da parte del TMB, l’API entra nella fase di *“erogazione”*. Durante questa fase l’API Provider si impegna a mantenere attiva la propria API con continuità, in modo da consentirne un utilizzo prolungato nel tempo da parte delle applicazioni;

3. Nel caso di *Major Change non retrocompatibili* (fra le quali cambio di policy o dismissione), l’API Provider è tenuto a comunicarlo con un prevviso di 6 mesi. Nell’arco di questi 6 mesi l’API Provider si impegna a mantenere stabile la versione in dismissione. Questa fase consente agli App Provider di poter intervenire sulla proprie applicazioni

4. Una volta effettivamente esaurito il transitorio di 6 mesi può verificarsi una delle seguenti situazioni:

     * l’API viene definitivamente dismessa e le applicazioni non ne possono più fare uso;

     * è stata nel frattempo pubblicata una nuova versione dell’API e l’Ecosistema invia alle applicazioni utilizzatrici una notifica nella quale promuove la migrazione verso la nuova versione;

     * l’Ecosistema invia alle applicazioni utilizzatrici una notifica nella quale comunica che l’API sarà ancora disponibile.


Generalmente non è possibile dismettere una API prima dei sei mesi, ad eccezione dei seguenti casi:


1. l’API non risulta più in utilizzo da parte di alcuna applicazione (ad esempio, perché tutte le applicazioni utilizzatrici hanno effettuato una migrazione ad una successiva versione);

2. eventuali cause di forza maggiore.

Dal momento che le API di E015 Digital Ecosystem possono essere soggette ad evoluzioni, è necessario prevedere la possibilità da parte dell’API Provider di pubblicare molteplici versioni di una stessa API.

Le linee guida per la pubblicazione di una nuova versione dell’API sono le seguenti:

1. le evoluzioni dell’API che comportano modifiche di *Major Change non retrocompatibili* determinano la pubblicazione di nuove versioni tra loro indipendenti. In questo caso:

    * le nuove versioni di una API devono essere erogate tramite un endpoint dedicato e il loro processo di pubblicazione segue il normale iter previsto per la pubblicazione di una nuova API (in particolare, il campo “Riferimento ad altre versioni dell’API” referenzierà le versioni precedenti); 

    * le versioni precedenti dell’API continuano ad essere attive e restano a disposizione delle applicazioni, come indicato in :ref:`Figura 2.8 <versioniapi>`. È possibile pertanto che più versioni della stessa API, le quali differiscono tra loro a livello di interfaccia e/o modello dei dati, siano attive contemporaneamente;

    * l’Ecosistema notifica alle applicazioni utilizzatrici la disponibilità di una nuova versione dell’API, promuovendo la migrazione alla versione più recente.

2. le evoluzioni dell’API che NON comportano modifiche all’interfaccia (ad esempio, che determinano un incremento della qualità dei dati erogati) non necessitano della pubblicazione di una nuova versione indipendente. 
In questo caso le modifiche all’API – previa approvazione da parte del TMB – vengono eseguite direttamente sulla stessa istanza dell’API già pubblicata all’interno dell’Ecosistema.
L’Ecosistema provvede ad inviare delle notifiche ai soggetti utilizzatori, specificando le caratteristiche dell’API oggetto di evoluzione.


.. _versioniapi:

.. figure::  pics/api_test/versioni2.png
   :scale: 80 %
   :align:   center


   Figura 2.8: Gestione delle versioni delle API in E015 Digital Ecosystem



