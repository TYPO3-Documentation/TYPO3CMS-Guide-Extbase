.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:format.number
===============

Mit diesem ViewHelper könnt Ihr Zahlen formatieren. Er arbeitet ähnlich dem f:format.currency-ViewHelper

Eigenschaften
-------------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Eigenschaft
   :Datatype,20:    Datentyp
   :Description,40: Beschreibung
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    decimals
   :Datatype:    Integer
   :Description: Wie viele Nachkommastellen dürfen angezeigt werden.
   :Standard:    2
   :Mandatory:   Nein

 - :Property:    decimalSeparator
   :Datatype:    String
   :Description: Welcher Zeichen soll für die Trennung von Euro und Cent verwendet werden. Dezimaltrenner.
   :Standard:    .
   :Mandatory:   Nein

 - :Property:    thousandsSeparator
   :Datatype:    String
   :Description: Welches Zeichen soll als Tausendertrennzeichen verwendet werden.
   :Standard:    ,
   :Mandatory:   Nein

Beispiel
--------

::

 <f:format.number decimals="3" decimalSeparator="." thousandsSeparator=",">1122334455.667788</f:format.number>

ergibt: 1,122,334,455.668. Wie Ihr seht wird sogar automatisch aufgerundet.
