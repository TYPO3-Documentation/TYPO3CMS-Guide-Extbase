.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../Includes.txt

f:count
=======

Dieser ViewHelper zählt die Elemente in dem angegebenen Objekt oder Array.

Eigenschaften
-------------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Eigenschaft
   :Datatype,20:    Datentyp
   :Description,40: Beschreibung
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    subject
   :Datatype:    Array
   :Description: Gebt hier das Array oder Objekt an, das gezählt werden soll. Wenn dieser Wert leergelassen wird,
                 dann versucht der ViewHelper, den Inhalt zwischen den Tags als Array zu interpretieren und zählt
                 diesen.
   :Standard:    NULL
   :Mandatory:   Nein

Beispiel: Array als renderChildren
----------------------------------

::

 <p>There are <f:count>{addresses}</f:count> records in our database</p>

**Ausgabe**

::

 <p>There are 23 records in our database</p>

Beispiel: Array über subject
----------------------------

::

 <p>There are <f:count subject="{addresses}" /> records in our database</p>

**Ausgabe**

::

 <p>There are 23 records in our database</p>

Beispiel: Inlinenotation
------------------------

::

 <p>There are {f:count(subject: addresses)} records in our database</p>

**Ausgabe**

::

 <p>There are 23 records in our database</p>

Beispiel: Die bessere Inlinenotation
------------------------------------

::

 <p>There are {addresses -> f:count()} records in our database</p>

**Ausgabe**

::

 <p>There are 23 records in our database</p>
