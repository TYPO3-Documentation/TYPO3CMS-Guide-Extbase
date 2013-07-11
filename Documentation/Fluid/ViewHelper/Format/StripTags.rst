.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:format.stripTags
==================

Dieser ViewHelper entfernt sämtliche HTML-Tags aus einem Text.

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
   :Datatype:    String
   :Description: Der Text aus dem die HTML-Tags entfernt werden sollen
   :Standard:    NULL
   :Mandatory:   Nein

Beispiel
--------

::

 <f:format.stripTags>Ein <strong>fetter</strong> Text mit einigen <span style="color: blue;">bunten</span> HTML-Tags.</f:format.stripTags>