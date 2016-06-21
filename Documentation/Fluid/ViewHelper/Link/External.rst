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

name
~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Der name des Links

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

rel
~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Gibt die Beziehung zwischen dem aktuellen Dokument und dem verknüpften Dokument an

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

rev
~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Gibt die Beziehung zwischen dem verknüpften Dokument und dem aktuellen Dokument an

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

target
~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    In welchem Fenster soll der Link geöffnet werden?

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

Exclusive properties of this ViewHelper
#######################################

uri
~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Die URL zu der externen Zielseite

:aspect:`Default value`

:aspect:`Mandatory`
    Yes

defaultScheme
~~~~~~~~~~~~~
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

::

 <f:link.external uri="www.example.com">Externer Link zu meiner Seite</f:link.external>
