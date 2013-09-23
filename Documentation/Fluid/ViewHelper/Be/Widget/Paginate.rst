.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../../Includes.txt

f:be.widget.paginate
====================

Dieser ViewHelper hilft Euch dabei eine große Anzahl an Daten auf mehrere Seiten mit Seitennavigation zu erstellen,
dabei könnt Ihr selbst fest legen wo sich die Navigation befinden soll und auch wie viele Datensätze pro Seite
angezeigt werden sollen.

Eigenschaften
-------------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Eigenschaft
   :Datatype,20:    Datentyp
   :Description,40: Beschreibung
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    objects
   :Datatype:    QueryResultInterface
   :Description: Hierbei handelt es sich nicht um die Ergebnisobjekte an sich, sondern um das Objekt aus dem
                 Repository, dass Daten enthält, die für das Zusammenstellen des SQL-Befehls benötigt werden. Das
                 SQL-Statementobjekt und SQL-Behle sind hier nicht erlaubt, da Extbase hier nicht weiß wie und wo es
                 den LIMIT-Befehl einbauen soll.
   :Standard:
   :Mandatory:   Ja

 - :Property:    as
   :Datatype:    String
   :Description: Wie soll die Variable heißen, in der die reduzierten Objekte zur Verfügung gestellt werden sollen?
   :Standard:
   :Mandatory:   Ja

 - :Property:    configuration
   :Datatype:    Array
   :Description: Konfiguration der Seitennavigation
   :Standard:    Siehe "Konfiguration der Seitennavigation"
   :Mandatory:   Nein

Konfiguration der Seitennavigation
----------------------------------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Eigenschaft
   :Datatype,20:    Datentyp
   :Description,40: Beschreibung
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    itemsPerPage
   :Datatype:    QueryResultInterface
   :Description: Wie viele Objekte sollen pro Seite angezeigt werden?
   :Standard:    10
   :Mandatory:   Nein

 - :Property:    insertAbove
   :Datatype:    Boolean
   :Description: Seitennavigator oberhalb anzeigen?
   :Standard:    FALSE
   :Mandatory:   Nein

 - :Property:    insertBelow
   :Datatype:    Boolean
   :Description: Seitennavigator unterhalb anzeigen?
   :Standard:    TRUE
   :Mandatory:   Nein

 - :Property:    recordsLabel
   :Datatype:    String
   :Description: Hier könnt Ihr einen eigenen Text einbinden, der den Schriftzug "Datensätze 1 - xy" überschreibt.
   :Standard:    Leerer String
   :Mandatory:   Nein
