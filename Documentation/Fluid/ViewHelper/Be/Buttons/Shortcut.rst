.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../../Includes.txt

f:be.buttons.shortcut
=====================

This ViewHelper provides the bookmark function used in backend.

Features
--------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Property
   :Datatype,20:    Datatype
   :Description,40: Description
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    getVars
   :Datatype:    Array
   :Description: if empty, page-UID, module and module arguments to save with the bookmark
   :Standard:    empty array
   :Mandatory:   No

 - :Property:    setVars
   :Datatype:    Array
   :Description: see template::makeShortcutIcon(), usually not used for extbase extensions
   :Standard:    empty array
   :Mandatory:   No

Example
-------

::

 <f:be.buttons.shortcut />