.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../Includes.txt

f:cObject
=========

Dieser ViewHelper stellt eine Verbindung zu TypoScript her. Übergebt einen TypoScript Objekt Pfad (lib.*) und lasst
TypoScript die Arbeit machen.

Eigenschaften
-------------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Eigenschaft
   :Datatype,20:    Datentyp
   :Description,40: Beschreibung
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    typoscriptObjectPath
   :Datatype:    String
   :Description: Gebt hier den TypoScript Objektpfad an
   :Standard:
   :Mandatory:   Ja

 - :Property:    data
   :Datatype:    Mixed
   :Description: Gebt hier den TypoScript Objektpfad an
   :Standard:    NULL
   :Mandatory:   Nein

 - :Property:    currentValueKey
   :Datatype:    String
   :Description: Gebt hier den TypoScript Objektpfad an
   :Standard:    NULL
   :Mandatory:   Nein


Einfaches Beispiel
------------------

**TypoScript**

::

 lib.fluidText = TEXT
 lib.fluidText {
   value = Text from TypoScript
 }

**Fluid-Template**

::

 <p><f:cObject typoscriptObjectPath="lib.fluidText" /></p>

**Ausgabe**

::

 <p>Text from TypoScript</p>

Beispiel für lokalisierte Datumswerte
-------------------------------------

Der f:format.date ViewHelper arbeitet mit der PHP Funktion date() und kann somit nur englische Monatsnamen ausgeben.
Besser wäre da schon die Verwendung von strftime. TypoScript bietet strftime formatierte Datumswerte an. Hier ein
Beispiel unter Verwendung von current:

**TypoScript**

::

 lib.formattedDate = TEXT
 lib.formattedDate {
   current = 1
   strftime = %d. %B %Y
 }

**Fluid-Template**

::

 <p><f:cObject typoscriptObjectPath="lib.formattedDate">{address.dayOfBirth}</f:cObject></p>

**Ausgabe**

::

 <p>17. Januar 2013</p>

Beispiel mit einem Array/Objekt
-------------------------------

**TypoScript**

::

 lib.address = COA
 lib.address {
   10 = TEXT
   10.value.current = 1
   10.value.wrap = <p>First name: |</p>
   20 = TEXT
   20.value.dataWrap = <p>Full name: {field: firstName} {field: lastName}
 }

**Fluid-Template**

::

 <f:cObject typoscriptObjectPath="lib.address" data="{address}" currentValueKey="firstName" />

**Ausgabe**

::

 <p>First name: Stefan</p><p>Full name: Stefan Froemken</p>

.. tip::

   Wie oben bereits erklärt, könnt Ihr mit currentValueKey angeben, welcher Wert aus dem Array oder Objekt
   über current=1 zur Verfügung gestellt werden soll.
   Auf die anderen Werte eines Arrays oder Objektes könnt Ihr dann wie hier im Beispiel mit "field" zugreifen.