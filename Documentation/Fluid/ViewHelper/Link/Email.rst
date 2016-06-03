.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:link.email
============

Mit diesem ViewHelper erstellt Ihr einen Link auf eine E-Mail-Adresse. Falls Ihr mit TypoScript im Bereich "config"
Angaben zum Verschlüsseln der E-Mail-Adresse gemacht habt, so werden diese Einstellungen auch hier angewendet.

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

email
~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Die zu verlinkende E-Mail-Adresse

:aspect:`Default value`

:aspect:`Mandatory`
    Yes

Beispiel
--------

::

 <f:link.email email="meine@mailadresse.tld" />
