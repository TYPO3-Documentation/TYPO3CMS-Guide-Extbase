.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../Includes.txt

f:cObject
=========

This view helper provides a connection to TypoScript. Pass in a TypoScript object path (lib.*) and let TypoScript 
do the work.

Properties
-------------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Property
   :Datatype,20:    Data type
   :Description,40: Description
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    typoscriptObjectPath
   :Datatype:    String
   :Description: The TypoScript object path
   :Standard:
   :Mandatory:   Yes

 - :Property:    data
   :Datatype:    Mixed
   :Description: The TypoScript object path
   :Standard:    NULL
   :Mandatory:   No

 - :Property:    currentValueKey
   :Datatype:    String
   :Description: The TypoScript object path
   :Standard:    NULL
   :Mandatory:   No


Simple example
--------------

**TypoScript**

::

 lib.fluidText = TEXT
 lib.fluidText {
   value = Text from TypoScript
 }

**Fluid template**

::

 <p><f:cObject typoscriptObjectPath="lib.fluidText" /></p>

**Output**

::

 <p>Text from TypoScript</p>

Example for a localized date value
----------------------------------

The f:format.date view helper works with the PHP function date(), so it can only output English month names. It would 
be better if we could use strftime: TypoScript provides dates formatted using strftime. Here's an example, using the 
current date and a German date format.

**TypoScript**

::

 lib.formattedDate = TEXT
 lib.formattedDate {
   current = 1
   strftime = %d. %B %Y
 }

**Fluid template**

::

 <p><f:cObject typoscriptObjectPath="lib.formattedDate">{address.dayOfBirth}</f:cObject></p>

**Output**

::

 <p>17. Januar 2013</p>

Example with an array or object
-------------------------------

**TypoScript**

::

 lib.address = COA
 lib.address {
   10 = TEXT
   10.value.current = 1
   10.value.wrap = <p>First name: |</p>
   20 = TEXT
   20.value.dataWrap = <p>Full name: {field: firstName} {field: lastName}
 }

**Fluid template**

::

 <f:cObject typoscriptObjectPath="lib.address" data="{address}" currentValueKey="firstName" />

**Output**

::

 <p>First name: Stefan</p><p>Full name: Stefan Froemken</p>

.. tip::

   As explained above, you can use currentValueKey to define which value should be provided using current=1. You can 
   access other values from the array using "field", as per the example.
