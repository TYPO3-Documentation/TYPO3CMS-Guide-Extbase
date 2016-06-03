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

Properties
----------

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

{f:uri.external(uri: 'www.example.com')}
