.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:format.html
=============

Wenn Ihr ein Modell für die Tabelle tt_content erstellt habt, dann erhaltet Ihr im Frontend die nackten Daten, wie sie
aus der Datenbank kommen. Damit die Daten wieder so aussehen, wie wenn Ihr sie mit styles.content.get ausgebt, hilft
Euch dieser ViewHelper weiter. Dieser schnappt sich das Durcheinander und schleift es einmal komplett durch den
TS-Objektpfad lib.parseFunc_RTE. Danach sollten Eure Daten wieder wie frisch aufbereitet aussehen.

Eigenschaften
-------------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Eigenschaft
   :Datatype,20:    Datentyp
   :Description,40: Beschreibung
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    parseFuncTSPath
   :Datatype:    String
   :Description: Formatiere einen Text anhand der TS-Konfiguration, die sich hinter dem angegebenen TS-Objektpfad befindet
   :Standard:    lib.parseFunc_RTE
   :Mandatory:   Nein

Beispiel
--------

::

 <f:format.html>{content.bodytext}</f:format.html>

Beispiel/Trick mit abgeschalteten htmlspecialchars
--------------------------------------------------

::

 <f:format.html parseFuncTSPath="lib.parseFunc">{variable}</f:format.html>