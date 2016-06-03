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

Eigenschaften
-------------

.. include:: ../../UniversalTagAttributes.txt

Eigenschaften speziell für das HTML-Element
###########################################

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Eigenschaft
   :Datatype,20:    Datentyp
   :Description,40: Beschreibung
   :Standard,10:    Default value
   :Mandatory,10:   Mandatory

 - :Property:    name
   :Datatype:    String
   :Description: Der name des Links
   :Standard:    NULL
   :Mandatory:   Nein

 - :Property:    rel
   :Datatype:    String
   :Description: Gibt die Beziehung zwischen dem aktuellen Dokument und dem verknüpften Dokument an
   :Standard:    NULL
   :Mandatory:   Nein

 - :Property:    rev
   :Datatype:    String
   :Description: Gibt die Beziehung zwischen dem verknüpften Dokument und dem aktuellen Dokument an
   :Standard:    NULL
   :Mandatory:   Nein

 - :Property:    target
   :Datatype:    String
   :Description: In welchem Fenster soll der Link geöffnet werden?
   :Standard:    NULL
   :Mandatory:   Nein

Eigenschaften speziell für diesen ViewHelper
############################################

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Eigenschaft
   :Datatype,20:    Datentyp
   :Description,40: Beschreibung
   :Standard,10:    Default value
   :Mandatory,10:   Mandatory

 - :Property:    uri
   :Datatype:    String
   :Description: Die URL zu der externen Zielseite
   :Standard:
   :Mandatory:   Ja

 - :Property:    defaultScheme
   :Datatype:    String
   :Description: Hier sind alle gültigen Schemas für Links erlaubt wie z.B. ftp oder https
   :Standard:    http
   :Mandatory:   Nein

Beispiel
--------

::

 <f:link.external uri="www.example.com">Externer Link zu meiner Seite</f:link.external>
