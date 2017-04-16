.. include:: ../../../../Includes.txt

f:form.select.optgroup
======================

This ViewHelper adds custom `<optgroup>` tags inside an `<f:form.select>`, it supports further
child `<f:form.select.option>` tags.

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

label
~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Human-readable label property for the generated optgroup tag.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

disabled
~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    If set to TRUE, the option group is rendered as disabled.

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No
