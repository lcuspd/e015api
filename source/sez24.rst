.. _sezione24:

Aspetti relativi al monitoraggio delle API
==========================================

.. raw:: html

  <style> p,td,li,ol {text-align:justify; word-wrap:break-word} </style>

  <style> p.caption {text-align:center;} </style>
.. _sezione241:

Gli aspetti relativi al monitoraggio all’interno del descrittore delle API
--------------------------------------------------------------------------

Si riportano nella tabella seguente i campi del descrittore delle API che indirizzano direttamente gli aspetti legati all’interoperabilità delle API.




.. list-table:: Campi del descrittore relativi al monitoraggio
   :align: center
   :header-rows: 1

   * - Campo
     - Descrizione
   * - Endpoint di monitoraggio
     - Endpoint per il controllo di disponibilità dell'API
   * - Invocazioni di test per monitoraggio
     - Formulazione delle invocazioni di test da utilizzare per la verifica di disponibilità dell’API e per la verifica della correttezza delle risposte ottenute.
   * - Frequenza di monitoraggio
     - Indicazione da parte dell’API Provider di una frequenza di monitoraggio compatibile col tipo di API erogata per quello specifico dominio.
   * - Segnalazioni specifiche
     - **Opzionale**: es. down quotidiani programmati per attività di manutenzione

.. _sezione242:

L’approccio dell’Ecosistema per il monitoraggio delle API
---------------------------------------------------------

In generale è di interesse per l’Ecosistema poter verificare su base continuativa se le API sono attive e come/quanto queste vengono usate da parte delle applicazioni.
Per questo motivo, l’Ecosistema prevede dei meccanismi di base per il monitoraggio continuativo delle API pubblicate; in particolare, a partire dalla  versione 1 verrà effettuato un **controllo di disponibilità** delle API.
Al fine di consentire a E015 Digital Ecosystem di poter effettuare tale controllo, l’API Provider è tenuto a specificare all’interno del descrittore dell’API un endpoint di monitoraggio e ad esprimere una frequenza di monitoraggio compatibile con il tipo di API erogata. 
Inoltre l’API Provider deve fornire all’interno del descrittore anche delle invocazioni “campione” di test (request e response), le quali saranno utilizzate dall’Ecosistema per la verifica di disponibilità dell’API e per la verifica della correttezza delle risposte ottenute.
L’Ecosistema utilizza l’endpoint di monitoraggio specificato nel descrittore per controllare periodicamente l’effettiva disponibilità dell’API (attraverso un semplice meccanismo di “ping”) e per effettuare delle invocazioni di test sulla base delle invocazioni “campione” specificate dall’API provider all’interno del descrittore.

Da un punto di vista operativo, la gestione degli aspetti di monitoraggio delle API erogate impatta su due fasi specifiche del processo di pubblicazione e di erogazione delle API:

1. *Descrizione dell’API*: In fase di compilazione del descrittore dell’API, l’API Provider compila gli attributi: *“Endpoint di monitoraggio”*, *“Invocazioni di test per monitoraggio”* e *“Frequenza di monitoraggio”* (utilizzati dall’Ecosistema per effettuare il controllo di disponibilità e di correttezza delle risposte delle API), *“Messaggi di indisponibilità”* (opzionale), *“Test suite”* (opzionale) , *“Endpoint ambiente di test”* (opzionale) e *“Segnalazioni specifiche”* (opzionale).

2. *Erogazione dell’API*: A run-time E015 Digital Ecosystem effettua periodicamente il controllo di disponibilità delle API e verifica la correttezza delle risposte ricevute in seguito alle invocazioni campione specificate nel descrittore. Il monitoraggio è effettuato “ai morsetti esterni” dell'API, poiché indica il livello di disponibilità con cui è percepito l’API dall’Ecosistema.

Il TMB utilizza i dati di monitoraggio per comprendere il livello di qualità dell’API erogata (in termini di disponibilità) e in seguito restituire tale informazione all’API Provider, nonché diffondere l’andamento del monitoraggio alle applicazioni che utilizzano l’API esposta.


