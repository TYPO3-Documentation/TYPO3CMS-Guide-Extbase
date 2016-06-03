.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../../Includes.txt

f:be.buttons.shortcut
=====================

This ViewHelper provides the bookmark function used in the backend.

Features
--------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Property
   :Datatype,20:    Variable type
   :Description,40: Description
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    getVars
   :Datatype:    Array
   :Description: If empty, the page UID, module and module arguments to save with the bookmark.
   :Standard:    Empty array
   :Mandatory:   No

 - :Property:    setVars
   :Datatype:    Array
   :Description: See template::makeShortcutIcon(). Usually not used for Extbase extensions.
   :Standard:    Empty array
   :Mandatory:   No

Example
-------

::

 <f:be.buttons.shortcut />