.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:be.tableList
==============

A very useful ViewHelper. We can use the familiar view from the Web->List module and configure it for our own 
purposes.

Properties
-------------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Property
   :Datatype,20:    Variable type
   :Description,40: Description
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    tableName
   :Datatype:    String
   :Description: The name of the table.
   :Standard:    NULL
   :Mandatory:   Yes

 - :Property:    storagePid
   :Datatype:    Integer
   :Description: The ID of the page containing the data to be displayed. If this value is not defined, then the records 
                 from the page with the ID set as persistence.storagePid will be displayed.
   :Standard:    NULL
   :Mandatory:   Yes

 - :Property:    levels
   :Datatype:    Integer
   :Description: If the page with the ID defined in the storagePid property contains subpages, this property defines the 
                 nesting level from which records should be collated.
   :Standard:    0
   :Mandatory:   Yes

 - :Property:    filter
   :Datatype:    String
   :Description: Provide a search term by which the records should be filtered.
   :Standard:    Leerer String
   :Mandatory:   Yes

 - :Property:    recordsPerPage
   :Datatype:    Integer
   :Description: The maximum number off records which may be displayed on a single page view.
   :Standard:    0
   :Mandatory:   Yes

 - :Property:    sortField
   :Datatype:    String
   :Description: The field by which the applicable records should be sorted.
   :Standard:    Leerer String
   :Mandatory:   Yes

 - :Property:    sortDescending
   :Datatype:    Boolean
   :Description: When active, this property defines that the sequence of records should be sorted in reverse order.
   :Standard:    FALSE
   :Mandatory:   Yes

 - :Property:    readOnly
   :Datatype:    Boolean
   :Description: When active, the edit icon will not be displayed alongside the records.
   :Standard:    FALSE
   :Mandatory:   Yes

 - :Property:    enableClickMenu
   :Datatype:    Boolean
   :Description: When active, the context menu will be activated for the view.
   :Standard:    TRUE
   :Mandatory:   Yes

 - :Property:    clickTitleMode
   :Datatype:    String
   :Description: A choice of “edit”, “info” or “show”. The mode “show” only applies to records from the “pages” or 
                 ”tt_content” types. Under usual circumstances, you need to either work using the content menu or 
                 an alternative module. Now, clicking on the record title will be sufficient.
   :Standard:    NULL
   :Mandatory:   Yes

 - :Property:    alternateBackgroundColors
   :Datatype:    Boolean
   :Description: When active, the background colour of each table row will be displayed alternately.
   :Standard:    FALSE
   :Mandatory:   Yes

Minimal example
---------------

The following example shows a table containing the header and bodytext fields of matching tt_content records. The table 
will only be displayed if there are records of this type available in the page defined by storagePid.

All backend modules - at least, those created using the Extension Builder - come with an extension template which must 
be bound to the site's root page. You can then define the page uid in the TypoScript constants as a fallback, in the 
event that storagePid isn't defined. (As is the case in this example.)

::

 <f:be.tableList tableName="tt_content" fieldList="{0: 'header', 1: 'bodytext'}" />

Example: maximum number of records
----------------------------------

Although we haven't defined recordsPerPage in the following example, only 100 of more than 150 records will be displayed 
within the data delivered with the Introduction Package. This is because where the property recordsPerPage isn't 
defined, the value from TCA ($TCA[TabellenName]['interface']['maxSingleDBListItems']) is applicable. Where this isn't 
set, then the limit is set to 100. If you need to show more than 100 records (in this example), use the property 
recordsPerPage.

::

 <f:be.tableList tableName="tt_content" fieldList="{0: 'header', 1: 'bodytext'}" storagePid="1" levels="5" />

Example: show records directly
------------------------------

You normally need to switch to the Web->View module or navigate via the context menu to see a preview of a selected 
record. A much easier option is to link the title of the record in such a way that clicking on it reveals a preview. 
This is where the property clickTitleMode comes into play, when it's set to “show”. (The following example also 
contains an example of the use of alternating background colours.)

::

 <f:be.tableList tableName="tt_content" fieldList="{0: 'header', 1: 'bodytext'}" storagePid="1" levels="5" alternateBackgroundColors="TRUE" clickTitleMode="show" />