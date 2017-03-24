.. include:: ../../../../Includes.txt

f:be.menus.actionMenuItemGroup
==============================

With this ViewHelper it is possible to group some `actionMenuItem` of an `actionMenu`.

Properties
----------

label
~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    The name of the group to display in the menu

:aspect:`Default value`
    Empty string

:aspect:`Required`
    No

Example
-------

::

    <f:be.menus.actionMenu>
        <f:be.menus.actionMenuItem label="Default: Welcome" controller="Default" action="index" />
        <f:be.menus.actionMenuItem label="Community: get in touch" controller="Community" action="index" />

        <f:be.menus.actionMenuItemGroup label="Information">
            <f:be.menus.actionMenuItem label="PHP Information" controller="Information" action="listPhpInfo" />
            <f:be.menus.actionMenuItem label="Documentation" controller="Information" action="documentation" />
            <f:be.menus.actionMenuItem label="Hooks" controller="Information" action="hooks" />
            <f:be.menus.actionMenuItem label="Signals" controller="Information" action="signals" />
            <f:be.menus.actionMenuItem label="XClasses" controller="Information" action="xclass" />
        </f:be.menus.actionMenuItemGroup>
    </f:be.menus.actionMenu>
