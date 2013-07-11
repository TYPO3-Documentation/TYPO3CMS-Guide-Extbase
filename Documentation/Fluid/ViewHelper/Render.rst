.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../Includes.txt

f:render
========

Die Partials sind in Fluid wie die FCEs in TemplaVoila. Kurz: Wiederverwendbare Templates. Eine geniale Sache solange
Ihr diese ViewHelper in Maßen einsetzt, denn das Laden eines Partials dauert ca. 5 Millisekunden. Wenn Ihr also
irgendwann mal auf die Idee kommen solltet jede Zelle einer Tabelle mit Partials generieren zu wollen, dann kann das
Laden der Webseite bei 700 Tabellenzeilen und 15 Spalten schonmal etwas dauern: 700 Zeilen * 15 Spalten * 5
Millisekunden = 52500 Millisekunden. Plus die Zeit, die TYPO3 selbst noch braucht sind wir bei knapp einer Minute.

Eigenschaften
-------------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Eigenschaft
   :Datatype,20:    Datentyp
   :Description,40: Beschreibung
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    section
   :Datatype:    String
   :Description: Der Name einer Section, die gerendert werden soll.
   :Standard:    NULL
   :Mandatory:   Ja

 - :Property:    partial
   :Datatype:    String
   :Description: Pfad + Dateiname ohne .html-Endung ab dem Verzeichnis, das für Partials definiert wurde.
   :Standard:    NULL
   :Mandatory:   Ja

 - :Property:    arguments
   :Datatype:    Array
   :Description: Welche Variablen sollen in den Partial/das Layout übernommen werden.
   :Standard:    Leeres Array
   :Mandatory:   Ja

 - :Property:    optional
   :Datatype:    Boolean
   :Description: Normalerweise hagelt es Fehlermeldungen, wenn Sections nicht auffindbar sind. Setzt man diesen Parameter aber auf TRUE, dann wird eben nichts ausgegeben.
   :Standard:    FALSE
   :Mandatory:   Ja

Die Dateien für Partials liegen immer in fest vorgegebenen Verzeichnissen. Innerhalb von Extensions ist dies:
typo3conf/ext/[ExtensionKey]/Resources/Private/Partials/. Wenn Ihr allerdings mit FLUIDTEMPLATE arbeitet, dann gebt
Euren gewünschten Verzeichnispfad mit Hilfe der TS-Eigenschaft "partialRootPath" mit abschließendem / an.

Sections haben kein eigenes Verzeichnis, da diese immer innerhalb der aktuellen Templatedatei definiert werden
müssen. Außnahmen machen da die Layouts.

Beispiel für Partial
--------------------

In unserem Fluidtemplate:

::

 <f:alias map="{mitarbeiter: {0: {vorname: 'Stefan', stadt: 'Lindlar'},1: {vorname: 'Petra', stadt: 'Lindlar'},2: {vorname: 'Sascha', stadt: 'Remscheid'},3: {vorname: 'Patrick', stadt: 'Bonn'},4: {vorname: 'Sven', stadt: 'Gummersbach'},5: {vorname: 'Andrea', stadt: 'Wuppertal'}}}">
   <table cellpadding="5" cellspacing="0" border="2">
     <f:for each="{mitarbeiter}" as="kollege">
       <f:render partial="TableRow" arguments="{kollege: kollege}"/>
     </f:for>
   </table>
 </f:alias>

In der Partial Datei TableRow.html

::

 <tr>
   <td>{kollege.vorname}</td>
   <td>{kollege.stadt}</td>
 </tr>