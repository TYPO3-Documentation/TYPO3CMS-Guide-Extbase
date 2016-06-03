.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:link.external
===============

Dieser ViewHelper erstellt einen Link zu einer externen Seite.

.. tip::

   Wenn Ihr bei uri einen vollständigen Link angebt, also inkl. http:// oder ftp://,
   dann braucht Ihr defaultScheme nicht zu setzen.

Properties
----------

.. include:: ../../UniversalTagAttributes.txt

Exclusive properties for the HTML-Element
#########################################

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Property
   :Datatype,20:    Variable type
   :Description,40: Description
   :Standard,10:    Default value
   :Mandatory,10:   Mandatory

 - :Property:    name
   :Datatype:    String
   :Description: Der name des Links
   :Standard:    NULL
   :Mandatory:   No

 - :Property:    rel
   :Datatype:    String
   :Description: Gibt die Beziehung zwischen dem aktuellen Dokument und dem verknüpften Dokument an
   :Standard:    NULL
   :Mandatory:   No

 - :Property:    rev
   :Datatype:    String
   :Description: Gibt die Beziehung zwischen dem verknüpften Dokument und dem aktuellen Dokument an
   :Standard:    NULL
   :Mandatory:   No

 - :Property:    target
   :Datatype:    String
   :Description: In welchem Fenster soll der Link geöffnet werden?
   :Standard:    NULL
   :Mandatory:   No

Exclusive properties of this ViewHelper
#######################################

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Property
   :Datatype,20:    Variable type
   :Description,40: Description
   :Standard,10:    Default value
   :Mandatory,10:   Mandatory

 - :Property:    uri
   :Datatype:    String
   :Description: Die URL zu der externen Zielseite
   :Standard:
   :Mandatory:   Yes

 - :Property:    defaultScheme
   :Datatype:    String
   :Description: Hier sind alle gültigen Schemas für Links erlaubt wie z.B. ftp oder https
   :Standard:    http
   :Mandatory:   No

Beispiel
--------

::

 <f:link.external uri="www.example.com">Externer Link zu meiner Seite</f:link.external>
