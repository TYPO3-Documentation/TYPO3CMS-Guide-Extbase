.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:format.padding
================

Padding

Properties
----------

 - :Property:    padLength
:aspect:`Variable type`
    Integer

:aspect:`Description`
    Wie viel Zeichen lang darf der Text inkl. der hinzugefügten Abstandszeichen maximal werden
   :Standard:

:aspect:`Mandatory`
    Yes

 - :Property:    padString
:aspect:`Variable type`
    String

:aspect:`Description`
    Welches Zeichen soll als Abstand dienen

:aspect:`Default value`
    Leerzeichen

:aspect:`Mandatory`
    No

 - :Property:    padType
:aspect:`Variable type`
    String

:aspect:`Description`
    Wo sollen die Abstandszeichen eingefügt werden. Zur Auswahl steht right, left und both

:aspect:`Default value`
    right

:aspect:`Mandatory`
    No

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