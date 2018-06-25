.. _sezione22:

Accesso sicuro alle API
=======================

.. raw:: html

  <style> p,td,li,ol {text-align:justify; word-wrap:break-word} </style>
  <style> p.caption {text-align:center;} </style>

.. _sezione221:

Gli aspetti di sicurezza all’interno del descrittore dell’API
-------------------------------------------------------------

Si riportano nella tabella seguente i campi del descrittore che indirizzano direttamente gli aspetti legati all’accesso sicuro alle API.




.. list-table:: Campi del descrittore relativi all'accesso sicuro alle API
   :align: center
   :header-rows: 1

   * - Campo
     - Descrizione
   * - Livello di accesso
     - Indicazione del livello di accesso previsto per l’API. I valori ammissibili sono:

          1. **Community**: per API accessibili da parte di qualsiasi applicazione dell’Ecosistema;
          2. **Restricted**: per API con accesso limitato alle sole applicazioni dell’Ecosistema esplicitamente autorizzate.

   * - Attestazione Client
     - Riferimento al certificato d'accesso utilizzato
   * - Aspetti di sicurezza specifici
     - Riferimento a uno o più file allegati al descrittore che documentano eventuali aspetti di sicurezza specifici che è necessario conoscere per utilizzare correttamente l’API.

.. _sezione222:

L’approccio dell’Ecosistema per l’accesso sicuro alle API da parte delle Applicazioni
-------------------------------------------------------------------------------------

