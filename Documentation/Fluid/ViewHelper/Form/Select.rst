.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:form.select
=============

This ViewHelper enables you to create a SELECT element for an HTML form.

Properties
----------

.. include:: ../../UniversalTagAttributes.txt

.. include:: ../../UniversalFormFieldAttributes.txt

Exclusive properties for the HTML-Element
#########################################

multiple
~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    When this option is selected, the website visitor can concurrently select more than one option.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

size
~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Defines the number of options which are displayed at the same time.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

disabled
~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    When this option is selected, the SELECT element is deactivated in the browser, and no options can be selected by 
    the website visitor.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

Exclusive properties of this ViewHelper
#######################################

options
~~~~~~~
:aspect:`Variable type`
    Array

:aspect:`Description`
    The options which are to be displayed in the SELECT element.

:aspect:`Default value`

:aspect:`Mandatory`
    Yes

optionValueField
~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    When the element contains options, then this property allows you to define which of the related records' properties 
    are used as the option value. (This will be sent to the server.)

:aspect:`Default value`

:aspect:`Mandatory`
    No

optionLabelField
~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    When the element contains options, then this property allows you to define which of the related records' properties 
    are used as the visible text in the SELECT element.

:aspect:`Default value`

:aspect:`Mandatory`
    No

sortByOptionLabel
~~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    Should the list of available options be sorted alphabetically, according to the visible text?

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No

selectAllByDefault
~~~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    If the `multiple` property is active and the `size` of the field is larger than 1, using this property allows you 
    to define that all of the available options are selected by default.

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No

errorClass
~~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    A CSS class name which can be assigned when the validator for this field identifies an error.

:aspect:`Default value`
    f3-form-error

:aspect:`Mandatory`
    No

prependOptionLabel
~~~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    The visible text of an additional option which will be prepended to the list.

:aspect:`Default value`

:aspect:`Mandatory`
    No

prependOptionValue
~~~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    The value of an additional option which will be prepended to the list.

:aspect:`Default value`

:aspect:`Mandatory`
    No

.. tip::

    The properties `optionValueField` and `optionLabelField` only work when using data related to an Object.


Examples
--------

::

 <f:form.select name="myExtName[country]" options="{data.countries}" />

or

::

 <f:form.select property="country" options="{data.countries}" />

