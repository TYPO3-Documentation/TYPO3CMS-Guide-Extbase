.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:format.padding
================

Padding

Eigenschaften
-------------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Property
   :Datatype,20:    Variable type
   :Description,40: Description
   :Standard,10:    Default value
   :Mandatory,10:   Mandatory

 - :Property:    padLength
   :Datatype:    Integer
   :Description: Wie viel Zeichen lang darf der Text inkl. der hinzugefügten Abstandszeichen maximal werden
   :Standard:
   :Mandatory:   Yes

 - :Property:    padString
   :Datatype:    String
   :Description: Welches Zeichen soll als Abstand dienen
   :Standard:    Leerzeichen
   :Mandatory:   No

 - :Property:    padType
   :Datatype:    String
   :Description: Wo sollen die Abstandszeichen eingefügt werden. Zur Auswahl steht right, left und both
   :Standard:    right
   :Mandatory:   No

Beispiel zur Funktionsweise
---------------------------

::

 <p><f:format.padding padLength="10" padString="-=">TYPO3</f:format.padding>ist cool</p>
 <p><f:format.padding padLength="10" padString="#">Stefan</f:format.padding>ist cool</p>
 <p><f:format.padding padLength="10" padString=" ">Ich</f:format.padding>bin cool</p>

In diesem Beispiel wird das angegebene Zeichen oder die Zeichen solange wiederholt, bis das Maximum an Zeichen erfüllt ist. Je nach Zeichensatz macht diese Darstellung wenig Sinn. Denn wie Ihr seht beginnen die letzten beiden Wörter je Zeile immer an einer unterschiedlichen Stelle.

Beispiel mit sinnvoller Einrückung
----------------------------------

::

 <pre><f:format.padding padLength="10" padString=" ">TYPO3</f:format.padding>ist cool<br />
 <f:format.padding padLength="10" padString=" ">Stefan</f:format.padding>ist cool<br />
 <f:format.padding padLength="10" padString=" ">Ich</f:format.padding>bin cool</pre>

Hier nahezu das gleiche Beispiel wie oben. Allerdings fangen die letzten beiden Wörter je Zeile nun immer an der
gleichen Position an. Mit Hilfe diesen ViewHelpers könnte man also so eine Art Tabulator erstellen.