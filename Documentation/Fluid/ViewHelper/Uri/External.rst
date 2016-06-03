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

 - :Property:    uri
:aspect:`Variable type`
    String

:aspect:`Description`
    Die URL zu der externen Zielseite
   :Standard:

:aspect:`Mandatory`
    Yes

 - :Property:    defaultScheme
:aspect:`Variable type`
    String

:aspect:`Description`
    Hier sind alle gültigen Schemas für Links erlaubt wie z.B. ftp oder https

:aspect:`Default value`
    http

:aspect:`Mandatory`
    No

Beispiel
--------

{f:uri.external(uri: 'www.example.com')}
