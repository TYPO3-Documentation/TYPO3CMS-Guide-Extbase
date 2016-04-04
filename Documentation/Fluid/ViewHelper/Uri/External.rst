.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:uri.external
==============

Dieser ViewHelper erstellt einen Link zu einer externen Seite.

.. tip::

   Wenn Ihr bei uri einen vollständigen Link angebt, also inkl http:// oder ftp://,
   dann braucht Ihr defaultScheme nicht zu setzen.

Eigenschaften
-------------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Eigenschaft
   :Datatype,20:    Datentyp
   :Description,40: Beschreibung
   :Standard,10:    Standard
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

{f:uri.external(uri: 'www.example.com')}
