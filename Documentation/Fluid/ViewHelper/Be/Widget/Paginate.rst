.. include:: ../../../../Includes.txt

====================
f:be.widget.paginate
====================

This ViewHelper allows you to split a large amount of data into chunks across
multiple pages, to define the number of records on each page, and to define
where and how the navigation between the pages should appear.

Properties
==========

.. rst-class:: dl-parameters

objects
   :sep:`|` :aspect:`Condition:`  required
   :sep:`|` :aspect:`Type:`       QueryResultInterface
   :sep:`|`

   Not the result objects themselves, but the object from the Repository which
   contains the data needed to reproduce the SQL command. The SQL statement
   object and the SQL command aren't allowed here, as Extbase won't be able to
   work out how to implement the LIMIT attribute which controls the division of
   the data into paginated results.


as
   :sep:`|` :aspect:`Condition:`  required
   :sep:`|` :aspect:`Type:`       string
   :sep:`|`

   The name of the variable in which the reduced object is made available.


configuration
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       array
   :sep:`|` :aspect:`Default:`    See "Configuration of the page navigation"
   :sep:`|`

   Configuration of the page navigation


Configuration of the page navigation
====================================

.. rst-class:: dl-parameters

itemsPerPage
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       QueryResultInterface
   :sep:`|` :aspect:`Default:`    10
   :sep:`|`

   The number of objects which may be associated with each page in the series.


insertAbove
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       boolean
   :sep:`|` :aspect:`Default:`    false
   :sep:`|`

   Display the page navigation above the results.


insertBelow
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       boolean
   :sep:`|` :aspect:`Default:`    true
   :sep:`|`

   Display the page navigation below the results.


recordsLabel
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       string
   :sep:`|` :aspect:`Default:`    empty string
   :sep:`|`

   An optional text to replace the standard descriptor “Records 1 - xy”.

