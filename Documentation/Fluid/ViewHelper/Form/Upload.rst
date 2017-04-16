.. include:: ../../../Includes.txt

f:form.upload
=============

This ViewHelper allows you to add an HTML file upload field to an HTML form, which allows the website user to upload a
file to the web server.

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

multiple
~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Specifies that the file input element should allow multiple selection of files.

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


Examples
--------

::

 <f:form.upload name="myExtName[image]" />


or

::

 <f:form.upload property="image" />
