.. include:: ../../../../Includes.txt

f:be.widget.paginate
====================

This ViewHelper allows you to split a large amount of data into chunks across multiple pages, to define the number of 
records on each page, and to define where and how the navigation between the pages should appear.

Properties
----------

objects
~~~~~~~
:aspect:`Variable type`
    QueryResultInterface

:aspect:`Description`
    Not the result objects themselves, but the object from the Repository which contains the data needed to reproduce 
    the SQL command. The SQL statement object and the SQL command aren't allowed here, as Extbase won't be able to 
    work out how to implement the LIMIT attribute which controls the division of the data into paginated results.

:aspect:`Default value`


:aspect:`Required`
    Yes

as
~~
:aspect:`Variable type`
    String

:aspect:`Description`
    The name of the variable in which the reduced object is made available.
   :Default value:

:aspect:`Required`
    Yes

configuration
~~~~~~~~~~~~~
:aspect:`Variable type`
    Array

:aspect:`Description`
    Configuration of the page navigation

:aspect:`Default value`
    See "Configuration of the page navigation"

:aspect:`Required`
    No

Configuration of the page navigation
------------------------------------

itemsPerPage
~~~~~~~~~~~~
:aspect:`Variable type`
    QueryResultInterface

:aspect:`Description`
    The number of objects which may be associated with each page in the series.

:aspect:`Default value`
    10

:aspect:`Required`
    No

insertAbove
~~~~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    Display the page navigation above the results.

:aspect:`Default value`
    FALSE

:aspect:`Required`
    No

insertBelow
~~~~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    Display the page navigation below the results.

:aspect:`Default value`
    TRUE

:aspect:`Required`
    No

recordsLabel
~~~~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    An optional text to replace the standard descriptor “Records 1 - xy”.

:aspect:`Default value`
    Empty string

:aspect:`Required`
    No
