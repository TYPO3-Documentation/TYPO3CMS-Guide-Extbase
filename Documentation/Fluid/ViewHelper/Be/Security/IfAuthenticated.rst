.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../../Includes.txt

f:be.security.ifAuthenticated
=============================

Dieser ViewHelper prüft, ob ein Backenduser sich authentifiziert hat oder nicht. Je nach dem wird der Inhalt aus dem
f:then oder f:else-ViewHelper geladen.

Dieser ViewHelper wird überwiegend aus dem Frontend heraus benötigt. So könnt Ihr bestimmen, welche Inhalte nur
angezeigt werden, wenn ein User im BE angemeldet ist.Ich denke Frontend-Bearbeitung wäre eine gute Anlaufstelle für
diesen ViewHelper.

Eigenschaften
-------------

Dieser ViewHelper besitzt keine Eigenschaften

Beispiel WENN->DANN->SONST
--------------------------

::

 <f:be.security.ifAuthenticated>
   <f:then>
     Sie haben das Recht diesen Inhalt zu bearbeiten
   </f:then>
   <f:else>
     Sie muessen sich zuvor anmelden
   </f:else>
 </f:be.security.ifAuthenticated>

Beispiel, wenn angemeldet
-------------------------

::

 <f:be.security.ifAuthenticated>
   Hier kommt der Inhalt hin, den nur angemeldete Backend-Benutzer sehen.
 </f:be.security.ifAuthenticated>