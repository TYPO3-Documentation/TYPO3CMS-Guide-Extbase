.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../Includes.txt

f:cycle
=======

You can improve the output of the f:for ViewHelper using f:cycle. For example, you can add odd/even classes to a 
table row. While you can reach the first and last elements using f:for, you'll need to use f:cycle to reach any of 
the other entries.

Properties
----------

 - :Property,20:    Properties
   :Datatype,20:    Variable type
   :Description,40: Description
   :Standard,10:    Default value
   :Mandatory,10:   Mandatory

values
~~~~~~
:aspect:`Variable type`
    Array

:aspect:`Description`
    Input in array notation. (See example for details.)
   :Standard:

:aspect:`Mandatory`
    Yes

as
~~
:aspect:`Variable type`
    String

:aspect:`Description`
    The name of the new variable for subsequent use in your template.
   :Standard:

:aspect:`Mandatory`
    Yes

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

**Output**

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
