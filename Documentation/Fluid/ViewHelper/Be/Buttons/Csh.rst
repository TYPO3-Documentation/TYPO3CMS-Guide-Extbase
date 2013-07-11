.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../../Includes.txt

f:be.buttons.csh
================

Eigentlich viel zu selten verwendet. Aber so ist es nun mal mit der Dokumentation. Mit diesem ViewHelper könnt Ihr
dem Benutzer kleine Hilfestellungen geben, was sie z.B. in ein bestimmtes Feld eingeben sollen. TYPO3 selbst verwendet
es nahezu durchgängig und Ihr erkennt es an diesen kleinen runden Fragezeichen in der Nähe eines jeden Eingabefeldes.
Wenn Ihr mit der Maus drüberfahrt und knapp ne Sekunde oder 2 wartet, dann erscheint der kurze Hilfetext. Klickt Ihr
auf das Icon öffnet sich ein PopUp mit weiteren Informationen zu diesem Eingabefeld. In den Benutzereinstellungen
könnt Ihr einstellen, ob dieses PopUp nach einem Klick erscheinen soll oder nicht.

Eigenschaften
-------------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Eigenschaft
   :Datatype,20:    Datentyp
   :Description,40: Beschreibung
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    table
   :Datatype:    String
   :Description: Der Tabellenname
   :Standard:    NULL
   :Mandatory:   Ja

 - :Property:    field
   :Datatype:    String
   :Description: Der Key aus der Sprachdatei
   :Standard:    Leerer String
   :Mandatory:   Ja

 - :Property:    iconOnly
   :Datatype:    Boolean
   :Description: Es wird nur das Bildchen dargestellt, nicht aber der Hilfetext
   :Standard:    FALSE
   :Mandatory:   Ja

 - :Property:    styleAttributes
   :Datatype:    String
   :Description: Zusätzliches style-Attribut, das in die umschließende Tabelle eingebunden wird
   :Standard:    Leerer String
   :Mandatory:   Ja

Beispiel
--------

Bei den Tabellen von TYPO3 haben wir meist Glück, dass der key innerhalb der Hilfe-Sprachdatei gleich dem
Spaltennamen ist:

::

 <f:be.buttons.csh table="tt_content" field="header" />

Beispiel mit Stil
-----------------

Damit dieses Beispiel funktioniert müsst Ihr zuallererst sicherstellen, dass in der userTSconfig folgende
Einstellung getroffen wurde:

::

 setup.override.edit_showFieldHelp=text

Erst jetzt könnt Ihr sehen wie sich das Icon verändert hat:

::

 <f:be.buttons.csh table="tt_content" field="header" styleAttributes="background-color: red;" />