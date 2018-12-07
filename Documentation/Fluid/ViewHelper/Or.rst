.. include:: ../../Includes.txt

f:or
====

If `content` is null/undefined use the text that's provided as `alternative`.

Properties
----------

content
~~~~~~~
:aspect:`Variable type`
    Mixed

:aspect:`Description`
    Content to check if null/undefined

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

alternative
~~~~~~~~~~~
:aspect:`Variable type`
    Mixed

:aspect:`Description`
    Alternative if content is null/undefined

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

arguments
~~~~~~~~~
:aspect:`Variable type`
    Array

:aspect:`Description`
    Arguments to be replaced in the resulting string, using sprintf

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

Examples
--------

Tag notation
~~~~~~~~~~~~

::

 <f:or alternative="some text">{undefinedVariable}</f:or>

Inline notation
~~~~~~~~~~~~~~~

::

 {f:or(content:undefinedVariable, alternative:'some other string')}

Inline notation II
~~~~~~~~~~~~~~~~~~

::

 {undefinedVariable -> f:or(alternative:'some %s text', arguments:{0: 'test'})}

Hint
----

Please keep in mind that `f:or` is checking on null/undefined and *not* on whether the content is "empty" or not.

For checking on "empty" it's possible to simply use the ternary operator as show in the following example:

::

 {undefinedVariable ? undefinedVariable : 'alternative string'}
