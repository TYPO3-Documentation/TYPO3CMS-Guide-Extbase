.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../Includes.txt

f:alias
=======

This ViewHelper creates variables that you can use when developing Fluid views. You create variables which contain either 
static values or dynamic values from objects or other ViewHelpers.

Details
-------

map
~~~
:aspect:`Variable type`
    Array

:aspect:`Description`
    The key is the name by which the variable is known, where the value reflects the content.
   :Standard:

:aspect:`Mandatory`
    Yes

Examples for static values
--------------------------

::

 <f:alias map="{firstName: 'Stefan', lastName: 'Froemken'}">
   <p>Hello, my name is {firstName} {lastName}</p>
 </f:alias>

**Output**

::

 <p>Hello, my name is Stefan Froemken</p>

Example for results from another ViewHelper
--------------------------------------------

::

 <f:alias map="{amount: '{addresses->f:count()}'}">
   <p>There are {amount} records in database</p>
 </f:alias>

**Output**

::

 <p>There are 23 records in database</p>

Example for values from an object
---------------------------------

::

 <f:alias map="{firstName: address.firstName, lastName: address.lastName}">
   <p>Hello, my name is {firstName} {lastName}</p>
 </f:alias>

**Output**

::

 <p>Hello, my name is Stefan Froemken</p>
