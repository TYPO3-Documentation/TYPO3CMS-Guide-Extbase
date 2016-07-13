.. include:: ../../../Includes.txt

f:format.raw
============

By default, variable contents are escaped when emitted within a fluid template. This prevents dangerous HTML/JavaScript ("XSS") within user-specified content. If you are certain that contents of a variable can be shown as-is, you can use the `f:format.raw` ViewHelper.

Properties
----------

value
~~~~~
:aspect:`Variable type`
    Mixed

:aspect:`Description`
    Text that shall not be escaped. Most useful when you reference a variable here.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

Example
--------

::

 <f:format.raw value="{formData.signature}" />
