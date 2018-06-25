.. _sezione28:

Policies delle API
==================

.. raw:: html

  <style> p,td,li,ol {text-align:justify; word-wrap:break-word} </style>

  <style> p.caption {text-align:center;} </style>

.. _sezione281:

Gli aspetti relativi alle policy all’interno del descrittore dell’API
---------------------------------------------------------------------

Si riportano nella tabella seguente i campi del descrittore dell’API che indirizzano direttamente gli aspetti legati alle policies delle API.

.. list-table:: Campi del descrittore relativi alla policy dell'API
   :align: center
   :header-rows: 1

   * - Campo
     - Descrizione
   * - | Policy generale
       | di utilizzo
     - | Riferimento al documento contenente
       | le condizioni di utilizzo dell’API
       | valide per tutti i soggetti utilizzatori.

.. _sezione282:

Approccio dell’Ecosistema per la gestione delle policy delle API
----------------------------------------------------------------

E015 Digital Ecosystem prevede che ogni API Provider stabilisca quali condizioni di utilizzo delle API i soggetti debbano impegnarsi a rispettare.
In particolare, è necessario che per ciascuno delle proprie API pubblicate l’API Provider specifichi all’interno del descrittore le relative **Policy generali di utilizzo**.
 
Tali policy indicano le condizioni di utilizzo dell’API comuni per tutti gli App Provider e devono essere accettate da parte di ogni soggetto utilizzatore che intende utilizzare la specifica API.
Se non rispettate, possono comportare l’inibizione da parte dell’API provider dell’accesso alla propria API.

In generale i soggetti aderenti godono della massima autonomia nella definizione di dettaglio di queste policy; il TMB fornisce un supporto indicando eventualmente possibili modelli di riferimento o segnalando eventuali situazioni che comportano un potenziale ridotto utilizzo delle API esposte. Esempi di possibili elementi contenuti all’interno delle policy generali / specifiche di utilizzo sono:


 * Proprietà dei dati erogati dalle API.

 * Possibilità di manipolare e/o modificare i dati erogati dalle API.

 * Clausole per l’utilizzo e la visualizzazione parziale dei dati erogati dall’API.

 * Clausole relative all’aggiornamento delle informazioni (Es: obbligo di mostrare agli utenti l’ora di aggiornamento).

 * Eventuale riferimento a framework di licensing già esistenti. Ad esempio:
      * Creative Commons.
      * Italian Open Data License.
      *  …

 * Clausole di esonero di responsabilità.

 * Clausole in merito alla storicizzazione delle informazioni erogate dalle API.

 * Eventuale riferimento al codice etico dell’API Provider.

 * Clausole relative alla privacy e alla eventuale gestione di dati sensibili.

 * Possibilità di visualizzare messaggi di tipo pubblicitario contestualmente alle informazioni erogate dalle API.

 * Obbligo di citare il soggetto erogatore delle informazioni:
      * semplice citazione testuale;
      * utilizzo di un logo.

 * Clausole relative ad eventuali sospensioni dell’erogazione dell’API.

 * Altro

.. questi per le ref:  ` ` non le virgolette 


In :ref:`Figura 2.9 <licenze>` è riportata una schematizzazione esemplificativa relativa a possibili framework di licensing già disponibili che gli API provider potrebbero decidere di referenziare e adottare all’interno delle proprie policy. Ad esempio:

1. per quanto concerne i *contenuti* erogati dalle API (file audio, immagini, video) è possibile utilizzare le licenze *Creative Commons*; nel caso in cui si volesse adottare un modello di licensing chiuso, gli API Provider possono decidere di proteggere i propri contenuti con diritti di copyright;

2. per quanto concerne i dati messi a disposizione (ad esempio, file corrispondenti a intere banche dati) è possibile utilizzare le licenze *Open Data Commons*; nel caso in cui si volesse adottare un modello di licensing chiuso, gli API Provider possono decidere di proteggere i propri dati con diritti di copyright;

3. per quanto concerne le API, è necessario definire all’interno delle Policy generali e all’interno delle Policy specifiche quali siano i Termini delle API previste.


.. _licenze:

.. figure::  pics/api_test/licensing.png
   :scale: 70 %
   :align:   center


   Figura 2.9: Esempi di modelli di licensing adottabili in E015 Digital Ecosystem



