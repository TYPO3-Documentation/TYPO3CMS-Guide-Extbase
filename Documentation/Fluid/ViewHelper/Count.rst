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

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Property
   :Datatype,20:    Variable type
   :Description,40: Description
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    subject
   :Datatype:    Array
   :Description: Provide the array or object containing the entries to be counted. If this value is empty, the view 
                 helper will attempt to interpret the content between the tags as an array, and then count its entries.
   :Standard:    NULL
   :Mandatory:   No

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
