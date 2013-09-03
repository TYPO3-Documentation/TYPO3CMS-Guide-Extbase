.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../../Includes.txt

f:be.buttons.icon
=================

With this ViewHelper you can generate these little linked icons like f.e. edit, delete,
new and many other more.

Features
--------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Property
   :Datatype,20:    Dataype
   :Description,40: Description
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    uri
   :Datatype:    String
   :Description: target url. Can be created by a f:uri.*-ViewHelper
   :Standard:    NULL
   :Mandatory:   No

 - :Property:    icon
   :Datatype:    String
   :Description: the name to use
   :Standard:    actions-document-close
   :Mandatory:   No

 - :Property:    title
   :Datatype:    String
   :Description: title attribute for the link
   :Standard:    empty string
   :Mandatory:   No

There is a predefined set of possible values for the icon parameter. In case of not knowing what they are, insert something definitely wrong. The answer contains all valid parameter values:

"foo" is no valid icon. Allowed are: "add", "add_workspace", "button_down", "button_hide", "button_left", "button_unhide", "button_right", "button_up", "clear_cache", "clip_copy", "clip_cut", "clip_pasteafter", "closedok", "datepicker", "deletedok", "edit2", "helpbubble", "icon_fatalerror", "icon_note", "icon_ok", "icon_warning", "new_el", "options", "perm", "refresh_n", "saveandclosedok", "savedok", "savedoknew", "savedokshow", "viewdok", "zoom".

Example
-------

in combination with an f:uri.action viewhelper providing the target url

::

 <f:be.buttons.icon uri="{f:uri.action(action:'new')}" icon="button_unhide" />

