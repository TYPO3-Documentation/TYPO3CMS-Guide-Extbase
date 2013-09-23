.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:be.container
==============

Zu allererst solltet Ihr Euch eine grundsätzliche Frage stellen: Willst Du etwas entwickeln ganz im Stile von TYPO3
oder willst Du etwas völlig Eigenes bauen. Wenn Ihr Euch für etwas völlig Eigenes entscheidet, dann braucht Ihr diesen
ViewHelper überhaupt nicht. Bindet in diesem Falle Eure benötigten StyleSheets und JavaScripte selbst ein.

Wenn Ihr allerdings etwas bauen wollt, dass sich an das TYPO3-Design anlehnt und möglichst kompatibel sein soll,
dann solltet Ihr diesen ViewHelper auf jeden Fall verwendet. Das was damals zu Zeiten von MediumDoc und Co.
eingebunden wurde, benötigt heute nur noch diesen Zweizeiler mit knapp 10 Parametern.

Eigenschaften
-------------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Eigenschaft
   :Datatype,20:    Datentyp
   :Description,40: Beschreibung
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    pageTitle
   :Datatype:    String
   :Description: BE-Module werden in einem Frame dargestellt, von daher macht ein Seitentitel wenig sind. Einfach leer lassen
   :Standard:    Leerer String
   :Mandatory:   Nein

 - :Property:    enableJumpToUrl
   :Datatype:    Boolean
   :Description: Lasst diesen Parameter eingeschaltet, wenn Ihr den ActionMenu-ViewHelper verwenden wollt, da dieser die entsprechenden JavaScripte dazu liefert.
   :Standard:    TRUE
   :Mandatory:   Nein

 - :Property:    enableClickMenu
   :Datatype:    Boolean
   :Description: Wenn aktiviert, wird das JavaScript für die Contextmenüs eingebunden
   :Standard:    TRUE
   :Mandatory:   Nein

 - :Property:    loadPrototype
   :Datatype:    Boolean
   :Description: Wenn aktiviert, wird das Prototype-JS-Framework eingebunden
   :Standard:    TRUE
   :Mandatory:   Nein

 - :Property:    loadScriptaculous
   :Datatype:    Boolean
   :Description: Wenn aktiviert, wird das Zusatzpaket für Prototype eingebunden
   :Standard:    FALSE
   :Mandatory:   Nein

 - :Property:    scriptaculousModule
   :Datatype:    String
   :Description: Ihr könnt hier noch weitere Module für das Scriptaculouspaket aktivieren
   :Standard:    Leerer String
   :Mandatory:   Nein

 - :Property:    loadExtJs
   :Datatype:    Boolean
   :Description: Wenn aktiviert, wird das ExtJS-Framework eingebunden
   :Standard:    FALSE
   :Mandatory:   Nein

 - :Property:    loadExtJsTheme
   :Datatype:    Boolean
   :Description: Wenn aktiviert, werden Vorgaben für die Grafischen Elemente eingebunden.
   :Standard:    TRUE
   :Mandatory:   Nein

 - :Property:    extJsAdapter
   :Datatype:    String
   :Description: Statt dem Standard ext-base kann hier ein anderer Adapter angegeben werden.
   :Standard:    Leerer String
   :Mandatory:   Nein

 - :Property:    enableExtJsDebug
   :Datatype:    Boolean
   :Description: Sollte nur aktiviert werden, wenn man auf Basis von ExtJS entwickelt.
   :Standard:    FALSE
   :Mandatory:   Nein

 - :Property:    addCssFile
   :Datatype:    String
   :Description: Eine CSS-Datei einbinden
   :Standard:    NULL
   :Mandatory:   Nein

 - :Property:    addJsFile
   :Datatype:    String
   :Description: Eine JavaScript-Datei einbinden
   :Standard:    NULL
   :Mandatory:   Nein

 - :Property:    loadJQuery
   :Datatype:    Boolean
   :Description: Soll jQuery als JavaScript Framework eingebunden werden?
   :Standard:    FALSE
   :Mandatory:   Nein

 - :Property:    includeCssFiles
   :Datatype:    Array
   :Description: Während addCssFile nur eine CSS-Datei einbinden kann, können mit dieser Eigenschaft mehrere
                 CSS-Dateien eingebunden werden.
   :Standard:    NULL
   :Mandatory:   Nein

 - :Property:    includeJsFiles
   :Datatype:    Array
   :Description: Während addJsFile nur eine JS-Datei einbinden kann, können mit dieser Eigenschaft mehrere
                 JS-Dateien eingebunden werden.
   :Standard:    NULL
   :Mandatory:   Nein

 - :Property:    addJsInlineLabels
   :Datatype:    Array
   :Description: Jeder Wert in diesem Array muss einem Key aus der locallang.xml/xlf entsprechen. Diese Übersetzung
                 wird dann im Backend zur Verfügung gestellt.
   :Standard:    NULL
   :Mandatory:   Nein
