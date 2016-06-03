.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:uri.resource
==============

Eigenschaften
-------------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Eigenschaft
   :Datatype,20:    Datentyp
   :Description,40: Beschreibung
   :Standard,10:    Default value
   :Mandatory,10:   Mandatory

 - :Property:    path
   :Datatype:    String
   :Description: Der Pfad inkl. Dateiname zu der Datei. Die Angabe erfolgt relativ zum Resource-Verzeichnis der
                 aktuellen Extension.
   :Standard:
   :Mandatory:   Ja

 - :Property:    extensionName
   :Datatype:    String
   :Description: Falls eine Datei einer anderen Extension benötigt wird,
                 kann hier der entsprechende Extensionname angegeben werden. Auch hier muss die Pfad relativ zum
                 Resourceverzeichnis angegeben werden.
   :Standard:    NULL
   :Mandatory:   Nein

 - :Property:    absolute
   :Datatype:    Boolean
   :Description: Wenn dieser Wert auf TRUE gesetzt wird, wird ein absoluter Pfad zurück geliefert.
   :Standard:    FALSE
   :Mandatory:   Nein


