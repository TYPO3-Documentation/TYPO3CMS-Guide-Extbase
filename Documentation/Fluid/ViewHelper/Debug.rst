.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../Includes.txt

f:debug
=======

Falls eine Eurer Variablen wieder erwartend nichts ausgeben sollte, könnt Ihr mit Hilfe diesen ViewHelpers die
Inhalte Eurer Variablen anzeigen lassen. In der Ausgabe seht Ihr dann, ob Euer gewünschter Wert überhaupt
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
   :Description: Mit dieser Eigenschaft könnt Ihr der Degugausgabe einen Titel geben,
                 um die Ausgabe zwischen evtl. weiteren vorhandenen Ausgaben schneller identifizieren zu können.
   :Standard:    NULL
   :Mandatory:   Nein

 - :Property:    maxDepth
   :Datatype:    Integer
   :Description: Zu Zeiten vor TYPO3 4.7 wurden Arrays und Objekte immer komplett dargestellt. Je nach Objektgröße
                 und Verschachtelung brach diese Darstellung jedoch ab. Mit dieser Eigenschaft werden die Arrays und
                 Objekte nur noch bis zu einer Tiefe von 8 Verschachtelungen dargestellt,
                 um dieses Problem zu umgehen. Je nach Rechnerleistung und Ausführungszeitraum,
                 könnt Ihr die Tiefe entsprechend anpassen.
   :Standard:    8
   :Mandatory:   Nein

 - :Property:    plainText
   :Datatype:    Boolean
   :Description: Für den CLI-Modus könnt Ihr hier die Debugausgabe als reinen Text ausgeben lassen.
   :Standard:    FALSE
   :Mandatory:   Nein

 - :Property:    ansiColors
   :Datatype:    Boolean
   :Description: Bestimmte Shells unterstützen die farbliche Hervorhebung von Wörtern in einem Text. Nach Aktivierung
                 werden der Debugausgabe ein paar zusätzliche Steuerzeichen hinzugefügt,
                 damit die Shell die Hervorhebung vornehmen kann. Diese Eigenschaft klappt nur,
                 wenn plainText aktiviert wurde.
   :Standard:    FALSE
   :Mandatory:   Nein

 - :Property:    inline
   :Datatype:    Boolean
   :Description: Normalerweise wird die Debugausgabe oberhalb der Webseite ausgegeben. Nach Aktivierung dieser Option
                 findet die Ausgabe genau dort statt, wo Ihr den f:debug-ViewHelper platziert habt.
   :Standard:    FALSE
   :Mandatory:   Nein

 - :Property:    blacklistedClassNames
   :Datatype:    Array
   :Description: Mit dieser Eigenschaft können ganz bestimmte Klassen hervorgehoben werden. Zur Zeit klappt diese
                 Eigenschaft nicht in Zusammenhang mit Namespaces
   :Standard:    NULL
   :Mandatory:   Nein

 - :Property:    blacklistedPropertyNames
   :Datatype:    Array
   :Description: Mit dieser Eigenschaft können ganz bestimmte Objekteigenschaften hervorgehoben werden. Zur
                 Zeit klappt diese Eigenschaft nicht in Zusammenhang mit Namespaces
   :Standard:    NULL
   :Mandatory:   Nein

.. tip::

   Das Debuggen von Aggregate-Root-Objekten führte in früheren Versionen immer wieder zu Problemen. Viele Objekte sind
   sehr tief verschachtelt oder sind rekursiv aufrufbar. Dies führte in vielen Fällen zur Überschreitung der in php.ini
   definierten memory_limit oder auch zur Überschreitung der max_execution_time. In solchen Fällen hat es geholfen nur
   einen Teil des Objektes zu debuggen oder das komplette Objekt in ein Array zu konvertieren.

Beispiel
--------

::

 <f:debug title="Results of customers">{customers}</f:debug>

::

 {customers -> f:debug(title="Results of customers")}

::

 {f:debug(subject: customers, title: "Results od customers")}
