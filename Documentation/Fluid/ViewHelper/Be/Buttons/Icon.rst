.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../../Includes.txt

f:be.buttons.icon
=================

Mit diesem ViewHelper könnt Ihr kleine verlinkte Icons generieren lassen wie z.B. bearbeiten, löschen, neu und
viele mehr.

Eigenschaften
-------------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Eigenschaft
   :Datatype,20:    Datentyp
   :Description,40: Beschreibung
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    uri
   :Datatype:    String
   :Description: Die URL wohin die Reise führen soll. Kann auch mit einem der f:uri.*-ViewHelper kombiniert werden
   :Standard:    NULL
   :Mandatory:   Ja

 - :Property:    icon
   :Datatype:    String
   :Description: Der Name des Icons, dass verwendet werden soll
   :Standard:    actions-document-close
   :Mandatory:   Ja

 - :Property:    title
   :Datatype:    String
   :Description: Der hier eingegebene Wert wird als title-Attribut für den Link verwendet
   :Standard:    Leerer String
   :Mandatory:   Ja

Welche Werte für den icon-Parameter gültig sind könnt Ihr herausfinden, wenn Ihr irgend einen Schwachsinn als Wert
für den icon-Parameter angebt. Denn dann erhaltet Ihr folgende Antwort:

"blabla" ist kein gültiges Icon. Erlaubt sind: "add", "add_workspace", "button_down", "button_hide", "button_left", "button_unhide", "button_right", "button_up", "clear_cache", "clip_copy", "clip_cut", "clip_pasteafter", "closedok", "datepicker", "deletedok", "edit2", "helpbubble", "icon_fatalerror", "icon_note", "icon_ok", "icon_warning", "new_el", "options", "perm", "refresh_n", "saveandclosedok", "savedok", "savedoknew", "savedokshow", "viewdok", "zoom".

Beispiel
--------

::

 <f:be.buttons.icon uri="{f:uri.action(action:'new')}" icon="button_unhide" />

Zur Zeit der 4.6.7 klappen die Icons wohl noch nicht. Ich habe die verschiedensten Werte ausprobiert, aber ich erhielt
immer das rote Missingicon mit dem weißen Fragezeichen. Naja...es steht ja auch noch "experimental" in den englischen
Kommentaren diesen ViewHelpers. Bleiben wir gespannt.