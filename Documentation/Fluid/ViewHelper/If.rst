.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../Includes.txt

f:if
====

Auch wenn dieser ViewHelper in seiner Ausführung noch etwas eingeschränkt ist gehört er trotzdem zu den ViewHelpern,
die Ihr auswendig kennen solltet. Wer sich mal den fed:if-ViewHelper aus der fed-Extension angeschaut hat, weiß wovon
wir reden.

Eigenschaften
-------------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Eigenschaft
   :Datatype,20:    Datentyp
   :Description,40: Beschreibung
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    condition
   :Datatype:    Boolean
   :Description: Hier kommt die Vergleichtsabfrage rein (Siehe Beispiele)
   :Standard:    NULL
   :Mandatory:   Ja

Folgende Vergleiche sind erlaubt: ==, !=, <, <=, >, >= und %

Vergleicht werden können nur Variablen folgenden Typs: Zahlen, Objekteigenschaften, Arrays, Strings (seit v6.2) und
Ergebnisse aus ViewHelpern

Einfache Beispiele
------------------

::

 <f:alias map="{wert1: 1, wert5: 5}">
   <f:if condition="{wert1}==1">
     <p>Der Wert ist 1</p>
   </f:if>
   <f:if condition="{wert5}==5">
     <f:then>
       <p>Der Wert ist 5</p>
     </f:then>
     <f:else>
       <p>Der Wert ist NICHT 5</p>
     </f:else>
   </f:if>
   <f:if condition="{wert5} % 2">
     <f:then>
       <p>Die Berechnung liefert einen Restwert von 1.</p>
     </f:then>
     <f:else>
       <p>Es konnte kein Restwert ermittelt werden</p>
     </f:else>
   </f:if>
   <f:if condition="{wert1}!={wert5}">
     <p>wert1 ist NICHT gleich wert5</p>
   </f:if>
   <f:if condition="{wert1}<{wert5}">
     <p>wert1 ist kleiner als wert5</p>
   </f:if>
   <f:if condition="{0:wert1,1:wert5}=={0:1,1:5}">
     <p>Der erste Array ist gleich mit allen Werten aus dem zweiten Zahlenarray</p>
   </f:if>
 </f:alias>
 <f:alias map="{elemente: {0: wert1, 1: wert2}}">
   <f:if condition="{elemente -> f:count()}==2">
     <p>Vergleich mit ViewHelpern: Das Elementearray beinhaltet 2 Elemente</p>
   </f:if>
 </f:alias>
 <f:alias map="{wert1: 'hallo'}">
   <f:if condition="{wert1} == 'hallo'">
     <p>Stringvergleiche klappen seit v6.2</p>
   </f:if>
   <f:if condition="{0: wert1} == {0: 'hallo'}">
     <p>Stringvergleiche vor v6.2 nur als Array</p>
   </f:if>

 </f:alias>

Wenn kein f:then oder f:else-ViewHelper gefunden wurde, dann wird der Inhalt zwischen den f:if-ViewHelpern immer nur
dann ausgegeben, wenn die Bedingung wahr ist. Wenn komplette WENN->DANN-SONST-Konstrukte erzeugt werden müssen, dann
müssen auch immer die f:then und f:else-ViewHelper verwendet werden.
