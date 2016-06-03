.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:uri.resource
==============

Properties
----------

path
~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Der Pfad inkl. Dateiname zu der Datei. Die Angabe erfolgt relativ zum Resource-Verzeichnis der
                 aktuellen Extension.

:aspect:`Default value`

:aspect:`Mandatory`
    Yes

extensionName
~~~~~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Falls eine Datei einer anderen Extension benötigt wird,
                 kann hier der entsprechende Extensionname angegeben werden. Auch hier muss die Pfad relativ zum
                 Resourceverzeichnis angegeben werden.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

absolute
~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    Wenn dieser Wert auf TRUE gesetzt wird, wird ein absoluter Pfad zurück geliefert.

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No


