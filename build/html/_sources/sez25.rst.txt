.. _sezione25:

Aspetti correlati all’erogazione di una API
===========================================

.. raw:: html

  <style> p,td,li,ol {text-align:justify; word-wrap:break-word} </style>

  <style> p.caption {text-align:center;} </style>
.. _sezione251:

Gli aspetti relativi all’erogazione all’interno del descrittore dell’ API
-------------------------------------------------------------------------

Si riportano nella tabella seguente i campi del descrittore dell’API che indirizzano direttamente gli aspetti legati all’erogazione dell’API.




.. list-table:: Campi del descrittore relativi all'erogazione dell'API
   :align: center
   :header-rows: 1

   * - Campo
     - Descrizione
   * - Impegni/capacità di erogazione
     - Indicazione generale su base volontaria della capacità di erogazione dell’API che  l’API Provider indica di poter sostenere nei confronti dell’Ecosistema (secondo una logica best effort).
   * - Logiche di remunerazione
     - Indicazione della logica di remunerazione connessa all'erogazione dell’API. I valori ammissibili per questoattributo del descrittore sono:

           1. *Free*: per API che non prevedono alcuna forma di tariffazione;
           2. *A pagamento*: per API che prevedono il pagamento di una tariffa legata all’utilizzo.

       **Modelli di tariffazione supportati** (attributo specifico da compilare per le sole API “a pagamento”):
       Indicazione dei modelli supportati per la tariffazione di API a pagamento.

       **Tipologia di QoS supportate** (attributo specifico da compilare per le sole API “a pagamento”):
       Indicazione delle tipologie di API level sulle quali l’API Provider si rende disponibile a stipulare accordi puntuali con specifici utilizzatori delle API.
   * - Dimensionamento dei flussi informativi
     - Informazioni circa le dimensioni dei flussi informativi in ingresso e in uscita dall'API.




.. _sezione252:

Impegni / capacità di erogazione
--------------------------------

E015 Digital Ecosystem prevede che normalmente le API siano erogate secondo una logica di tipo **Best effort**; è interesse degli API Provider erogare verso l’Ecosistema API di qualità al fine di incentivare un ampio utilizzo delle stesse da parte delle applicazioni. 
All’interno del descrittore il campo *“Impegni / capacità di erogazione”* offre all’API Provider la possibilità di comunicare all’Ecosistema, su base volontaria, le disponibilità e gli impegni di massima che esso si rende disponibile a sostenere per l’erogazione della propria API; ad esempio, l’API Provider può dichiarare all’interno del descrittore – relativamente al campo *“Impegni / capacità di erogazione”* –  il numero massimo di invocazioni giornaliere per Applicazione supportate dalla propria API. Tali informazioni rappresentano una utile indicazione verso il TMB per favorire l’ottimizzazione dell’utilizzo dell’API da parte delle applicazioni - sempre e comunque in una logica complessiva di tipo best effort [#f1]_ - e per promuovere il miglioramento progressivo nel tempo della qualità delle funzionalità esposte.

.. _sezione253:

Logiche di remunerazione
------------------------

Ciascun soggetto dell’Ecosistema ha la possibilità di perseguire proprie logiche di remunerazione legate all’erogazione delle API. È pertanto possibile che gli API Provider decidano di erogare le proprie API solo a soggetti con i quali è stato definito un accordo di tipo commerciale.

Al fine di dare evidenza di questa possibilità, gli API Provider devono specificare all’interno del descrittore se le proprie API sono disponibili a pagamento (attributo “Logiche di remunerazione”). In questo modo, E015 Digital Ecosystem facilita la stipulazione di accordi commerciali tra le diverse parti.
All’interno del descrittore, relativamente all’attributo “Logiche di remunerazione”, sarà possibile selezionare pertanto una delle seguenti opzioni:

1. **Free**: non è prevista alcuna forma di tariffazione; l’API è erogata gratuitamente ai soggetti autorizzati ad accedervi;

2. **A pagamento**: l’accesso all’API è soggetto a tariffazione.

Nel caso di API *“a pagamento”*, l’API Provider è tenuto a compilare anche i campi del descrittore *“Modelli di tariffazione supportati”*, *“Tipologie di QoS supportate”* e *“Referente commerciale”* al fine di indicare gli aspetti di interesse sulla base dei quali la tariffa di erogazione dell’API sarà concordata.

Si precisa che nel caso di API *“a pagamento”* la negoziazione della tariffa tra API Provider e i soggetti utilizzatori avviene al di fuori dell’Ecosistema.
Qualora l’API Provider desiderasse esporre all’interno dell’Ecosistema due versioni della medesima API, una *“free”* ed una *“a pagamento”* - per l’utilizzo della quale è necessario stipulare un accordo di tipo commerciale - è necessario procedere alla pubblicazione di due API distinte, ciascuna delle quali corredata da un proprio descrittore specifico.

.. _sezione2531:

Modelli di tariffazione supportati (API “a pagamento”)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Nel caso di API *“a pagamento”* l’API Provider deve specificare all’interno del descrittore, nel campo *“Modelli di tariffazione supportati”*, quali sono le modalità previste per il riconoscimento di un corrispettivo economico derivante dall’utilizzo dell’API da parte delle applicazioni.
Esempi di modelli di tariffazione che possono essere specificati all’interno di questo campo sono: pagamento una tantum, pagamento di un abbonamento, pagamento a consumo, pagamento in base alla QoS garantita ecc.

.. _sezione2532:

Tipologie di QoS supportate (API “a pagamento”)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Nel caso di API *“a pagamento”* per i quali sia previsto un modello di tariffazione basato su garanzie di qualità (QoS), è necessario che  l’API Provider compili il campo del descrittore *“Tipologie di QoS supportate”*.

All’interno di questo campo l’API Provider dichiara le tipologie di API level sulla base delle quali esso è disponibile a definire la tariffa di erogazione dell’API (stipulando in questo modo accordi di tipo commerciale). Esempi di possibili tipologie di API level sono: disponibilità dell’API, response time, volume di traffico per tipologia di transazioni campione, soglie di traffico, fasce orarie di erogazione ecc.

.. _sezione254:

Dimensionamento dei flussi informativi
--------------------------------------

Al fine di consentire ai soggetti utilizzatori di ottimizzare l’utilizzo delle API dell’Ecosistema, è data facoltà agli API Provider di fornire, nel campo “Dimensionamento dei flussi informativi”, alcune indicazioni circa le dimensioni (ad esempio, in kb) dei flussi informativi in ingresso e in uscita dall’API in corrispondenza di invocazioni campione rappresentative di un normale utilizzo.


.. rubric:: Footnotes

.. [#f1] Si precisa che le dichiarazioni riportate nel campo “Impegni / capacità di erogazione” hanno carattere puramente indicativo e non rappresentano un vincolo per l’ API Provider.


