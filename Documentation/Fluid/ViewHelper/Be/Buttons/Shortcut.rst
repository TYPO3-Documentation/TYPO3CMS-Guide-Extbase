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

getVars
~~~~~~~
:aspect:`Variable type`
    Array

:aspect:`Description`
    If empty, the page UID, module and module arguments to save with the bookmark.

:aspect:`Default value`
     Empty array

:aspect:`Required`
     No

setVars
~~~~~~~
:aspect:`Variable type`
    Array

:aspect:`Description`
    See template::makeShortcutIcon(). Usually not used for Extbase extensions.

:aspect:`Default value`
     Empty array

:aspect:`Required`
     No

Example
-------

::

 <f:be.buttons.shortcut />