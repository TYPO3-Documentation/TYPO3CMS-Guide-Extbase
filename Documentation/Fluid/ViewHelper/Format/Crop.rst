.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:format.crop
===============

Schneidet Text zurecht

Eigenschaften
-------------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Eigenschaft
   :Datatype,20:    Datentyp
   :Description,40: Beschreibung
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    maxCharacters
   :Datatype:    Integer
   :Description: Anzahl Zeichen nach denen abgeschnitten werden soll.
   :Standard:
   :Mandatory:   Ja

 - :Property:    append
   :Datatype:    String
   :Description: Ein Text oder eine Anzahl Zeichen, die dem Text angefügt werden soll.
   :Standard:    ...
   :Mandatory:   Nein

 - :Property:    respectWordBoundaries
   :Datatype:    Boolean
   :Description: Solange dieser Wert aktiviert ist und ein Schnitt innerhalb eines Wortes geschehen würde, wird dieser Schnitt VOR dem Wort ausgeführt, um das Wort nicht zu stückeln. Mit FALSE zwingt man den ViewHelper zum Trennen IM Wort.
   :Standard:    TRUE
   :Mandatory:   Nein

 - :Property:    respectHtml
   :Datatype:    Boolean
   :Description: Bei TRUE werden HTML-Tags berücksichtigt. Bei FALSE kann es vorkommen,
                 dass die Trennung innerhalb des HTML-Tag statt findet.
   :Standard:    TRUE
   :Mandatory:   Nein

Beispiel
--------

::

 <f:format.crop maxCharacters="14">Diesen Text werden wir jetzt zerschnibbeln</f:format.crop>

Normalerweise würde dieser Befehl das Wort "werden" auftrennen. Aber dadurch dass "respectWordBoundaries" per default
gesetzt ist erhalten wir diese Ausgabe:

Diesen Text...

Beispiel: Trennung im Wort
--------------------------

::

 <f:format.crop maxCharacters="14" respectWordBoundaries="FALSE">Diesen Text werden wir jetzt zerschnibbeln</f:format.crop>

ergibt

Diesen Text we...

Beispiel mit respectHtml = FALSE
--------------------------------

::

 <f:format.crop maxCharacters="25" respectHtml="FALSE"><p>Diesen Text <strong>werden</strong> wir jetzt zerschnibbeln</p></f:format.crop>

ergibt

Diesen Text...

Wie oben schon erwähnt, liegt das daran, dass nun auch alle Buchstaben der HTML-Tags mitgezählt werden.