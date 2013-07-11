.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../Includes.txt

f:for
=====

Der f:for-ViewHelper ist DER ViewHelper für die Listengeneration. Schaut Euch die Erläuterung in den Beispielen an.

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
   :Standard:    NULL
   :Mandatory:   Ja

 - :Property:    as
   :Datatype:    String
   :Description: Ein Variablenname, der Daten des aktuellen Durchlaufs enthält
   :Standard:    NULL
   :Mandatory:   Ja

 - :Property:    key
   :Datatype:    String
   :Description: Falls Ihr den Key/Schlüssel des aktuellen Durchlaufes benötigt, könnt Ihr hiermit den Namen einer weiteren Variable definieren
   :Standard:    Leerer String
   :Mandatory:   Ja

 - :Property:    reverse
   :Datatype:    Boolean
   :Description: Der Durchlauf des Arrays oder Objektes geschieht rückwärts
   :Standard:    FALSE
   :Mandatory:   Ja

 - :Property:    iteration
   :Datatype:    String
   :Description: Eine Arrayvariable, die Informationen darüber beinhaltet, ob man sich im ersten oder letzten Durchlauf befindet. Außerdem enthalten: index, cycle, total, isEven, isOdd
   :Standard:    NULL
   :Mandatory:   Ja

Einfaches Beispiel
------------------

::

 <f:alias map="{mitarbeiter: {0: {vorname: 'Stefan', stadt: 'Lindlar'},1: {vorname: 'Petra', stadt: 'Lindlar'},2: {vorname: 'Sascha', stadt: 'Remscheid'},3: {vorname: 'Patrick', stadt: 'Bonn'},4: {vorname: 'Sven', stadt: 'Gummersbach'},5: {vorname: 'Andrea', stadt: 'Wuppertal'}}}">
   <table cellpadding="5" cellspacing="0" border="2">
     <f:for each="{mitarbeiter}" as="kollege">
       <tr>
         <td>{kollege.vorname}</td>
         <td>{kollege.stadt}</td>
       </tr>
     </f:for>
   </table>
 </f:alias>

Ich weise der Variable mitarbeiter 6 Einträge zu, die dann eins nach dem Anderen von f:for durchlaufen werden. Mit
jedem Durchlauf wird eine weitere Tabellenzeile erstellt.

Beispiel für rückwärts
----------------------

::

 <f:alias map="{mitarbeiter: {0: {vorname: 'Stefan', stadt: 'Lindlar'},1: {vorname: 'Petra', stadt: 'Lindlar'},2: {vorname: 'Sascha', stadt: 'Remscheid'},3: {vorname: 'Patrick', stadt: 'Bonn'},4: {vorname: 'Sven', stadt: 'Gummersbach'},5: {vorname: 'Andrea', stadt: 'Wuppertal'}}}">
   <table cellpadding="5" cellspacing="0" border="2">
     <f:for each="{mitarbeiter}" as="kollege" reverse="1">
       <tr>
         <td>{kollege.vorname}</td>
         <td>{kollege.stadt}</td>
       </tr>
     </f:for>
   </table>
 </f:alias>

Zu Info: Man könnte bei dem Parameter reverse auch TRUE statt 1 verwenden.

Beispiel mit key/Schlüssel
--------------------------

::

 <f:alias map="{mitarbeiter: {0: {vorname: 'Stefan', stadt: 'Lindlar'},1: {vorname: 'Petra', stadt: 'Lindlar'},2: {vorname: 'Sascha', stadt: 'Remscheid'},3: {vorname: 'Patrick', stadt: 'Bonn'},4: {vorname: 'Sven', stadt: 'Gummersbach'},5: {vorname: 'Andrea', stadt: 'Wuppertal'}}}">
   <table cellpadding="5" cellspacing="0" border="2">
     <f:for each="{mitarbeiter}" as="kollege" reverse="1" key="eintrag">
       <tr>
         <th colspan="2">Eintrag: {eintrag}</th>
       </tr>
       <tr>
         <td>{kollege.vorname}</td>
         <td>{kollege.stadt}</td>
       </tr>
     </f:for>
   </table>
 </f:alias>

Beispiel mit Durchlaufinformationen
-----------------------------------

::

 <f:alias map="{mitarbeiter: {0: {vorname: 'Stefan', stadt: 'Lindlar'},1: {vorname: 'Petra', stadt: 'Lindlar'},2: {vorname: 'Sascha', stadt: 'Remscheid'},3: {vorname: 'Patrick', stadt: 'Bonn'},4: {vorname: 'Sven', stadt: 'Gummersbach'},5: {vorname: 'Andrea', stadt: 'Wuppertal'}}}">
   <table cellpadding="5" cellspacing="0" border="2">
     <f:for each="{mitarbeiter}" as="kollege" iteration="iterator">
       <f:if condition="{iterator.isFirst}">
         <tr>
           <th colspan="2">Los gehts</th>
         </tr>
       </f:if>
       <tr>
         <td>Durchlauf beginnend bei 0: {iterator.index}</td>
         <td>Durchlauf beginnend bei 1: {iterator.cycle}</td>
         <td{f:if(condition:iterator.isOdd, then: ' style="color: green;"')}>{kollege.vorname}</td>
         <td{f:if(condition:iterator.isEven, then: ' style="color: red;"')}>{kollege.stadt}</td>
       </tr>
       <f:if condition="{iterator.isLast}">
         <tr>
           <th colspan="2">Eintraege: {iterator.total}</th>
         </tr>
       </f:if>
     </f:for>
   </table>
 </f:alias>

iterator.cycle ist genau wie iterator.index einfach nur ein Zähler und hat nichts mit dem ViewHelper f:cycle zu tun.
Dieses Beispiel zeigt die Verwendung aller Durchlaufinformationen. Auch wenn Ihr den f:if-ViewHelper noch nicht
kennengelernt haben solltet, so sollte dieses Beispiel selbsterklärend sein. Probierts mal aus.