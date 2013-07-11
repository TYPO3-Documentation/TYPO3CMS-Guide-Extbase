.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../../Includes.txt

f:be.menus.actionMenuView
=========================

Dieser ViewHelper erstellt eine Selectbox. Mit Hilfe der actionMenuItem-ViewHelper könnt Ihr diese Selectbox mit
Optionen auffüllen, die dann nach Auswahl auf die gewünschte Action zugreifen.

Eigenschaften
-------------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Eigenschaft
   :Datatype,20:    Datentyp
   :Description,40: Beschreibung
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    defaultController
   :Datatype:    String
   :Description: Gebt hier den Controllernamen ein auf den zurückgegriffen werden soll, falls im ActionMenuItem-ViewHelper kein Controller angegeben worden ist. Wenn ich mir den ViewHelper im Quellcode anschaue, würde ich diesen Parameter besser nicht verwenden. Erstens: Weil er im Quelltext überhaupt nicht weiter verwendet wird und Zweitens: Weil der Controller in den ActionMenuItems eh eine Pflichtangabe ist.
   :Standard:    NULL
   :Mandatory:   Ja

Beispiele findet Ihr bei den ActionMenuItem-ViewHelpern