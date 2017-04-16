.. include:: ../../../Includes.txt

f:form.textarea
===============

This ViewHelper allows you to add a TEXTAREA (text input field) to an HTML form, which allows a website visitor to enter
text on multiple lines. For example, this type of field is usually seen in a contact form, where the website visitor
can enter the text of his or her message.
The value of the text area needs to be set via the "value" attribute, as with all other form ViewHelpers.

Properties
----------

All the :ref:`universal tag attributes <UniversalTagAttributes>`

All the :ref:`universal form field attributes <UniversalFormFieldAttributes>`

autofocus
~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Specifies that a text area should automatically get focus when the page loads.

:aspect:`Default value`
    Empty string

:aspect:`Mandatory`
    No

rows
~~~~
:aspect:`Variable type`
    Int

:aspect:`Description`
    The number of rows of a text area.

:aspect:`Default value`
    0

:aspect:`Mandatory`
    No

cols
~~~~
:aspect:`Variable type`
    Int

:aspect:`Description`
    The number of columns of a text area.

:aspect:`Default value`
    0

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

placeholder
~~~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    The placeholder of the textarea.

:aspect:`Default value`
    Empty string

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

Examples
--------

::

 <f:form.textarea name="myExtName[message]" />


or

::

 <f:form.textarea property="message" />
