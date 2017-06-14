.. include:: ../../Includes.txt

f:case
======

This ViewHelper is part of the use case for `f:switch`. Where the value of this tag matches the value in the `f:switch` 
tag, the content of this tag will be rendered and output.

Properties
----------

Exclusive properties of this ViewHelper
#######################################

value
~~~~~
:aspect:`Variable type`
    Mixed

:aspect:`Description`
    The value against which the value from the `f:switch` ViewHelper should be compared.

:aspect:`Default value`

:aspect:`Mandatory`
    Yes

Example
--------

A example of the usage of the `f:case` ViewHelper is in the documentation for the `f:switch` ViewHelper.

Deprecation
--------

The usage of this ViewHelper as default case like below is deprecated and will be removed in TYPO3 v9.*.
Use DefaultCaseViewHelper instead.

Old:
::
    <f:case default="TRUE">Foo</f:case>

New:
::
    <f:defaultCase>Foo</f:defaultCase>
