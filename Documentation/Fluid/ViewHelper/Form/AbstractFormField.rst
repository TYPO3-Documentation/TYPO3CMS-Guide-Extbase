.. include:: ../../../Includes.txt

f:form.abstractFormField
========================

Abstract Form Field View Helper. Bundles functionality related to direct property access of objects in other Form ViewHelpers.

If you set the "property" attribute to the name of the property to resolve from the object, this class will
automatically set the name and value of a form element.

Properties
----------

name
~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Name of input tag

:aspect:`Default value`
    Empty string

:aspect:`Mandatory`
    No

value
~~~~~
:aspect:`Variable type`
    Mixed

:aspect:`Description`
    Value of input tag

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

property
~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Name of Object Property. If used in conjunction with <f:form object="...">, "name" and "value" properties will be ignored.

:aspect:`Default value`
    Empty string

:aspect:`Mandatory`
    No
