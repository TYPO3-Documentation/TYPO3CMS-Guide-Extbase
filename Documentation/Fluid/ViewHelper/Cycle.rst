.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../Includes.txt

f:cycle
=======

Mit diesem ViewHelper könnt Ihr die Ausgaben des f:for-ViewHelpers aufpeppen und zum Beispiel odd/even-Tabellen
erstellen. Zwar könnt Ihr mit dem f:for ViewHelper auf das erste und letzte Element der Schleife zugreifen, aber um
jeder zweiten oder dritten Zeile ein anderes Aussehen zu verpassen, benötiget Ihr f:cycle.

Eigenschaften
-------------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Eigenschaft
   :Datatype,20:    Datentyp
   :Description,40: Beschreibung
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    values
   :Datatype:    Array
   :Description: Eingabe als Arraynotation. Erläuterung im Beispiel
   :Standard:
   :Mandatory:   Ja

 - :Property:    as
   :Datatype:    String
   :Description: Gebt hier den Namen der neuen Variable für das Template an
   :Standard:
   :Mandatory:   Ja

Beispiel
--------

::

 <table cellpadding="5" cellspacing="0" border="2">
   <f:for each="{addresses}" as="address">
     <f:cycle values="{0: 'green', 1: 'red', 2: 'blue'}" as="color">
       <tr>
         <td style="color: {color}">{address.firstName}</td>
         <td style="color: {color}">{address.lastName}</td>
       </tr>
     </f:cycle>
   </f:for>
 </table>

**Ausgabe**

::

 <table cellpadding="5" cellspacing="0" border="2">
   <tr>
     <td style="color: green">Stefan</td>
     <td style="color: green">Froemken</td>
   </tr>
   <tr>
     <td style="color: red">Bastian</td>
     <td style="color: red">Krump</td>
   </tr>
   <tr>
     <td style="color: blue">Thorsten</td>
     <td style="color: blue">Ploemi</td>
   </tr>
   <tr>
     <td style="color: green">Max</td>
     <td style="color: green">Mustermann</td>
   </tr>
 </table>
