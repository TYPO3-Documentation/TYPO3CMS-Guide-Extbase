.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:format.raw
============

f:format.rawworks since 1.4
Es gibt viele ViewHelper, die Inhalte vor der Ausgabe durch htmlspecialchars und anderen Methoden und Funktionen schleusen. Dies zu verhindern stellt auf jeden Fall ein Sicherheitsrisiko dar, kann aber mit diesem ViewHelper erreicht werden. Ich denke gerade im Bereich von Formulardaten kann dieser ViewHelper evtl. Verwendung finden.

Eigenschaften
-------------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Eigenschaft
   :Datatype,20:    Datentyp
   :Description,40: Beschreibung
   :Standard,10:    Default value
   :Mandatory,10:   Mandatory

 - :Property:    value
   :Datatype:    Mixed
   :Description: Der Text, der unangetastet/unverändert ausgegeben werden soll
   :Standard:    NULL
   :Mandatory:   Nein

Beispiel
--------

::

 <f:format.raw value="{formData.nachricht}" />