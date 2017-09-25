.. include:: ../../../Includes.txt

f:form.textfield
================

This ViewHelper allows you to create a simple text input field.

Properties
----------

All the :ref:`universal tag attributes <UniversalTagAttributes>`

All the :ref:`universal form field attributes <UniversalFormFieldAttributes>`

Exclusive properties of this ViewHelper
#######################################

autofocus
~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Specifies that an input should automatically get focus when the page loads.

:aspect:`Default value`
    Empty string

:aspect:`Mandatory`
    No

disabled
~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Specifies that the input element should be disabled when the page loads.

:aspect:`Default value`
    Empty string

:aspect:`Mandatory`
    No

maxlength
~~~~~~~~~
:aspect:`Variable type`
    Int

:aspect:`Description`
    The maxlength attribute of the input field (will not be validated).

:aspect:`Default value`
    0

:aspect:`Mandatory`
    No

readonly
~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    The readonly attribute of the input field.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

size
~~~~
:aspect:`Variable type`
    Int

:aspect:`Description`
    The size of the input field.

:aspect:`Default value`
    0

:aspect:`Mandatory`
    No

placeholder
~~~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    A helpful, short piece of text, which disappears when a value is entered to the field.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

pattern
~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    HTML validation pattern.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

errorClass
~~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    CSS class to set if there are errors for this view helper.

:aspect:`Default value`
    f3-form-error

:aspect:`Mandatory`
    No

required
~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    If this property is used, then the field is marked as being obligatory, so that a third party or browser-embedded
    validator can be appropriately implemented.

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No

type
~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    The usual type is “text”, but several other types are available under the HTML5 definition. For example, `url`,
    `email`, `date`.

:aspect:`Default value`
    text

:aspect:`Mandatory`
    No

Examples
--------

::

 <f:form.textfield property="address" />


or

::

 <f:form.textfield name="myExtName[address]" />
 <f:form.textfield name="myExtName[email]" type="email" required="TRUE" />

