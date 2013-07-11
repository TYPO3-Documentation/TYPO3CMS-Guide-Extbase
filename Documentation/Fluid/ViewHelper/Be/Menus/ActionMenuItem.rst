.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../../Includes.txt

f:be.menus.actionMenuItem
=========================

Mit diesem ViewHelper könnt Ihr einen Menüeintrag für Euer BE-Modul erstellen. Damit das funktioniert müssen sich
diese ViewHelper innerhalb des f:be.menus.actionMenu-ViewHelper befinden.

Eigenschaften
-------------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Eigenschaft
   :Datatype,20:    Datentyp
   :Description,40: Beschreibung
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    label
   :Datatype:    String
   :Description: Der anzuzeigende Name des Menüeintrages
   :Standard:    NULL
   :Mandatory:   Ja

 - :Property:    controller
   :Datatype:    String
   :Description: In welchem Controller liegt die aufzurufende Action
   :Standard:    NULL
   :Mandatory:   Ja

 - :Property:    action
   :Datatype:    String
   :Description: Welche Action soll nach Auswahl aufgerufen werden
   :Standard:    NULL
   :Mandatory:   Ja

 - :Property:    arguments
   :Datatype:    Array
   :Description: Welche Parameter sollen an die aufzurufende Action übergeben werden
   :Standard:    Leeres Array
   :Mandatory:   Ja

Beispiel
--------

Dieses Menü beinhaltet eine Selectbox mit 2 Menüeinträgen, die nach Auswahl die hinterlegte Action des hinterlegten
Controllers direkt aufrufen. Wie Ihr seht, könnt Ihr die Labels entweder direkt oder noch besser als Sprach-ViewHelper
realisieren.

::

 <f:be.menus.actionMenu>
   <f:be.menus.actionMenuItem label="Neu" controller="Fluid" action="new" />
   <f:be.menus.actionMenuItem label="{f:translate(key='list')}" controller="Fluid" action="list" />
 </f:be.menus.actionMenu>