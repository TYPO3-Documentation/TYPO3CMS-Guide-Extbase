.. include:: ../../../Includes.txt

==============
f:be.tableList
==============

A very useful ViewHelper. We can use the familiar view from the Web->List
module and configure it for our own purposes.

Properties
==========


.. rst-class:: dl-parameters

tableName
   :sep:`|` :aspect:`Condition:`  required
   :sep:`|` :aspect:`Type:`       string
   :sep:`|` :aspect:`Default:`    null
   :sep:`|`

   The name of the database table.

fieldList
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       array
   :sep:`|` :aspect:`Default:`    null
   :sep:`|`

   List of fields to be displayed. If empty, only the title column (configured
   in :php:` $TCA[$tableName]['ctrl']['title']`) is shown.


storagePid
   :sep:`|` :aspect:`Condition:`  required
   :sep:`|` :aspect:`Type:`       integer
   :sep:`|` :aspect:`Default:`    null
   :sep:`|`

   By default, records are fetched from the storage PID configured in
   persistence.storagePid. With this argument, the storage PID can be
   overwritten.


levels
   :sep:`|` :aspect:`Condition:`  required
   :sep:`|` :aspect:`Type:`       integer
   :sep:`|` :aspect:`Default:`    0
   :sep:`|`

   Corresponds to the level selector of the TYPO3 list module. By default only
   records from the current storagePid are fetched.


filter
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       string
   :sep:`|` :aspect:`Default:`    empty string
   :sep:`|`

   Corresponds to the "Search String" textbox of the TYPO3 list module. If not
   empty, only records matching the string will be fetched.


recordsPerPage
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       integer
   :sep:`|` :aspect:`Default:`    ... \| 100
   :sep:`|`

   The amount of records to be displayed at once. Defaults to
   :php:`$TCA[$tableName]['interface']['maxSingleDBListItems']` or (if that's
   not set) to 100.


sortField
   :sep:`|` :aspect:`Condition:`  required
   :sep:`|` :aspect:`Type:`       string
   :sep:`|` :aspect:`Default:`    empty string
   :sep:`|`

   The table field by which the applicable records should be sorted.


sortDescending
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       boolean
   :sep:`|` :aspect:`Default:`    false
   :sep:`|`

   If set to TRUE, the records will be sorted in descending order.


readOnly
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       boolean
   :sep:`|` :aspect:`Default:`    false
   :sep:`|`

   If set to TRUE, the edit icons won't be shown. Otherwise edit icons will be
   shown, if the current BE user has edit rights for the specified table!


enableClickMenu
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       boolean
   :sep:`|` :aspect:`Default:`    true
   :sep:`|`

   When active, the context menu will be activated for the view.


clickTitleMode
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       string
   :sep:`|` :aspect:`Default:`    null
   :sep:`|`

   A choice of “edit”, “info” or “show”. The mode “show” only applies to
   records from the “pages” or ”tt_content” types. Under usual circumstances,
   you need to either work using the content menu or an alternative module.
   Now, clicking on the record title will be sufficient.


Minimal example
===============

The following example shows a table containing the header and bodytext fields
of matching tt_content records. The table will only be displayed if there are
records of this type available in the page defined by storagePid.

All backend modules - at least, those created using the Extension Builder -
come with an extension template which must be bound to the site's root page.
You can then define the page uid in the TypoScript constants as a fallback, in
the event that storagePid isn't defined. (As is the case in this example.)

::

   <f:be.tableList tableName="tt_content" 
                    fieldList="{
                      0: 'header', 
                      1: 'bodytext'}" 
   />


Example: maximum number of records
==================================

Although we haven't defined recordsPerPage in the following example, only 100
of more than 150 records will be displayed within the data delivered with the
Introduction Package. This is because where the property recordsPerPage isn't
defined, the value from TCA
(:php:`$TCA[TabellenName]['interface']['maxSingleDBListItems']`) is applicable.
Where this isn't set, then the limit is set to 100. If you need to show more
than 100 records (in this example), use the property recordsPerPage.

::

   <f:be.tableList tableName="tt_content" 
                   fieldList="{
                      0: 'header', 
                      1: 'bodytext'}" 
                   storagePid="1" 
                   levels="5" 
   />


Example: show records directly
==============================

You normally need to switch to the Web->View module or navigate via the context
menu to see a preview of a selected record. A much easier option is to link the
title of the record in such a way that clicking on it reveals a preview. This
is where the property clickTitleMode comes into play, when it's set to “show”.
(The following example also contains an example of the use of alternating
background colours.)

::

   <f:be.tableList tableName="tt_content" 
                   fieldList="{
                      0: 'header', 
                      1: 'bodytext'}" 
                   storagePid="1" 
                   levels="5" 
                   clickTitleMode="show" 
   />
