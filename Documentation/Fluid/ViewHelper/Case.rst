.. include:: ../../Includes.txt

======
f:case
======

This ViewHelper is part of the use case for `f:switch`. Where the value of
this tag matches the value in the `f:switch` tag, the content of this tag
will be rendered and output.

Properties
==========

Exclusive properties of this ViewHelper:


value
-----

:aspect:`Variable type`
   Mixed

:aspect:`Description`
   The value against which the value from the `f:switch` ViewHelper should be compared.

:aspect:`Mandatory`
   Yes


Example
=======

See the example for the :ref:`viewhelper 'switch' <viewhelper-switch>`.


Deprecation
===========

The usage of this ViewHelper for the default case in the following manner
is deprecated and will be removed in TYPO3 v9. Use `DefaultCaseViewHelper` instead.

.. highlight:: xml

Old, deprecated::

   <f:case default="TRUE">Foo</f:case>

New::

   <f:defaultCase>Foo</f:defaultCase>
