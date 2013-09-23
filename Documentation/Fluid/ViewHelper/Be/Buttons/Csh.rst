.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../../Includes.txt

f:be.buttons.csh
================

This ViewHelper is rarely used, but very helpful nonetheless. It enables to include hints into Backend forms.
TYPO3 uses this functionality all over the backend, and it is noticeable by the small question mark images. When hovered it reveals the helptext in a little tooltip. It can be activated by mouse click and then display the help text in a popup window.
There is a setting in the user configuration whether to show the popup or not.

Features
--------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Property
   :Datatype,20:    Datatype
   :Description,40: Description
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    table
   :Datatype:    String
   :Description: table name
   :Standard:    NULL
   :Mandatory:   No

 - :Property:    field
   :Datatype:    String
   :Description: the key from locallang file to use
   :Standard:    empty string
   :Mandatory:   No

 - :Property:    iconOnly
   :Datatype:    Boolean
   :Description: display the icon, but not the text
   :Standard:    FALSE
   :Mandatory:   No

 - :Property:    styleAttributes
   :Datatype:    String
   :Description: additional style attribute, added to the containing table
   :Standard:    empty string
   :Mandatory:   No

Example
-------

Usually in the most TYPO3 tables the language file key is the same as the column name:

::

 <f:be.buttons.csh table="tt_content" field="header" />

Example with style attribute
----------------------------

Make sure there is the following setting in userTSconfig:

::

 setup.override.edit_showFieldHelp=text

Now the icon has changed:

::

 <f:be.buttons.csh table="tt_content" field="header" styleAttributes="background-color: red;" />