.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:form.radio
============

This ViewHelper allows you to create a radio button element for use in an HTML form. Radio button fields are usually 
used in groups, and only a single radio button in a group may be active at one time. A multiple selection - like the one 
we see when using checkboxes - isn't possible with radio buttons.

Properties
----------

.. include:: ../../UniversalTagAttributes.txt

.. include:: ../../UniversalFormFieldAttributes.txt

Exclusive properties for the HTML-Element
#########################################

checked
~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    When active, the radio button field will appear in a checked (active) state.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

Examples
--------

::

 <f:form.radio name="myExtName[age]" value="1-10" />
 <f:form.radio name="myExtName[age]" value="11-40" />
 <f:form.radio name="myExtName[age]" value="41-99" />

or

::

 <f:form.radio property="age" value="1-10" />
 <f:form.radio property="age" value="11-40" />
 <f:form.radio property="age" value="41-99" />