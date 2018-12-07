.. include:: ../../Includes.txt

f:variable
===========

Assigns one template variable which will exist also after the ViewHelper is done rendering, i.e. adds template variables.

If you require a variable assignment which does not exist in the template after a piece of Fluid code is rendered, consider using `f:alias` instead.

Properties
----------

name
~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Name of variable to create

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    Yes

value
~~~~~~~
:aspect:`Variable type`
    Mixed

:aspect:`Description`
   Value to assign. If not in arguments then taken from tag content

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

Examples
--------

Tag notation
~~~~~~~~~~~~

::

 <f:variable name="myvariable" value="some value" />

Tag notation II
~~~~~~~~~~~~~~~

::

 <f:variable name="myvariable">some value</f:variable>

Inline notation
~~~~~~~~~~~~~~~

::

 {f:variable(name: 'myvariable', value: 'some value')}

Inline notation II
~~~~~~~~~~~~~~~~~~

::

 {oldvariable -> f:format.htmlspecialchars() -> f:variable(name: 'newvariable')}

Simple math
~~~~~~~~~~~

::

 {f:variable(name: 'mycount', value: 0)}
 {mycount}

> Outout is "0"

::

 {f:variable(name: 'mycount', value: '{mycount + 1}')}
 {mycount}

> Outout is now "1"
