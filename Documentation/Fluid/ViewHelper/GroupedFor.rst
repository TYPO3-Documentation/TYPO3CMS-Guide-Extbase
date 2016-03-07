.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../Includes.txt

f:groupedFor
============

A very powerful view helper in the area of list generation. Pass an array to the view helper with a grouping criterium, 
and you'll get an array of elements which match the group criterium in each iteration.

Properties
----------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Property
   :Datatype,20:    Data type
   :Description,40: Description
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    each
   :Datatype:    Array
   :Description: The array or object to be iterated
   :Standard:
   :Mandatory:   Yes

 - :Property:    as
   :Datatype:    String
   :Description: The name of the variable which contains the grouped entries
   :Standard:
   :Mandatory:   Yes

 - :Property:    groupBy
   :Datatype:    String
   :Description: The property by which the array should be grouped.
   :Standard:
   :Mandatory:   Yes

 - :Property:    groupKey
   :Datatype:    String
   :Description: The grouped value can be accessed by this key from within each f:groupedBy tag.
   :Standard:
   :Mandatory:   Yes

Example
--------

::

 <f:alias map="{employees: {0: {first_name: 'Stefan', city: 'Lindlar'},1: {first_name: 'Petra', city: 'Lindlar'},2: {first_name: 'Sascha', city: 'Remscheid'},3: {first_name: 'Patrick', city: 'Bonn'},4: {first_name: 'Sven', city: 'Gummersbach'},5: {first_name: 'Andrea', city: 'Wuppertal'}}}">
   <table cellpadding="5" cellspacing="0" border="2">
     <f:groupedFor each="{employees}" as="employeesByCity" groupBy="city" groupKey="city">
       <tr>
         <th colspan="2">{city}</th>
       </tr>
       <f:for each="{employeesByCity}" as="employee">
         <tr>
           <td>{employee.first_name}</td>
           <td>{employee.city}</td>
         </tr>
       </f:for>
     </f:groupedFor>
   </table>
 </f:alias>

Here's an example with six employees. As you can see, the f:groupedBy view helper groups the employees by city. An 
experienced eye will see that the first employees in the array work in Lindlar.

So that we can access the city names within the f:groupedBy tags, we'll use the 'groupKey' “city”. (The values 'groupBy' 
and 'groupKey' don't need to match: you could use 'city' as a groupKey too.

By referring to the variable 'as', you can access the elements of the first city employees and loop through them with 
a f:for loop.