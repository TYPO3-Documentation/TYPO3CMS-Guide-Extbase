
.. include:: ../../Includes.txt

f:groupedFor
============

A very powerful ViewHelper in the area of list generation. Pass an array to the ViewHelper with a grouping criterium,
and you'll get an array of elements which match the group criterium in each iteration.

Properties
----------

each
~~~~
:aspect:`Variable type`
    Array

:aspect:`Description`
    The array or object to be iterated

:aspect:`Mandatory`
    Yes

as
~~
:aspect:`Variable type`
    String

:aspect:`Description`
    The name of the variable which contains the grouped entries

:aspect:`Mandatory`
    Yes

groupBy
~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    The property by which the array should be grouped.

:aspect:`Mandatory`
    Yes

groupKey
~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    The grouped value can be accessed by this key from within each `f:groupedBy` tag.

:aspect:`Mandatory`
    Yes

Example
-------

.. code-block:: xhtml

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

Here's an example with six employees. As you can see, the `f:groupedFor` ViewHelper groups the employees by city. An
experienced eye will see that the first employees in the array work in Lindlar.

So that we can access the city names within the `f:groupedFor` tags, we'll use the 'groupKey' "city". (The values 'groupBy'
and 'groupKey' don't need to match: you could use 'city' as a groupKey too.

By referring to the variable 'as', you can access the elements of the first city employees and loop through them with
a `f:for` loop.
