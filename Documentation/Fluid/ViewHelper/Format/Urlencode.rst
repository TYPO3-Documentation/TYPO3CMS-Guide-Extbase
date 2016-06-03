.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:format.urlencode
==================

In Texten und Firmennamen kommen immer wieder Sonderzeichen wie @ & oder % vor. Diese Zeichen sind nicht URL-sicher
und sollten vor der Übermittlung durch diesen ViewHelper geschleust werden.

Eigenschaften
-------------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Property
   :Datatype,20:    Variable type
   :Description,40: Description
   :Standard,10:    Default value
   :Mandatory,10:   Mandatory

 - :Property:    value
   :Datatype:    String
   :Description: Der Text, der für die Übergabe per Link vorbereitet werden soll
   :Standard:    NULL
   :Mandatory:   No

Beispiel
--------

::

 <f:format.urlencode>Text mit ein npaar Sonderzeichen, die für die URL entsprechend maskiert werden müssen: @+%/</f:format.urlencode>

Ergebnis:

::

 Text%20mit%20ein%20npaar%20Sonderzeichen%2C%20die%20f%C3%BCr%20die%20URL%20entsprechend%20maskiert%20werden%20m%C3%BCssen%3A%20%40%2B%25%2F
