.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:format.htmlspecialchars
=========================

Wenn Ihr mit Userdaten (Formulardaten) arbeitet, dann sollte dieser Inhalt zuallererst durch diesen ViewHelper.
Denn dieser wandelt alle spitzen Klammern von HTML-Tags in ein nicht mehr interprtierbares Format um. Die HTML-Tags
können also keinen Schaden mehr verursachen und werden iom FE angezeigt statt verarbeitet.

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
   :Datatype:    String
   :Description: Der Text der formatiert werden soll
   :Standard:    NULL
   :Mandatory:   Nein

 - :Property:    keepQuotes
   :Datatype:    Boolean
   :Description: Sollen einfache und doppelte Anführungszeichen auch formatiert werden
   :Standard:    FALSE
   :Mandatory:   Nein

 - :Property:    encoding
   :Datatype:    String
   :Description:
   :Standard:    NULL
   :Mandatory:   Nein

 - :Property:    doubleEncode
   :Datatype:    Boolean
   :Description: Mit jedem Aufruf diesen ViewHelpers wird ein bereits htmlspecialchared Text immer und immer wieder gehtmlspecialchared. Auf & wird dann &amp; dann &amp;amp;, dann &amp;amp;amp; und so weiter. Um das zu verhindert, kann dieser Parameter auf FALSE gesetzt werden.
   :Standard:    TRUE
   :Mandatory:   Nein

Beispiel
--------

::

 <f:format.htmlspecialchars><p><strong>fetter</strong> Text</p></f:format.htmlspecialchars>