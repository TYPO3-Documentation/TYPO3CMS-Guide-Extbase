.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../Includes.txt

f:section
=========

A Section is similar to a Partial. The difference is that Partials are separate files, where Sections are defined within 
the same template file.

Properties
---------

 - :Property:    name
:aspect:`Variable type`
    String

:aspect:`Description`
    A name which can be referenced in order to fetch the content contained within the f:section tage.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    Yes

Example
-------

::

 <f:section name="TableRow">
   <tr>
     <td>{employee.first_name}</td>
     <td>{employee.city}</td>
   </tr>
 </f:section>
 
 <f:alias map="{employees: {0: {first_name: 'Stefan', city: 'Lindlar'},1: {first_name: 'Petra', city: 'Lindlar'},2: {first_name: 'Sascha', city: 'Remscheid'},3: {first_name: 'Patrick', city: 'Bonn'},4: {first_name: 'Sven', city: 'Gummersbach'},5: {first_name: 'Andrea', city: 'Wuppertal'}}}">
   <table cellpadding="5" cellspacing="0" border="2">
     <f:for each="{employees}" as="employee">
       <f:render section="TableRow" arguments="{employee: employee}"/>
     </f:for>
   </table>
 </f:alias>

As you can see, we've defined a Section to contain the content of a table row. Then we've passed the employee data to 
this section on each iteration in the loop, to output the same HTML each time but containing the individual employee information.