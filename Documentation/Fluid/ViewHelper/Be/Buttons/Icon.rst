.. include:: ../../../../Includes.txt

f:be.buttons.icon
=================

With this ViewHelper, you can generate small linked icons like edit, delete and new, as well as a range of others.

Features
--------

uri
~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Target url. Can be created by a `f:uri.*`-ViewHelper.

:aspect:`Default value`
    NULL

:aspect:`Required`
    No

title
~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Title attribute for the link.

:aspect:`Default value`
    empty string

:aspect:`Required`
    No

icon
~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    The name to use.

:aspect:`Default value`
    actions-document-close

:aspect:`Required`
    No


There is a predefined set of possible values for the icon parameter. If you're not sure what they are, try inserting 
a deliberately invalid value. The resultant error message will give you a list of all valid values, for example::

 "foo" is not a valid icon. Allowed are: "add", "add_workspace", "button_down", "button_hide", "button_left", "button_unhide", "button_right", "button_up", "clear_cache", "clip_copy", "clip_cut", "clip_pasteafter", "closedok", "datepicker", "deletedok", "edit2", "helpbubble", "icon_fatalerror", "icon_note", "icon_ok", "icon_warning", "new_el", "options", "perm", "refresh_n", "saveandclosedok", "savedok", "savedoknew", "savedokshow", "viewdok", "zoom".


Example
-------

In combination with an `f:uri.action` ViewHelper providing the target url.

::

 <f:be.buttons.icon uri="{f:uri.action(action:'new')}" icon="button_unhide" />

