.. _capitolo3:

***********************************************************************
Verifiche del Technical Management Board per la pubblicazione delle API
***********************************************************************

.. raw:: html

  <style> p,td,li,ol {text-align:justify; word-wrap:break-word} </style>

  <style> p.caption {text-align:center;} </style>

Il processo di pubblicazione di una API all’interno di E015 Digital Ecosystem prevede che il Technical Management Board effettui le verifiche necessarie a garantire che le API pubblicate posseggano tutte le caratteristiche di validità richieste dall’Ecosistema.

.. _sezione31:

Elementi di verifica da parte del Technical Management Board
============================================================

Una volta ricevuta da parte dell’API Provider la richiesta di pubblicazione di una API, corredata dal descrittore dell’API compilato in ogni sua parte, il Technical Management Board procede ad eseguire le seguenti verifiche:

1. **Verifica di completezza del descrittore**: tutti gli attributi obbligatori devono essere valorizzati ed adeguatamente documentati.

2. **Verifica della correttezza e della coerenza del descrittore**: tutti gli attributi devono essere compilati coerentemente con le Linee Guida del presente documento.

3. **Verifica di coerenza dell’API con le Linee Guida tecnologiche di E015 Digital Ecosystem**: l’API deve rispettare tutte le indicazioni tecnologiche fornite in questo documento.

4. **Test di invocazione dell’ API**: il TMB, attraverso opportuni strumenti, effettua delle invocazioni di test, verificando così il funzionamento dell’API e la consistenza del comportamento effettivo con quanto documentato all’interno del descrittore e della documentazione tecnica ad esso allegata. [#f1]_

5. **Verifica di disponibilità dell’API**: il TMB “aggancia” l’API al componente core di verifica di disponibilità al fine di verificare gli aspetti specifici relativi al monitoraggio. Sulla base dell’esito di tali verifiche il TMB comunicherà all’API Provider l’accettazione della richiesta di pubblicazione dell’API; in caso di rifiuto della richiesta, il TMB fornirà all’API Provider le indicazioni di “non conformità” al fine di consentire la risoluzione delle problematiche riscontrate, la rimozione di eventuali ostacoli al fine di favorire la successiva pubblicazione dell’API.

.. _sezione32:

Esito del processo di verifica
==============================


Come descritto nel paragrafo precedente, il processo di verifica delle API può concludersi positivamente o meno a seconda delle non conformità rilevate dal Technical Management Board in fase di verifica dell’API.
In caso di esito positivo del processo di verifica, il Technical Management Board dell’Ecosistema rilascia all’API Provider un resoconto con il dettaglio delle verifiche svolte contenente una attestazione di conformità dell’API alle Linee Guida per la pubblicazione delle API definite nell’Ecosistema e descritte nelle sezioni precedenti. Questa attestazione di conformità formalizza l’accettazione da parte dell’Ecosistema della richiesta di pubblicazione dell’API precedentemente inviata dall’API Provider e riconosce al soggetto aderente il ruolo di API Provider dell’Ecosistema.

In caso di esito positivo del processo di pubblicazione, il Technical Management Board include l’API all’interno del registro ufficiale delle API dell’Ecosistema e procede ad integrarlo all’interno dell’ambiente di *“preview”* dell’API (tale ambiente di *“preview”* costituisce una particolare sezione del registro delle API all’interno della quale viene data una dimostrazione reale - attraverso una interfaccia grafica interattiva – delle funzionalità erogate dall’API).

Qualora durante la sessione di verifica dell’API fossero rilevate dal Technical Management Board delle non conformità (lievi e comunque non bloccanti) rispetto alle linee guida descritte nei paragrafi precedenti, il report finale riporterà anche una serie di raccomandazioni per le quali il Technical Management Board richiede la definizione di un **piano di interventi** da parte dell'API Provider per superare le non conformità rilevate [#f2]_. 


.. rubric:: Footnotes

.. [#f1] Al fine di consentire al TMB di poter effettuare queste verifiche, è necessario che l’API Provider configuri il meccanismo di restrizione dell’accesso all’API (meccanismo di attestazione) al fine di garantire l’accesso programmatico da parte del TMB. In particolare, l’API Provider dovrà includere all’interno del trust store associato al proprio API il certificato client del TMB reso disponibile dall’Ecosistema.   

.. [#f2] La mancata definizione del piano di interventi per le singole raccomandazioni segnalate oppure il mancato rispetto dei tempi indicati nel piano di interventi definito dal API Provider può costituire motivo di revoca della pubblicazione del API all’interno dell’Ecosistema.
