.. include:: ../../../Includes.txt

f:be.tableList
==============

A very useful ViewHelper. We can use the familiar view from the Web->List module and configure it for our own purposes.

Properties
----------

tableName
~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    The name of the database table.

:aspect:`Default value`
    NULL

:aspect:`Required`
    Yes

fieldList
~~~~~~~~~
:aspect:`Variable type`
    Array

:aspect:`Description`
    List of fields to be displayed. If empty, only the title column (configured in $TCA[$tableName]['ctrl']['title']) is shown.

:aspect:`Default value`
    NULL

:aspect:`Required`
    No

storagePid
~~~~~~~~~~
:aspect:`Variable type`
    Integer

:aspect:`Description`
    By default, records are fetched from the storage PID configured in persistence.storagePid. With this argument,
    the storage PID can be overwritten.

:aspect:`Default value`
    NULL

:aspect:`Required`
    Yes

levels
~~~~~~
:aspect:`Variable type`
    Integer

:aspect:`Description`
    Corresponds to the level selector of the TYPO3 list module.
    By default only records from the current storagePid are fetched.

:aspect:`Default value`
    0

:aspect:`Required`
    Yes

filter
~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Corresponds to the "Search String" textbox of the TYPO3 list module.
    If not empty, only records matching the string will be fetched.

:aspect:`Default value`
    Empty String

:aspect:`Required`
    No

recordsPerPage
~~~~~~~~~~~~~~
:aspect:`Variable type`
    Integer

:aspect:`Description`
    The amount of records to be displayed at once.
    Defaults to $TCA[$tableName]['interface']['maxSingleDBListItems'] or (if that's not set) to 100.

:aspect:`Default value`
    0

:aspect:`Required`
    No

sortField
~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    The table field by which the applicable records should be sorted.

:aspect:`Default value`
    Empty String

:aspect:`Required`
    Yes

sortDescending
~~~~~~~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    If set to TRUE, the records will be sorted in descending order.

:aspect:`Default value`
    FALSE

:aspect:`Required`
    No

readOnly
~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    If set to TRUE, the edit icons won't be shown.
    Otherwise edit icons will be shown, if the current BE user has edit rights for the specified table!

:aspect:`Default value`
    FALSE

:aspect:`Required`
    No

enableClickMenu
~~~~~~~~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    When active, the context menu will be activated for the view.

:aspect:`Default value`
    TRUE

:aspect:`Required`
    No

clickTitleMode
~~~~~~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    A choice of “edit”, “info” or “show”. The mode “show” only applies to records from the “pages” or ”tt_content” 
    types. Under usual circumstances, you need to either work using the content menu or an alternative module. Now, 
    clicking on the record title will be sufficient.

:aspect:`Default value`
    NULL

:aspect:`Required`
    No

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

    <f:be.tableList tableName="tt_content" fieldList="{0: 'header', 1: 'bodytext'}" storagePid="1" levels="5" clickTitleMode="show" />
