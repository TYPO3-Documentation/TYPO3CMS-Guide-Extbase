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

label
~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    The name to display in the menu

:aspect:`Default value`
     NULL

:aspect:`Required`
     Yes

controller
~~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    The Controller in which the appropriate Action lies.

:aspect:`Default value`
     NULL

:aspect:`Required`
     Yes

action
~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Which Action should be called when this menu entry is selected.

:aspect:`Default value`
     NULL

:aspect:`Required`
     Yes

arguments
~~~~~~~~~
:aspect:`Variable type`
    Array

:aspect:`Description`
    Parameters to be passed to the Action.

:aspect:`Default value`
     Empty array

:aspect:`Required`
     Yes

Example
-------

The following menu contains a Select element with two menu entries. Selecting an entry calls the indicated Action within 
the indicated Controller. As you can see, you can either define the menu entry label directly, or (better) through the 
use of the `f:translate` ViewHelper.

::

 <f:be.menus.actionMenu>
   <f:be.menus.actionMenuItem label="New" controller="Fluid" action="new" />
   <f:be.menus.actionMenuItem label="{f:translate(key='List')}" controller="Fluid" action="list" />
 </f:be.menus.actionMenu>