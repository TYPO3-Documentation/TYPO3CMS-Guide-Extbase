.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../../Includes.txt

f:be.widget.paginate
====================

This ViewHelper allows you to split a large amount of data into chunks across multiple pages, to define the number of 
records on each page, and to define where and how the navigation between the pages should appear.

Properties
----------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Property
   :Datatype,20:    Variable type
   :Description,40: Description
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    objects
   :Datatype:    QueryResultInterface
   :Description: Not the result objects themselves, but the object from the Repository which contains the data needed 
                 to reproduce the SQL command. The SQL statement object and the SQL command aren't allowed here, as 
                 Extbase won't be able to work out how to implement the LIMIT attribute which controls the division of 
                 the data into paginated results.
   :Standard:
   :Mandatory:   Yes

 - :Property:    as
   :Datatype:    String
   :Description: The name of the variable in which the reduced object is made available.
   :Standard:
   :Mandatory:   Yes

 - :Property:    configuration
   :Datatype:    Array
   :Description: Configuration of the page navigation
   :Standard:    See "Configuration of the page navigation"
   :Mandatory:   No

Configuration of the page navigation
------------------------------------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Property
   :Datatype,20:    Variable type
   :Description,40: Description
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    itemsPerPage
   :Datatype:    QueryResultInterface
   :Description: The number of objects which may be associated with each page in the series.
   :Standard:    10
   :Mandatory:   No

 - :Property:    insertAbove
   :Datatype:    Boolean
   :Description: Display the page navigation above the results.
   :Standard:    FALSE
   :Mandatory:   No

 - :Property:    insertBelow
   :Datatype:    Boolean
   :Description: Display the page navigation below the results.
   :Standard:    TRUE
   :Mandatory:   No

 - :Property:    recordsLabel
   :Datatype:    String
   :Description: An optional text to replace the standard descriptor “Records 1 - xy”.
   :Standard:    Empty string
   :Mandatory:   No
