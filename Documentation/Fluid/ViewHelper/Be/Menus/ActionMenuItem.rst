.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../../Includes.txt

f:be.menus.actionMenuItem
=========================

You can use this ViewHelper to create a menu entry for your backend module. For this to work, the call to this 
ViewHelper must be placed within a `f:be.menus.actionMenu` ViewHelper.


Properties
----------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Property
   :Datatype,20:    Variable type
   :Description,40: Description
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    label
   :Datatype:    String
   :Description: The name to display in the menu
   :Standard:    NULL
   :Mandatory:   Yes

 - :Property:    controller
   :Datatype:    String
   :Description: The Controller in which the appropriate Action lies.
   :Standard:    NULL
   :Mandatory:   Yes

 - :Property:    action
   :Datatype:    String
   :Description: Which Action should be called when this menu entry is selected.
   :Standard:    NULL
   :Mandatory:   Yes

 - :Property:    arguments
   :Datatype:    Array
   :Description: Parameters to be passed to the Action.
   :Standard:    Empty array
   :Mandatory:   Yes

Example
--------

The following menu contains a Select element with two menu entries. Selecting an entry calls the indicated Action within 
the indicated Controller. As you can see, you can either define the menu entry label directly, or (better) through the 
use of the `f:translate` ViewHelper.

::

 <f:be.menus.actionMenu>
   <f:be.menus.actionMenuItem label="New" controller="Fluid" action="new" />
   <f:be.menus.actionMenuItem label="{f:translate(key='List')}" controller="Fluid" action="list" />
 </f:be.menus.actionMenu>