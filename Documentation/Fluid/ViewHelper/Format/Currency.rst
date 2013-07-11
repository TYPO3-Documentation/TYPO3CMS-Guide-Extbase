.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:format.currency
=================

Mit diesem ViewHelper könnt Ihr Zahlen als Währung darstellen lassen.

Eigenschaften
-------------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Eigenschaft
   :Datatype,20:    Datentyp
   :Description,40: Beschreibung
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    currencySign
   :Datatype:    String
   :Description: Das Währungskennzeichen wie $ oder €. Dieses Zeichen wird immer hinter der Währung angezeigt.
   :Standard:    Leerer String
   :Mandatory:   Nein

 - :Property:    decimalSeperator
   :Datatype:    String
   :Description: Welcher Zeichen soll für die Trennung von Euro und Cent verwendet werden. Dezimaltrenner.
   :Standard:    ,
   :Mandatory:   Nein

 - :Property:    thousandsSeperator
   :Datatype:    String
   :Description: Welches Zeichen soll als Tausendertrennzeichen verwendet werden.
   :Standard:    .
   :Mandatory:   Nein

 - :Property:    prependCurrency
   :Datatype:    Boolean
   :Description: Soll das Währungssymbol VOR die Währung gesetzt werden?
   :Standard:    FALSE
   :Mandatory:   Nein

 - :Property:    separateCurrency
   :Datatype:    Boolean
   :Description: Soll das Währungssymbol durch ein Leerzeichen von der Währung getrennt werden?
   :Standard:    TRUE
   :Mandatory:   Nein

 - :Property:    decimals
   :Datatype:    Integer
   :Description: Wie viele Stellen nach dem Komma sollen angezeigt werden?
   :Standard:    2
   :Mandatory:   Nein

Zwei wichtige Informationen:

Übergebt Ihr an diesen ViewHelper einen leeren Text, dann benötigt die in diesem ViewHelper befindliche Funktion
number_format knapp 23 Millisekunden. Liefert Ihr dieser Funktion stattdessen direkt ein 0.00 ist die Funktion
in 1-2 Millisekunden durch. Wichtig wenn Ihr mit langen Listen arbeitet.

Ihr dürft diesem ViewHelper keine Zahlen mit einem Komma als Dezimaltrenner mitgeben. Siehe Beispiel.

Beispiel
--------

::

 <f:format.currency currencySign="$" decimalSeparator="." thousandsSeparator=",">1122334455.66</f:format.currency>

ergibt: 1,122,334,455.66 $

Beispiel mit nicht float kompatiblen Zahlen
-------------------------------------------

::

 <f:format.currency currencySign="$" decimalSeparator="." thousandsSeparator=",">1122334455,66</f:format.currency>

ergibt: 1,122,334,455.00 $