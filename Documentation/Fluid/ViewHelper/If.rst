.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../Includes.txt

f:if
====

Even though the usage of this ViewHelper is a little limited, it's one of the ViewHelpers you should know well. If 
you're familiar with the old fed:if ViewHelper, you'll know what we're talking about.

Properties
----------

condition
~~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    The content of the variable comparison rules. (See the examples.)

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    Yes

The following comparators are allowed: ==, !=, <, <=, >, >= and %

Only variables of the following types can be compared: numbers, object properties, arrays, strings (since v6.2) and 
the results of other ViewHelpers.

Simple examples
---------------

::

 <f:alias map="{value1: 1, value5: 5}">
   <f:if condition="{value1}==1">
     <p>The value is 1</p>
   </f:if>
   <f:if condition="{value5}==5">
     <f:then>
       <p>The value is 5</p>
     </f:then>
     <f:else>
       <p>The value is NOT 5</p>
     </f:else>
   </f:if>
   <f:if condition="{value5} % 2">
     <f:then>
       <p>The calculation returns a remainder value of 1.</p>
     </f:then>
     <f:else>
       <p>The calculation did not return a remainder value.</p>
     </f:else>
   </f:if>
   <f:if condition="{value1}!={value5}">
     <p>value1 is NOT equal to value5</p>
   </f:if>
   <f:if condition="{value1}<{value5}">
     <p>value1 is smaller than value5</p>
   </f:if>
   <f:if condition="{0:value1,1:value5}=={0:1,1:5}">
     <p>Values in the first array are all the same as the values in the second array.</p>
   </f:if>
 </f:alias>
 <f:alias map="{elements: {0: value1, 1: value2}}">
   <f:if condition="{elements -> f:count()}==2">
     <p>Comparing with ViewHelpers: the array contains 2 elements.</p>
   </f:if>
 </f:alias>
 <f:alias map="{value1: 'hello'}">
   <f:if condition="{value1} == 'hello'">
     <p>String comparison works since v6.2.</p>
   </f:if>
   <f:if condition="{0: value1} == {0: 'hello'}">
     <p>String comparisons only work in array syntax before v6.2.</p>
   </f:if>
 </f:alias>


If there are no `f:then` or `f:else` ViewHelpers in use, the content between the `f:if` ViewHelpers will only be output if 
the comparison returns a positive result. If you need to use the full if-then-else construct, then you'll have to 
use the `f:then` / `f:else` ViewHelpers.
