.. include:: ../../Includes.txt
.. highlight:: html

=====
f:for
=====

The `f:for` viewhelper is the preferred viewhelper to form loops and lists.


Usage
=====

Minimal usage:
   ::

      <f:for each="{items}" as="item">
         ...
      </f:for>


All parameters:
   ::

      <f:for each="{items}" as="item" key="itemkey"
             reverse="false" iteration="iterator">
         ...
      </f:for>


Parameters
==========

.. rst-class:: dl-parameters

each
   :sep:`|` :aspect:`Condition:`  required
   :sep:`|` :aspect:`Type:`       array
   :sep:`|` :aspect:`Default:`    NULL
   :sep:`|`

   The **array** or **object** to be iterated.

as
   :sep:`|` :aspect:`Condition:`  required
   :sep:`|` :aspect:`Type:`       string
   :sep:`|` :aspect:`Default:`    NULL
   :sep:`|`

   The **name of the variable** which contains the value
   for the current loop iteration.

key
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       string
   :sep:`|` :aspect:`Default:`    empty string
   :sep:`|`

   The **name of the variable** that contains the key
   of the current loop iteration.

reverse
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       boolean
   :sep:`|` :aspect:`Default:`    false
   :sep:`|`

   A **boolean flag**. Use *true* to reverse the sequence.

   *Examples of true:* `reverse="true"`, `reverse="1"`, `reverse="abc"`.

   *Examples of false:* `reverse="false"`, `reverse="0"`, `reverse=""`.

iteration
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       string
   :sep:`|` :aspect:`Default:`    NULL
   :sep:`|`

   The **name of a variable** that holds the iteration data of each loop.

   *Example:* `iteration="iterator"`. Iteration data can then be accessed
   like `{iterator.index}`, `{iterator.cycle}`, `{iterator.total}`,
   `{iterator.isEven}`, `{iterator.isOdd}`.

   *Attention:* `iterator.cycle` is just a simple counter.  It has nothing to
   do with the viewhelper `f:cycle`.

Examples
========

Example: Exhaustive usage
-------------------------

1. Page typoscript template:

   .. code-block:: typoscript

      page = PAGE
      page {
         10 = FLUIDTEMPLATE
         10.file = fileadmin/FluidForLoopExample.html
      }

2. Fluid html template in file :file:`fileadmin/FluidForLoopExample.html`::

      <p><b>FluidForLoopExample.html</b></p>
      <hr>
      <f:alias map="{
         employees: {
            0: {first_name: 'Aname', city: 'Atown'},
            1: {first_name: 'Bname', city: 'Btown'},
            2: {first_name: 'Cname', city: 'Ctown'},
            3: {first_name: 'Dname', city: 'Dtown'},
            4: {first_name: 'Ename', city: 'Etown'},
            5: {first_name: 'Fname', city: 'Ftown'}}}">

         <p>Legend:<br>
            <br> 01 = employee.first_name
            <br> 02 = employee.city
            <br> 03 = itemkey
            <br> 04 = iterator.index
            <br> 05 = iterator.cycle
            <br> 06 = iterator.isFirst
            <br> 07 = iterator.isLast
            <br> 08 = iterator.isOdd
            <br> 09 = iterator.isEven
            <br> 10 = iterator.total
         </p>

         <p>reverse = "false" </p>

         <table cellpadding="3" cellspacing="0" border="1">
            <tr>
               <th>01</th>
               <th>02</th>
               <th>03</th>
               <th>04</th>
               <th>05</th>
               <th>06</th>
               <th>07</th>
               <th>08</th>
               <th>09</th>
               <th>10</th>
            </tr>
            <f:for each="{employees}" as="employee" key="itemkey"
                   reverse="false" iteration="iterator">
               <tr>
                  <td>{employee.first_name}</td>
                  <td>{employee.city}      </td>
                  <td>{itemkey}            </td>
                  <td>{iterator.index}     </td>
                  <td>{iterator.cycle}     </td>
                  <td>{iterator.isFirst}   </td>
                  <td>{iterator.isLast}    </td>
                  <td>{iterator.isOdd}     </td>
                  <td>{iterator.isEven}    </td>
                  <td>{iterator.total}     </td>
               </tr>
            </f:for>
         </table>
      </f:alias>

3. Result for `reverse="false"`:

   .. figure:: For.rst.001.png
      :class: with-shadow

      With `reverse="false"` items appear in normal (default) order.

4. Result for `reverse="true"`:

   .. figure:: For.rst.002.png
      :class: with-shadow

      With `reverse="true"` items appear in reversed order. Everything else
      remains.


Example: Minimum usage
----------------------

::

   <f:alias map="{
      employees: {
         0: {first_name: 'Stefan', city: 'Lindlar'},
         1: {first_name: 'Petra', city: 'Lindlar'},
         2: {first_name: 'Sascha', city: 'Remscheid'},
         3: {first_name: 'Patrick', city: 'Bonn'},
         4: {first_name: 'Sven', city: 'Gummersbach'},
         5: {first_name: 'Andrea', city: 'Wuppertal'}}}
   ">
      <table cellpadding="5" cellspacing="0" border="2">
         <f:for each="{employees}" as="employee">
            <tr>
               <td>{employee.first_name}</td>
               <td>{employee.city}</td>
            </tr>
         </f:for>
      </table>
   </f:alias>

This creates a new table row for each of the entries in the 'employee' array.


Example: Iterator usage
-----------------------

::

   <f:alias map="{
      employees: {
         0: {first_name: 'Stefan', city: 'Lindlar'},
         1: {first_name: 'Petra', city: 'Lindlar'},
         2: {first_name: 'Sascha', city: 'Remscheid'},
         3: {first_name: 'Patrick', city: 'Bonn'},
         4: {first_name: 'Sven', city: 'Gummersbach'},
         5: {first_name: 'Andrea', city: 'Wuppertal'}
      }
   }">
    <table cellpadding="5" cellspacing="0" border="2">
       <f:for each="{employees}" as="employee" iteration="iterator">
          <f:if condition="{iterator.isFirst}">
             <tr>
                <th colspan="2">List of employees</th>
             </tr>
          </f:if>
          <tr>
             <td>Iteration beginning with 0: {iterator.index}</td>
             <td>Iteration beginning with 1: {iterator.cycle}</td>
             <td{f:if(condition:iterator.isOdd, then: ' style="color: green;"')}>{employee.first_name}</td>
             <td{f:if(condition:iterator.isEven, then: ' style="color: red;"')}>{employee.city}</td>
          </tr>
          <f:if condition="{iterator.isLast}">
             <tr>
                <th colspan="2">Number of employees: {iterator.total}</th>
             </tr>
          </f:if>
       </f:for>
    </table>
 </f:alias>
