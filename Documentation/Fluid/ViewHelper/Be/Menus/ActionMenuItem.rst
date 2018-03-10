.. include:: ../../../../Includes.txt

=========================
f:be.menus.actionMenuItem
=========================

You can use this ViewHelper to create a menu entry for your backend module. For
this to work, the call to this ViewHelper must be placed within a
`f:be.menus.actionMenu` ViewHelper.

Properties
==========

.. rst-class:: dl-parameters

label
   :sep:`|` :aspect:`Condition:`  required
   :sep:`|` :aspect:`Type:`       string
   :sep:`|` :aspect:`Default:`    null
   :sep:`|`

   The name to display in the menu


controller
   :sep:`|` :aspect:`Condition:`  required
   :sep:`|` :aspect:`Type:`       string
   :sep:`|` :aspect:`Default:`    null
   :sep:`|`

   The Controller in which the appropriate Action lies.


action
   :sep:`|` :aspect:`Condition:`  required
   :sep:`|` :aspect:`Type:`       string
   :sep:`|` :aspect:`Default:`    null
   :sep:`|`

   Which Action should be called when this menu entry is selected.


arguments
~~~~~~~~~
   :sep:`|` :aspect:`Condition:`  required
   :sep:`|` :aspect:`Type:`       array
   :sep:`|` :aspect:`Default:`    empty array
   :sep:`|`

   Parameters to be passed to the Action.


Example
=======

The following menu contains a Select element with two menu entries. Selecting
an entry calls the indicated Action within the indicated Controller. As you can
see, you can either define the menu entry label directly, or (better) through
the use of the `f:translate` ViewHelper.

::

   <f:be.menus.actionMenu>
      <f:be.menus.actionMenuItem label="New" 
                                 controller="Fluid" 
                                 action="new" />
      <f:be.menus.actionMenuItem label="{f:translate(key='List')}" 
                                 controller="Fluid" 
                                 action="list" />
    </f:be.menus.actionMenu>
