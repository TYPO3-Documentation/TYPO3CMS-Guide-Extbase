.. include:: ../../../Includes.txt

f:link.typolink
===========

Rendert einen Typolink - basierend auf dem Linkwizzard im Backend.

Properties
----------

.. include:: ../../UniversalTagAttributes.txt

Exclusive properties for the HTML-Element
#########################################

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

parameter
~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Auf welche Seiten-UID soll verlinkt werden. Es wird die Syntax aus dem Backend Linkwizzard (z.B. bei Verlinkungen per RTE) erwartet. Beispiel: 19 _blank

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    Yes

additionalParams
~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Fügt weitere Parameter der Zielseite an. Im Gegensatz zu arguments, können hiermit Variablen hinzugefügt werden die nicht mit dem Extensionnamen geprefixed werden.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

additionalAttributes
~~~~~~~~
:aspect:`Variable type`
    Array

:aspect:`Description`
	Fügt zusätzliche Parameter für das "ATag" ein. Das Array wird automatisch in die TypoScript Syntax Param1=Wert Param2=Wert umgewandelt

:aspect:`Default value`
    Leeres Array

:aspect:`Mandatory`
    No



Beispiel
--------

::

<f:link.typolink parameter="{link}">Linktext</f:link.typolink>

Dabei enthält {link} folgenden Wert "19 _blank - "testtitle with whitespace" &X=y" (wird z.B. im Backend im Linkwizzard verwendet)

Ausgabe:

a href="index.php?id=19&X=y" title="testtitle with whitespace" target="_blank">Linktext</a>

Volle Konfiguration
 <f:link.typolink parameter="{link}" target="_blank" class="ico-class" title="some title" additionalParams="&u=b" additionalAttributes="{type:'button'}">Linktext</f:link.typolink>

Ausgabe
a href="index.php?id=19&X=y&u=b" title="some title" target="_blank" class="ico-class" type="button">Linktext</a>
