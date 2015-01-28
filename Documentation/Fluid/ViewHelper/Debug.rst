.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../Includes.txt

f:debug
=======

Falls eine eurer Variablen wieder erwarten nichts ausgeben sollte, könnt ihr mit Hilfe dieses ViewHelpers die
Inhalte eurer Variablen anzeigen lassen. In der Ausgabe seht ihr dann, ob euer gewünschter Wert überhaupt
gefüllt ist oder nicht.

Eigenschaften
-------------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Eigenschaft
   :Datatype,20:    Datentyp
   :Description,40: Beschreibung
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    title
   :Datatype:    String
   :Description: Mit dieser Eigenschaft könnt ihr der Debug-Ausgabe einen Titel geben,
                 um die Ausgabe zwischen eventuell weiteren vorhandenen Ausgaben schneller identifizieren zu können.
   :Standard:    NULL
   :Mandatory:   Nein

 - :Property:    maxDepth
   :Datatype:    Integer
   :Description: Zu Zeiten vor TYPO3 4.7 wurden Arrays und Objekte immer komplett dargestellt. Je nach Objektgröße
                 und Verschachtelung brach diese Darstellung jedoch ab. Mit dieser Eigenschaft werden die Arrays und
                 Objekte nur noch bis zu einer Tiefe von 8 Verschachtelungen dargestellt,
                 um das Problem zu umgehen. Je nach Rechnerleistung und Ausführungszeitraum
                 könnt ihr die Tiefe entsprechend anpassen.
   :Standard:    8
   :Mandatory:   Nein

 - :Property:    plainText
   :Datatype:    Boolean
   :Description: Für den CLI-Modus könnt ihr hier die Debug-Ausgabe als reinen Text ausgeben lassen.
   :Standard:    FALSE
   :Mandatory:   Nein

 - :Property:    ansiColors
   :Datatype:    Boolean
   :Description: Bestimmte Shells unterstützen die farbliche Hervorhebung von Wörtern in einem Text. Nach Aktivierung
                 werden der Debug-Ausgabe zusätzliche Steuerzeichen hinzugefügt,
                 damit die Shell die Hervorhebung vornehmen kann. Dieses funktioniert nur
                 zusammen mit 'plainText'.
   :Standard:    FALSE
   :Mandatory:   Nein

 - :Property:    inline
   :Datatype:    Boolean
   :Description: Normalerweise erscheint die Debug-Ausgabe oberhalb der Webseite. Mit 'inline'
                 erscheint die Ausgabe genau an der Stelle des f:debug-ViewHelpers.
   :Standard:    FALSE
   :Mandatory:   Nein

 - :Property:    blacklistedClassNames
   :Datatype:    Array
   :Description: Hiermit können ausgewählte Klassen hervorgehoben werden. Funktioniert im Augenblick (?)
                 nicht mit Namespaces.
   :Standard:    NULL
   :Mandatory:   Nein

 - :Property:    blacklistedPropertyNames
   :Datatype:    Array
   :Description: Hiermit können ausgewählte Objekteigenschaften hervorgehoben werden. Funktioniert
                 im Augenblick (?) nicht mit Namespaces.
   :Standard:    NULL
   :Mandatory:   Nein

.. tip::

   Das Debuggen von Aggregate-Root-Objekten führte in früheren Versionen immer wieder zu Problemen.
   Viele Objekte sind sehr tief verschachtelt oder sind rekursiv aufrufbar. Dies führte in vielen 
   Fällen zur Überschreitung der in php.ini definierten memory_limit oder auch zur Überschreitung
   der max_execution_time. In solchen Fällen hat es geholfen nur einen Teil des Objektes zu 
   debuggen oder das komplette Objekt in ein Array zu konvertieren.

Beispiele
---------

::

   <f:debug title="Results of customers">{customers}</f:debug>

::

   {customers -> f:debug(title="Results of customers")}

::

   {f:debug(subject: customers, title: "Results od customers")}
