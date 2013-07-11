.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM. ÄÖÜäöüß

.. include:: ../Includes.txt

Dispatcher
==========

Der Dispatcher kümmert sich darum für die aktuelle Anfrage an eine Webseite eine Klasse zu finden,
die diesen Webseitenaufruf verarbeiten kann. Hat er eine Klasse gefunden, ruft der Dispatcher die Methode
*handleRequest* der gefundenen Klasse auf und erhält den Inhalt als Ergebnis wieder zurück. Dieses Ergebnis wird dann
als Webseiteninhalt ausgegeben.

Hier nun der Weg bis zum Dispatcher Schritt für Schritt:

RequestHandler
--------------

Extbase bringt von Haus aus ein paar Klassen für die unterschiedlichen Webseitenaufrufe mit und stellt diese über die
ext_typoscript_setup.txt zur Verfügung::

 config.tx_extbase {
   mvc {
     requestHandlers {
       Tx_Extbase_MVC_Web_FrontendRequestHandler = Tx_Extbase_MVC_Web_FrontendRequestHandler
       Tx_Extbase_MVC_Web_BackendRequestHandler = Tx_Extbase_MVC_Web_BackendRequestHandler
       Tx_Extbase_MVC_CLI_RequestHandler = Tx_Extbase_MVC_CLI_RequestHandler
     }
   }
 }

Somit stellt Extbase sogenannte *RequestHandler* für Anfragen aus dem Frontend, dem Backend und Anfragen,
die über die Shell/CLI kommen bereit.

Dank dieser TypoScript Konfiguration habt Ihr die Möglichkeit auch eigene *RequestHandler* zu registrieren. So
könnt Ihr zum Beispiel einen *RequestHandler* für AJAX-Anfragen erstellen und hier bekannt machen.

Welcher *RequestHandler* nun den aktuellen Webseitenaufruf verarbeiten kann entscheidet sich über die Methode
*canHandleRequest* innerhalb eines jeden *RequestHandlers*. Dieser schaut beim BackendRequestHandler
so aus::

 canHandleRequest*() {
   return TYPO3_MODE === 'BE';
 }

Bei der Angabe eigener *RequestHandler* kann es aber durchaus vorkommen, dass sowohl Euer *RequestHandler* als auch
der *RequestHandler* von Extbase für das Frontend zuständig sind. Also 2 *RequestHandler* kommen für den aktuellen
Webseitenaufruf in Frage. Da aber nur EIN *RequestHandler* erlaubt ist, gibt es für dieses Dilemma die Möglichkeit
jedem *RequestHandler* eine Priorität zuzuordnen. Für den Front- und Backend-*RequestHandler* setzt Extbase diese
Priorität auf 100. 90 ist die Priorität für CLI-Anfragen. Setzt also eine höhere Priorität,
wenn Euer eigener *RequestHandler* Vorrang erhalten soll.

RequestBuilder
--------------

Jetzt nachdem nur noch ein *RequestHandler* übrig geblieben ist, wird die enthaltene Methode *handleRequest*
ausgeführt. Diese Methode erstellt mit Hilfe des *RequestBuilders* ein Objekt, das alle benötigten Daten für den
Webseitenaufruf zusammen stellt. Er durchsucht die Pluginkonfiguration in der ext_localconf.php,
um heraus zu finden welcher Controller und welche Action als Standard verwendet werden sollen (Methode:
*loadDefaultValues*). Ebenso liest der *RequestBuilder* die Webseiten-Uri aus, um zu prüfen,
ob evtl. ein anderer Controller/eine andere Action statt den Angaben aus der ext_localconf.php geladen werden sollen.

Sämtliche Daten des Webseitenaufrufes werden nun zusammen gestellt und stehen anschließend in dem Objekt *$request*
zur späteren Verfügung::

 $request = $this->objectManager->create('Tx_Extbase_MVC_Web_Request');
 $request->setPluginName($this->pluginName);
 $request->setControllerExtensionName($this->extensionName);
 $request->setControllerName($controllerName);
 $request->setControllerActionName($actionName);
 $request->setRequestUri(t3lib_div::getIndpEnv('TYPO3_REQUEST_URL'));
 $request->setBaseUri(t3lib_div::getIndpEnv('TYPO3_SITE_URL'));
 $request->setMethod((isset($_SERVER['REQUEST_METHOD'])) ? $_SERVER['REQUEST_METHOD'] : NULL);

Abschließend werden die Parameter, die nur für dieses eine Plugin gültig sind, dem $request-Objekt als Argumente
hinzugefügt::

 foreach ($parameters as $argumentName => $argumentValue) {
   $request->setArgument($argumentName, $argumentValue);
 }

RequestHashService
------------------

Alle Daten für den aktuellen Webseitenaufruf wurden im *Request*-Objekt hinterlegt. Zeit zu überprüfen,
ob die Daten sauber sind. Der *RequestHashService* prüft, ob sich im *Request*-Object ein __hmac-Argument befindet.
Das ist immer dann der Fall, wenn Formulardaten übertragen wurden. Extbase weiß,
welche Formulardaten auf der Webseite angezeigt werden. Hat sich die Anzahl der Felder beim Übertragen der Daten
verändert, dann wurde möglicherweise das Formular kompromitiert und das Verarbeiten der Daten wird gestoppt. Ist das
hmac-Argument nicht enthalten handelt es sich um ganz normale Webseitenaufrufe und die Inhaltsgenerierung kann
gestartet werden

Response
--------

Es wird nun ein Antwort-Objekt erstellt, das die Headerdaten beinhaltet. Das sind zum einen die Statuscodes wie
Fehler 404 und für die Inhaltsausgabe benötigte JavaScript und CSS-Dateien. Dieses Objekt ist derzeit noch leer,
wird aber im nächsten Schritt, dem sogenannten *Dispatching* befüllt.

Der Dispatcher
--------------

Der Dispatcher holt sich aus dem Request-Objekt den Controllernamen und erstellt über die Methode *resolveController*
das zum Controller gehörende Objekt. In der Beispielextension *productoverview* ist das die Klasse
*Tx_Productoverview_Controller_ProductController*.

Das Objekt $request und das noch leere Objekt $response wird nun an die Methode *processRequest* des Controllers
übergeben. Ab hier endet die Aufgabe des Dispatchers. Er wartet nur noch darauf aus dem Controllerobjekt die Daten
zurück zu bekommen, setzt dann die HTTP-Header, die während des Prozesses im $response-Objekt gesetzt wurden und
liefert den generierten Inhalt zurück an das Inhaltsobjekt *USER* vom TypoScript,
welches den Inhalt schlussendlich ausgibt.