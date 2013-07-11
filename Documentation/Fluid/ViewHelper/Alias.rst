.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../Includes.txt

f:alias
=======

Dieser ViewHelper erstellt Variablen, die Ihr im weiteren Verlauf wieder verwenden könnt. Ihr könnt den Variablen
entweder einen eigenen statischen Wert oder aber dynamische Werte aus Objekten und anderen ViewHelpern zuweisen.

Eigenschaften
-------------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Eigenschaft
   :Datatype,20:    Datentyp
   :Description,40: Beschreibung
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    map
   :Datatype:    Array
   :Description: Der Key gibt den Namen der neuen Variable an, während der Value den Inhalt wieder spiegelt.
   :Standard:
   :Mandatory:   Ja

Beispiel für statische Werte
----------------------------

::

 <f:alias map="{firstName: 'Stefan', lastName: 'Froemken'}">
   <p>Hello, my name is {firstName} {lastName}</p>
 </f:alias>

**Ausgabe**

::

 <p>Hello, my name is Stefan Froemken</p>

Beispiel für Ergebnisse aus ViewHelpern
---------------------------------------

::

 <f:alias map="{amount: '{addresses->f:count()}'}">
   <p>There are {amount} records in database</p>
 </f:alias>

**Ausgabe**

::

 <p>There are 23 records in database</p>

Beispiel für Werte aus Objekten
-------------------------------

::

 <f:alias map="{firstName: address.firstName, lastName: address.lastName}">
   <p>Hello, my name is {firstName} {lastName}</p>
 </f:alias>

**Ausgabe**

::

 <p>Hello, my name is Stefan Froemken</p>