Nell’ambito di E015 Digital Ecosystem l’API Provider, per ciascuna delle API erogate, deve esplicitare all’interno del descrittore se intende consentire l’accesso a tutte le applicazioni dell’Ecosistema (senza la necessità di una autorizzazione esplicita) oppure se intende restringere l’accesso alle sole applicazioni autorizzate.
In particolare all’interno del descrittore, relativamente alla sezione “Accesso all’API”, sarà possibile selezionare una delle seguenti opzioni per l’attributo *“Livello di accesso”*:

 1. **Community**: L’API è accessibile da parte di tutte le applicazioni dell’Ecosistema senza la necessità di una autorizzazione esplicita da parte dell’API Provider. L’Ecosistema invia all’API Provider una notifica ogni qualvolta una API di tipo community viene richiesta da parte di un App Provider. In questo modo E015 Digital Ecosystem consente all’API Provider di essere a conoscenza di quali siano gli utilizzatori della propria API.

 2. **Restricted**: L’accesso è consentito alle sole applicazioni esplicitamente autorizzate da parte dell’ API Provider. In questo caso, l’Ecosistema inoltra agli API Provider le eventuali richieste di utilizzo ricevute da parte dei soggetti interessati e tiene traccia della risposta specificata da parte degli API Provider (di tipo “allow” / “deny”). In questo modo, E015 Digital Ecosystem è in grado di stabilire, ad un dato momento, quali applicazioni sono state esplicitamente autorizzate all’accesso. L’API Provider ha la possibilità in ogni momento di revocare l’accesso all’API da parte di una applicazione, ad esempio in seguito alla rilevazione di una violazione dei relativi termini di utilizzo [#f1]_.


Il meccanismo attraverso il quale E015 Digital Ecosystem consente agli API Provider di gestire la restrizione dell’accesso alle proprie API a tutte le applicazioni dell’Ecosistema (nel caso di API di tipo *Community*)  o alle sole applicazioni dell’Ecosistema esplicitamente autorizzate (nel caso di API *Restricted*) prende il nome di *“Meccanismo di attestazione”*.

Grazie al meccanismo di attestazione le API hanno la possibilità di determinare a quali applicazioni dell’Ecosistema appartengono le invocazioni ricevute.

Da un punto di vista operativo, la gestione dell’accesso sicuro alle API impatta su due fasi specifiche del processo di pubblicazione di una API:


1. *Descrizione dell’API*: In fase di compilazione del descrittore l’API Provider assegna all’attributo «Livello di accesso» il valore *Community* o *Restricted*.

 
2. *Richiesta di utilizzo delle API*: Quando un soggetto richiede di poter utilizzare una API per realizzare una applicazione, l’Ecosistema invia all’API Provider una notifica di richiesta di utilizzo.

Si possono verificare due casi:

* Se il livello di accesso è «Community» E015 Digital Ecosystem considera da subito la richiesta come accettata (l’Ecosistema tiene traccia della relazione di utilizzo instaurata); l’API Provider - oltre a prender visione del soggetto e dell’applicazione utilizzatrice dell’API esposta - abilita il meccanismo di accesso all’API per la specifica applicazione richiedente entro 10 giorni lavorativi dalla data di richiesta;


* Se il livello è «Restricted», l’API Provider notifica all’Ecosistema l’accettazione o meno della richiesta e l’Ecosistema la propaga al soggetto richiedente; l’API Provider si impegna ad evadere le richieste di utilizzo delle proprie API entro 10 giorni lavorativi dalla data di richiesta; in caso di accettazione, l’Ecosistema tiene traccia della relazione di utilizzo instaurata e l’API Provider abilita il meccanismo di accesso all’API per la specifica applicazione richiedente, entro 10 giorni lavorativi dalla data di richiesta.

In entrambi i casi, l’API Provider dovrà procedere alle attività tecniche di configurazione necessarie per consentire a run-time l’accesso all’API a tutti i soggetti autorizzati.

.. _sezione223:

Linee guida tecnologiche per la gestione dell’accesso alle API (meccanismo di attestazione)
-------------------------------------------------------------------------------------------

Il meccanismo di attestazione si basa sia sull’utilizzo di token (es. token generati nell’ambito dell’adozione dello standard OAuth2.0, SAML, API Key, Basic Authentication, …) sia sull’uso di certificati X.509 (http://www.itu.int/rec/T-REC-X.509/en), resi disponibili attraverso i registri ufficiali dell’Ecosistema.

Di seguito vengono riportati i passi che l’API Provider deve eseguire al fine di adottare il meccanismo di attestazione tramite *certificati X.509*:

* *Fase di descrizione e pubblicazione dell’API*:

     * L’API Provider crea una coppia di chiavi: una privata e una pubblica inserita in un certificato X.509, ottenendola da una authority esterna o auto generandola. L’API Provider referenzia la chiave pubblica (certificato X.509) nel descrittore della propria API (attributo “Certificato X.509”);

     * L’API Provider configura il proprio application server su cui viene eseguita l’API (ed eventualmente – se necessario – i propri apparati di rete) per l’utilizzo della chiave privata inserendola nel relativo keystore in modo da realizzare un endpoint HTTPS sul quale ricevere le richieste di utilizzo; lo stesso endpoint deve essere configurato per richiedere al client di presentare il proprio certificato.

* *Fase di gestione delle richieste di utilizzo*:
     * Una volta ricevuta tramite l’Ecosistema, e approvata, nel caso di API «Restricted», una richiesta di utilizzo da parte di un soggetto fruitore, l’API Provider ottiene il certificato dell’applicazione. Tale certificato è inviato all’API Provider da parte dell’Ecosistema contestualmente alla richiesta di utilizzo dell’API.

     * L’API Provider inserisce il certificato del soggetto fruitore nel trust-store dell’application server su cui viene eseguita l’API. La modalità con cui svolgere questa attività dipende dai componenti sistemistici specifici utilizzati dal singolo API Provider. In generale comunque, dal momento che ad ogni applicazione è associata una certificate chain, si potrà alternativamente:

          * inserire nel truststore il certificato foglia della certificate chain;

          * inserire nel truststore il certificato CA della certificate chain, configurando i propri appliance con regole specifiche per abilitare soltanto lo specifico certificato foglia (ad esempio, effettuando un controllo sul campo CN del certificato foglia associato a tale CA).

     Queste due alternative sono del tutto equivalenti dal punto di vista concettuale di gestione del meccanismo di attestazione; l’API Provider può decidere autonomamente quale perseguire in base alle specificità dei propri componenti hardware per la gestione delle connessioni SSL.

* *Fase di erogazione dell'API a runtime*
     * Una volta ricevuta una richiesta applicativa da parte di una App, l’application server dell'API verifica in automatico che il certificato presentato sia tra quelli presenti nel proprio truststore / sia firmato da parte di una delle CA presenti nel proprio truststore.

     * Se la verifica va a buon fine, l’application server instaura con il fruitore un canale di comunicazione sicuro (SSL/TLS con Client Authentication) e rende disponibile al livello applicativo il certificato del fruitore per consentire l’attuazione delle eventuali politiche di autorizzazione.

I certificati delle API, al fine di essere compatibili con E015 Digital Ecosystem, devono possedere una struttura conforme ai requisiti che seguono:

  * Durata: maggiore o uguale a 2 anni;
  * Basic Constraint: End Entity (quindi non-CA);
  * Key Usage (critical): Digital Signature e Key Encipherment;
  * Enhanced Key Usage: Server Authentication, Client Authentication;
  * Signature Algorithm: almeno *sha256RSA* per massimizzare la compatibilità con il software esistente.

È consentito l’utilizzo di certificati multi-dominio  nel caso si debba utilizzare un singolo certificato per  domini/API diversi (che rimangono comunque univocamente identificati da certificato e domain name). Questi certificati, denominati certificati ‘SAN’, riportano nel campo Subject Alternative Names l’elenco dei nomi di dominio per i quali il certificato deve essere considerato valido. Questo elenco viene definito al momento della creazione del certificato X509 indicando l’utilizzo dell’estensione ‘Subject Alternative Name’ e specificato come contenuto del campo Subject Alternative Name la lista di stringhe con l’elenco dei domini da considerare, nel seguente formato:  *‘DNS:<domainName1>, DNS:<domainName2>’*  (per maggiori dettagli si veda http://tools.ietf.org/html/rfc2818).

Il Technical Management Board presiede i processi per la gestione del meccanismo di attestazione:

* validando i certificati delle API all’atto della sottomissione del descrittore per approvazione;

* monitorando periodicamente la validità dei certificati pubblicati nei registri dell’Ecosistema e notificando agli API Provider la necessità di procedere al rinnovo in prossimità delle date di scadenza.

Si precisa che il ruolo di E015 Digital Ecosystem nella gestione del meccanismo di attestazione non è quello di emettere dei certificati, bensì quello di gestire l’albo ufficiale dei certificati delle API. Ciascun soggetto è libero infatti di decidere se acquisire i certificati X.509 da una authority esterna oppure se auto generarli [#f2]_.

.. _sezione224:

Linee guida tecnologiche per la gestione degli aspetti di sicurezza delle API
-----------------------------------------------------------------------------

Gestire la sicurezza nelle interazioni applicative tra API ed applicazioni di E015 Digital Ecosystem significa:

* fornire agli API provider opportuni strumenti per garantire proprietà dell’interazione quali: integrità e confidenzialità dei dati, prova della fonte, non ripudio ecc.;

* dare la possibilità agli API Provider di specificare i requisiti di sicurezza per l’accesso alle API erogate nell’Ecosistema.

I principali aspetti da considerare sono:

* gli strumenti per realizzare la sicurezza nelle interazioni applicative tra API;

* gli strumenti per permettere agli API Provider di specificare i requisiti di sicurezza delle proprie API.

.. _sezione2241:

Sicurezza e API SOAP
^^^^^^^^^^^^^^^^^^^^

Per quanto riguarda la realizzazione di API sicure, nel contesto dell’Ecosistema si fa riferimento in generale allo stack tecnologico dei Web API e al **WS-I Basic Security Profile 1.1**.


.. figure::  pics/api_test/security.png
   :scale: 50 %
   :align:   center


   Figura 2.4: WS-Stack e tecnologie di sicurezza



In particolare, il WS-I Basic Security Profile 1.1 definito dalla OASIS WS-I Organization (http://www.oasis-ws-i.org/) indica le specifiche tecnologie da utilizzare con riferimento alle dimensioni di interoperabilità relative alla sicurezza e al trasporto in ambito Web Service SOAP.


.. figure::  pics/api_test/WSbasicsecurityprofile.png
   :scale: 80 %
   :align:   center


   Figura 2.5: WS-I Basic Security Profile 1.1 e tecnologie considerate


Lo standard OASIS WS-Security: SOAP Message Security (http://docs.oasis-open.org/wss/v1.1/) definisce diverse estensioni al protocollo SOAP al fine di garantire la protezione end-to-end dei messaggi scambiati nelle interazioni tra Web API SOAP. In particolare, i tre principali meccanismi forniti dallo standard  sono:

* la possibilità di veicolare **token di sicurezza** come parte di un messaggio SOAP;

* la tutela dell’**integrità** del messaggio SOAP;

* la tutela della **confidenzialità** del messaggio SOAP.


Alla base di WS-Security c’è il concetto di *security token*: costrutti che possono essere usati all’interno dei messaggi SOAP (in particolare nell’header) per rappresentare e veicolare informazioni (per esempio di identità, oppure relative ai meccanismi di processing da eseguire per validare i token stessi). Lo standard WS-Security permette di usare diversi tipi di token: binari, basati su XML (tra cui rientrano le asserzioni SAML), criptati e altri ancora. Per la protezione di integrità e confidenzialità, WS-Security utilizza standard come XML-Signature e XML-Encription, applicandoli a determinate parti del messaggio SOAP.

In aggiunta al WS-I Basic Security Profile 1.1, per permettere agli API Provider di specificare i requisiti di sicurezza delle proprie API si considerano i seguenti standard:

* **WS-Policy** (http://www.w3.org/TR/ws-policy/) definisce un framework e un modello per rappresentare le policy di sicurezza di una API mediante descrizioni machine-readable: una policy può ad esempio descrivere i requisiti di sicurezza (autenticazione, autorizzazione ecc.) che il richiedente deve soddisfare per poter accedere a un API, oppure la messa in atto da parte dell’API Provider di determinati meccanismi come il tracciamento dei messaggi applicativi. Per esempio, tramite una policy WS-Policy un Web API può comunicare di essere in grado di accettare asserzioni SAML 2.0. WS-Policy non entra nel merito della rappresentazione delle caratteristiche di una API: a tal fine possono essere usate altre specifiche, per esempio WS-SecurityPolicy.

* **WS-SecurityPolicy** (http://www.oasis-open.org/standards#ws-secpol) definisce le modalità di rappresentazione delle specifiche capacità o degli specifici requisiti di sicurezza di una API. Per esempio, grazie a WS-SecurityPolicy, è possibile scrivere una policy assertion per richiedere la presenza di un determinato elemento nell’header del messaggio SOAP.

I requisiti di sicurezza di un API così descritti possono diventare parte integrante del descrittore del API.

.. _sezione2242:

Sicurezza e API REST
^^^^^^^^^^^^^^^^^^^^

Per le API REST in generale non esistono standard specifici per la gestione della sicurezza. Nell’ambito di E015 Digital Ecosystem è raccomandato l’utilizzo delle strategie e meccanismi di sicurezza comunemente utilizzate per l’accesso a web application (sicurezza di canale con SSL/TLS ecc.). Il Technical Management Board si riserva di accettare meccanismi di autenticazione differenti, purché adeguatamente documentati.


.. rubric:: Footnotes

.. [#f1] Anche in questo caso, è necessario che l’API provider comunichi all’Ecosistema l’avvenuta revoca dell’accesso.

.. [#f2] In generale è auspicabile l’acquisizione dei certificati presso authority esterne; al fine di garantire l’inclusività di un ampio numero di soggetti, E015 – Digital Ecosystem consente comunque l’uso di certificati auto generati.

