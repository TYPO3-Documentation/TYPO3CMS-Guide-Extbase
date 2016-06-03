.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:format.bytes
==============

This ViewHelper converts a value in bytes (integer) into a readable format.

Properties
----------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    property
   :Datatype,20:    Variable type
   :Description,40: Description
   :Standard,10:    Default value
   :Mandatory,10:   Mandatory

 - :Property:    value
   :Datatype:    Integer
   :Description: The integer value (bytes) to be converted.
   :Standard:    NULL
   :Mandatory:   No

 - :Property:    decimals
   :Datatype:    Integer
   :Description: The number of decimals to be shown after the decimal point.
   :Standard:    0
   :Mandatory:   No

 - :Property:    decimalSeparator
   :Datatype:    String
   :Description: The character to use as the decimal separator.
   :Standard:    .
   :Mandatory:   No

 - :Property:    thousandsSeparator
   :Datatype:    String
   :Description: The character to use as the “thousands” separator.
   :Standard:    ,
   :Mandatory:   No

Example
-------

With a value of 1024.33, using the code 

::

 <f:format.bytes>{fileSize}</f:format.bytes>

will output

::

 1024 KB
