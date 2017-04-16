.. include:: ../../../../Includes.txt

f:form.select.option
====================

This ViewHelper adds custom `<option>` tags inside an `<f:form.select>`.

Properties
----------

additionalAttributes
~~~~~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    Array

:aspect:`Description`
    Additional tag attributes. They will be added directly to the resulting HTML tag.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

data
~~~~
:aspect:`Variable type`
    Array

:aspect:`Description`
    Additional data-* attributes. They will each be added with a "data-" prefix.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

value
~~~~~
:aspect:`Variable type`
    Mixed

:aspect:`Description`
    Value to be inserted in HTML tag - must be convertible to string!

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

selected
~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    If set to TRUE, overrides automatic detection of selected state for this option.

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No
