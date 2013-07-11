.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../../Includes.txt

f:be.security.ifHasRole
=======================

Dieser ViewHelper prüft, ob ein im Backend angemeldeter User der im Parameter role angegebenen Benutzergruppe angehört.
Wie schon bei dem f:if-ViewHelper wird bei Gültigkeit der Inhalt zwischen den Tags oder, wenn vorhanden, der Inhalt aus
dem f:then-ViewHelper angezeigt. Falls gewünscht, kann auch der f:else-ViewHelper angegeben werden, der immer dann
angezeigt werden soll, falls der User nicht der angegebenen Benutzergruppe angehört.

Eigenschaften
-------------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Eigenschaft
   :Datatype,20:    Datentyp
   :Description,40: Beschreibung
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    role
   :Datatype:    String
   :Description: Entweder der Gruppenname (Groß- und Kleinschreibung beachten) oder die Gruppen-UID
   :Standard:    NULL
   :Mandatory:   Ja

Beispiel WENN->DANN->SONST
--------------------------

::

 <f:be.security.ifHasRole role="Administrator">
   <f:then>
     Sie dürfen diese Daten ändern
   </f:then>
   <f:else>
     Du nix Admin
   </f:else>
 </f:be.security.ifHasRole>

Beispiel, wenn angemeldet
-------------------------

::

 <f:be.security.ifHasRole role="2">
   Willkommen in der Gruppe der BE-Administratoren
 </f:be.security.ifHasRole>