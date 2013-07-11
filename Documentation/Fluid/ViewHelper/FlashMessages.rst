.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../Includes.txt

f:flashMessages
===============

Dieser ViewHelper macht nur im Bereich selbstprogrammierter Extensions Sinn. Denn nur hier können Fehler auftauchen,
die dem Webseitenbesucher mitgeteilt werden müssen. Hat der User z.B. vergessen bei einem Loginformular seinen
Usernamen anzugeben und die dafür zuständige Action/Methode wurde so programmiert, dass der Username eine
Pflichtangabe ist, dann wird dies dem Validator gemeldet, der daraufhin eine errorAction-Methode aufruft, die dann
wiederum Fehlermeldungen zuerst sammelt und dann als "Bündel" an der Stelle ausgibt, an der Ihr diesen ViewHelper-Tag
platziert habt.

Eigenschaften
-------------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Eigenschaft
   :Datatype,20:    Datentyp
   :Description,40: Beschreibung
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    renderMode
   :Datatype:    String
   :Description: Sollen die Fehlermeldungen als Liste (ul) oder als Container (div) gerendert werden
   :Standard:    NULL
   :Mandatory:   Ja

Beispiel Standard
-----------------

::

 <f:flashMessages />

Beispiel als Container
----------------------

::

 <f:flashMessages renderMode="div" />