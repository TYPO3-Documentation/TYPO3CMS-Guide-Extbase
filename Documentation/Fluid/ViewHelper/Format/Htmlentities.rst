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

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Property
   :Datatype,20:    Variable type
   :Description,40: Description
   :Standard,10:    Default value
   :Mandatory,10:   Mandatory

 - :Property:    value
   :Datatype:    String
   :Description: Der Text der dekodiert werden soll
   :Standard:    NULL
   :Mandatory:   No

 - :Property:    keepQuotes
   :Datatype:    Boolean
   :Description: Sollen einfache und doppelte Anführungsstriche auch dekodiert werden?
   :Standard:    FALSE
   :Mandatory:   No

 - :Property:    encoding
   :Datatype:    String
   :Description: Wir sind hier im Bereich TYPO3 und da sollte der Zeichensatz auf UTF-8 und nix anderes stehen. Sollte wiedererwartend ein anderer Zeichensatz gewünscht sein, kann dieser hier angegeben werden. Siehe auch Info auf php.net.
   :Standard:    NULL
   :Mandatory:   No

 - :Property:    doubleEncode
   :Datatype:    Boolean
   :Description: Bei TRUE (Standard) wird alles kodiert. Bei FALSE, werden bereits kodierte Werte nicht erneut kodiert.
   :Standard:    TRUE
   :Mandatory:   No

Beispiel
--------

::

 <f:format.htmlentities>Müller & Breuer</f:format.htmlentities>

::

 M&uuml;ller &amp; Breuer