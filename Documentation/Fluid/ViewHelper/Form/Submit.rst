.. include:: ../../../Includes.txt

f:form.submit
=============

This ViewHelper has no unique properties (apart from the standard `value` property). It allows you to add a button to
an HMTL form, which submits the form when the website visitor clicks the button.

Properties
----------

All the :ref:`universal tag attributes <UniversalTagAttributes>`

All the :ref:`universal form field attributes <UniversalFormFieldAttributes>`

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

Example
-------

::

 <f:form.submit value="Send" />
