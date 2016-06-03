.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:uri.resource
==============

Properties
----------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Property
   :Datatype,20:    Variable type
   :Description,40: Description
   :Standard,10:    Default value
   :Mandatory,10:   Mandatory

 - :Property:    path
   :Datatype:    String
   :Description: Der Pfad inkl. Dateiname zu der Datei. Die Angabe erfolgt relativ zum Resource-Verzeichnis der
                 aktuellen Extension.
   :Standard:
   :Mandatory:   Yes

 - :Property:    extensionName
   :Datatype:    String
   :Description: Falls eine Datei einer anderen Extension benötigt wird,
                 kann hier der entsprechende Extensionname angegeben werden. Auch hier muss die Pfad relativ zum
                 Resourceverzeichnis angegeben werden.
   :Standard:    NULL
   :Mandatory:   No

 - :Property:    absolute
   :Datatype:    Boolean
   :Description: Wenn dieser Wert auf TRUE gesetzt wird, wird ein absoluter Pfad zurück geliefert.
   :Standard:    FALSE
   :Mandatory:   No


