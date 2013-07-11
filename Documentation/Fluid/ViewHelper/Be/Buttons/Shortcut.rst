.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../../Includes.txt

f:be.buttons.shortcut
=====================

Mit diesem ViewHelper könnt Ihr Euren BE-Modul-Besuchern anbieten Euer Modul als Favorit abzuspeichern

Eigenschaften
-------------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Eigenschaft
   :Datatype,20:    Datentyp
   :Description,40: Beschreibung
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    getVars
   :Datatype:    Array
   :Description: Wenn nichts angegeben wird, dann werden Seiten-UID, Modul und Modulargumente mit dem Favoriten zusammen abgespeichert.
   :Standard:    Leeres Array
   :Mandatory:   Ja

 - :Property:    setVars
   :Datatype:    Array
   :Description: Hier wird auf template::makeShortcutIcon() verwiesen. Wird aber für Extbase-Module normalerweise nicht benötigt.
   :Standard:    Leeres Array
   :Mandatory:   Ja

Beispiel
--------

::

 <f:be.buttons.shortcut />