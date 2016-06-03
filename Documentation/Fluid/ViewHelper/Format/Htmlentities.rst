.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:format.htmlentities
=====================

Mit diesem ViewHelper könnt Ihr die htmlentities Funktion von PHP auf einen Text anwenden.

Properties
----------

value
~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Der Text der dekodiert werden soll

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

keepQuotes
~~~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    Sollen einfache und doppelte Anführungsstriche auch dekodiert werden?

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No

encoding
~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Wir sind hier im Bereich TYPO3 und da sollte der Zeichensatz auf UTF-8 und nix anderes stehen. Sollte wiedererwartend ein anderer Zeichensatz gewünscht sein, kann dieser hier angegeben werden. Siehe auch Info auf php.net.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

doubleEncode
~~~~~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    Bei TRUE (Standard) wird alles kodiert. Bei FALSE, werden bereits kodierte Werte nicht erneut kodiert.

:aspect:`Default value`
    TRUE

:aspect:`Mandatory`
    No

Beispiel
--------

::

 <f:format.htmlentities>Müller & Breuer</f:format.htmlentities>

::

 M&uuml;ller &amp; Breuer