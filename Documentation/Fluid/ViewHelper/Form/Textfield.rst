.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:form.textfield
================

This ViewHelper allows you to create a simple text input field.

Properties
----------

.. include:: ../../UniversalTagAttributes.txt

.. include:: ../../UniversalFormFieldAttributes.txt

Exclusive properties of this ViewHelper
#######################################

required
~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    If this property is used, then the field is marked as being obligatory, so that a third party or browser-embedded 
    validator can be appropriately implemented.

:aspect:`Default value`
    NULL

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

Examples
--------

::

 <f:form.textfield property="address" />

or

::

 <f:form.textfield name="myExtName[address]" />
 <f:form.textfield name="myExtName[email]" type="email" required="TRUE" />

