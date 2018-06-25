.. _sezione23:

Glossari delle API
==================

.. raw:: html

  <style> p,td,li,ol {text-align:justify; word-wrap:break-word} </style>

  <style> p.caption {text-align:center;} </style>

.. _sezione231:

Gli aspetti relativi ai glossari all’interno del descrittore delle API
----------------------------------------------------------------------

Si riportano nella tabella seguente i campi del descrittore delle API che indirizzano direttamente gli aspetti legati all’interoperabilità delle API.

.. raw:: html

  <style> .line {text-align:justify; word-wrap:break-word} </style>


.. list-table::
   :align: center
   :header-rows: 1

   * - Campo
     - Descrizione
   * - Usi di glossari condivisi
     - Riferimento ad eventuali glossari condivisi dell’Ecosistema utilizzati da parte delle API


.. _sezione232:

Linee Guida per la gestione dei glossari all’interno dell’Ecosistema
--------------------------------------------------------------------

Un primo importante aspetto che indirizza la gestione dei Glossari all’interno dell’Ecosistema riguarda il modello dei dati di una API.
Il **modello dei dati** di una API identifica e descrive:

* le entità e i concetti utilizzati nell’interazione con entità esterne per l’erogazione di funzionalità;

* la rappresentazione di tali entità e concetti (per esempio le modalità di  serializzazione in costrutti XML da utilizzare nei messaggi di richiesta e risposta).

Pertanto è opportuno che il modello dei dati delle API dell’Ecosistema sia adeguatamente documentato, formalizzato e strutturato:

* la **documentazione** può consistere in una descrizione testuale (eventualmente guidata da un template comune);

* la **formalizzazione** può consistere in una rappresentazione dei concetti mediante opportuni linguaggi di descrizione (diagrammi UML http://www.uml.org/ , E-R ecc.);

* la **strutturazione** è la rappresentazione basata su una specifica tecnologia (per esempio un linguaggio di markup come XML) utilizzata dalla specifica API o applicazione.

Se adeguatamente descritti, formalizzati, strutturati e condivisi, i modelli dei dati abilitano il riuso nell’ambito di E015 Digital Ecosystem; diverse API e applicazioni infatti spesso utilizzano nel proprio modello dei dati gli stessi concetti, dunque:

* potrebbe essere già disponibile una rappresentazione degli stessi concetti;

* rappresentazioni di nuovi concetti potrebbero essere condivise con altri provider dell’Ecosistema.


.. figure::  pics/api_test/modellodati.png
   :scale: 55 %
   :align:   center


   Figura 2.6: Modello dei dati: documentazione, formalizzazione, rappresentazione e utilizzo


L’approccio indicato per E015 Digital Ecosystem propone e incentiva l’adozione di **glossari condivisi** per favorire l’interoperabilità e il riuso nella realizzazione di API e delle applicazioni da parte dei soggetti aderenti all’ecosistema, difatti:

* I glossari condivisi permettono sia di classificare le API che di adottare modelli dei dati comuni;

* I glossari condivisi possono rappresentare un patrimonio informativo utilizzabile; 

* È di interesse il potenziale ruolo degli operatori di dominio e/o delle associazioni di categoria per la definizione e l’evoluzione dei glossari;

* È importante promuovere l’inclusione nell’ecosistema di glossari e standard già esistenti in alcuni settori.


Condivisione e riuso di un modello dei dati possono avvenire a diversi “livelli” di specializzazione: i glossari infatti possono coprire concetti generali (tempo, geo-localizzazione ecc.), concetti di specifici domini applicativi (turismo, trasporti, enogastronomia, alberghiero ecc.), concetti specifici di una singola applicazione o di una singola API.


.. figure::  pics/api_test/glossario.png
   :scale: 50 %
   :align:   center


   Figura 2.7: Possibili livelli di specializzazione di un glossario


Inoltre, i glossari condivisi possono essere più o meno formalizzati: da semplici tag, keyword o vocabolari si può arrivare a tassonomie complete o ad una vera e propria formalizzazione in ontologie.
In fase di sottomissione di una nuova API da pubblicare all’interno dell’Ecosistema il TMB verificherà l’eventuale presenza di glossari già disponibili e di potenziale interesse per l'API Provider, rispetto ai quali rendere coerente l’interfaccia ad il modello dei dati dell’ API stessa.


