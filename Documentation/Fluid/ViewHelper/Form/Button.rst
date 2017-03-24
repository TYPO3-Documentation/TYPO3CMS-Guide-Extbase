.. include:: ../../../Includes.txt

f:form.button
=============

This ViewHelper creates a button element in a form, for example the one which allows the form to be submitted.

Properties
----------

All the :ref:`universal tag attributes <UniversalTagAttributes>`

All the :ref:`universal form field attributes <UniversalFormFieldAttributes>`

Exclusive properties for the HTML-Element
#########################################

type
~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    The type of button to create. Allowed options are "button", "reset" and "submit"

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

Examples
--------

::

 <f:form.button>Send Mail</f:form.button>


::

 <f:form.button type="reset" name="buttonName" value="buttonValue" disabled="disabled" formmethod="post" formnovalidate="formnovalidate">Cancel</f:form.button>
