.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../Includes.txt

f:count
=======

This ViewHelper counts the elements in the referenced object or array.

Properties
----------

subject
~~~~~~~
:aspect:`Variable type`
    Array

:aspect:`Description`
    Provide the array or object containing the entries to be counted. If this value is empty, the ViewHelper 
   will attempt to interpret the content between the tags as an array, and then count its entries.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

Example: array as renderChildren
--------------------------------

::

 <p>There are <f:count>{addresses}</f:count> records in our database</p>

**Output**

::

 <p>There are 23 records in our database</p>

Example: array by subject
-------------------------

::

 <p>There are <f:count subject="{addresses}" /> records in our database</p>

**Output**

::

 <p>There are 23 records in our database</p>

Example: inline notation
------------------------

::

 <p>There are {f:count(subject: addresses)} records in our database</p>

**Output**

::

 <p>There are 23 records in our database</p>

Example: better inline notation
-------------------------------

::

 <p>There are {addresses -> f:count()} records in our database</p>

**Output**

::

 <p>There are 23 records in our database</p>
