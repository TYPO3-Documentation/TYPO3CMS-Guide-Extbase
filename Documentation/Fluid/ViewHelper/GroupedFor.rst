.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../Includes.txt

f:groupedFor
============

Ein sehr mächtiger ViewHelper im Bereich der Listengenerierung. Übergebt dem ViewHelper ein Array und ein
Gruppierungskriterium und Ihr erhaltet mit jedem Durchlauf bzw. mit jeder gefundenen Gruppe ein Array mit den
dazugehörigen Arrayelementen zurück.

Eigenschaften
-------------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Eigenschaft
   :Datatype,20:    Datentyp
   :Description,40: Beschreibung
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    each
   :Datatype:    Array
   :Description: Array oder Objekt, das durchlaufen werden soll
   :Standard:
   :Mandatory:   Ja

 - :Property:    as
   :Datatype:    String
   :Description: Ein Variablenname, der die gruppierten Datensätze enthält
   :Standard:
   :Mandatory:   Ja

 - :Property:    groupBy
   :Datatype:    String
   :Description: anhand welcher Eigenschaft soll das Array gruppiert werden
   :Standard:
   :Mandatory:   Ja

 - :Property:    groupKey
   :Datatype:    String
   :Description: Innerhalb der f:groupedBy-Tags kann mit dieser Variable auf den gruppierten Wert zugegriffen werden.
   :Standard:
   :Mandatory:   Ja

Beispiel
--------

::

 <f:alias map="{mitarbeiter: {0: {vorname: 'Stefan', stadt: 'Lindlar'},1: {vorname: 'Petra', stadt: 'Lindlar'},2: {vorname: 'Sascha', stadt: 'Remscheid'},3: {vorname: 'Patrick', stadt: 'Bonn'},4: {vorname: 'Sven', stadt: 'Gummersbach'},5: {vorname: 'Andrea', stadt: 'Wuppertal'}}}">
   <table cellpadding="5" cellspacing="0" border="2">
     <f:groupedFor each="{mitarbeiter}" as="kollegen" groupBy="stadt" groupKey="stadt">
       <tr>
         <th colspan="2">{stadt}</th> ist das hier der groupKey? 
       </tr>
       <f:for each="{kollegen}" as="kollege">
         <tr>
           <td style="color: {color}">{kollege.vorname}</td>
           <td style="color: {color}">{kollege.stadt}</td>
         </tr>
       </f:for>
     </f:groupedFor>
   </table>
 </f:alias>

Hier wieder das Beispiel mit den 6 Mitarbeitern. Wie Ihr sehen könnt gruppiert der f:groupedBy(müsste es nicht groupedFor lauten)-ViewHelper diese
Mitarbeiter anhand ihrer Städte (groupBy). Das geübte Auge sieht evtl. sofort, dass die ersten beiden Arrayeinträge
in Lindlar wohnen. Um innerhalb der f:groupedBy-Tags auf diesen Städtenamen zugreifen zu können, verwendet Ihr den
Parameter groupKey. Der Wert aus groupBy und groupKey müssen nicht übereinstimmen. Innerhalb von groupKey könntet Ihr
auch einfach city nehmen.

Über die Variable "as" könnt Ihr nun auf die Elemente der ersten gefundenen Gruppe zugreifen und mit f:for durchlaufen
lassen.
