.. include:: ../../../../Includes.txt

f:be.buttons.shortcut
=====================

This ViewHelper provides the bookmark function used in the backend. Currently this ViewHelper is not used by the core.

Properties
----------

getVars
~~~~~~~
:aspect:`Variable type`
    Array

:aspect:`Description`
    List of GET variables to store. By default the current id, module and all module arguments will be stored.

:aspect:`Default value`
    Empty array

:aspect:`Required`
    No

setVars
~~~~~~~
:aspect:`Variable type`
    Array

:aspect:`Description`
    List of SET[] variables to store. See DocumentTemplate::makeShortcutIcon(). Normally won't be used by Extbase modules.

:aspect:`Default value`
    Empty array

:aspect:`Required`
    No

Example
-------

Default::

    <f:be.buttons.shortcut />

Explicitly set parameters to be stored in the shortcut::

    <f:be.buttons.shortcut getVars="{0: 'M', 1: 'myOwnPrefix'}" setVars="{0: 'function'}" />
