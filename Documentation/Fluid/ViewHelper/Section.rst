.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../Includes.txt

f:section
=========

Sections sind ähnlich Partials mit dem Unterschied, dass Partials in Dateien ausgelagert werden und Sections
innerhalb des Templates definiert werden müssen.

Eigenschaften
-------------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Eigenschaft
   :Datatype,20:    Datentyp
   :Description,40: Beschreibung
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    name
   :Datatype:    String
   :Description: Ein Name unter dem man den Inhalt zwischen den Tags wieder auffinden kann
   :Standard:    NULL
   :Mandatory:   Ja

Beispiel
--------

::

 <f:section name="TableRow">
   <tr>
     <td>{kollege.vorname}</td>
     <td>{kollege.stadt}</td>
   </tr>
 </f:section>
 <f:alias map="{mitarbeiter: {0: {vorname: 'Stefan', stadt: 'Lindlar'},1: {vorname: 'Petra', stadt: 'Lindlar'},2: {vorname: 'Sascha', stadt: 'Remscheid'},3: {vorname: 'Patrick', stadt: 'Bonn'},4: {vorname: 'Sven', stadt: 'Gummersbach'},5: {vorname: 'Andrea', stadt: 'Wuppertal'}}}">
   <table cellpadding="5" cellspacing="0" border="2">
     <f:for each="{mitarbeiter}" as="kollege">
       <f:render section="TableRow" arguments="{kollege: kollege}"/>
     </f:for>
   </table>
 </f:alias>

Wie Ihr seht wird hier erst das HTML für eine Tabellenzeile definiert und der Section der Name "TableRow" gegeben.
Später dann in der Schleife könnt Ihr mit Hilfe des f:render-ViewHelpers diese Section wieder aufrufen.