.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:format.bytes
==============

Dieser ViewHelper wandelt eine Bytes-Angabe (Integer) in ein lesbares Format um.

Eigenschaften
-------------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Eigenschaft
   :Datatype,20:    Datentyp
   :Description,40: Beschreibung
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    value
   :Datatype:    Integer
   :Description: Die Bytes als Integer, die konvertiert werden sollen
   :Standard:    NULL
   :Mandatory:   Nein

 - :Property:    decimals
   :Datatype:    Integer
   :Description: Die Anzahl Zahlen, die nach dem Dezimalpunkt noch angezeigt werden sollen
   :Standard:    0
   :Mandatory:   Nein

 - :Property:    decimalSeparator
   :Datatype:    String
   :Description: Das Zeichen, das als Dezimaltrenner verwendet werden soll
   :Standard:    .
   :Mandatory:   Nein

 - :Property:    thousandsSeparator
   :Datatype:    String
   :Description: Das Zeichen, das als Tausendertrenner verwendet werden soll
   :Standard:    ,
   :Mandatory:   Nein

Beispiel mit Text:
------------------

::

 <f:format.bytes>{fileSize}</f:format.bytes>

wird zu

::

 123 KB
