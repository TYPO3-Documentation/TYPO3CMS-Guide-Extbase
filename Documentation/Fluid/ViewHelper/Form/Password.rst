.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:form.password
===============

This ViewHelper allows you to create a field in an HTML form, whose content is optically masked by the browser. (e.g. 
the value in the field is replaced by a series of star characters.

Properties
----------

.. include:: ../../UniversalTagAttributes.txt

.. include:: ../../UniversalFormFieldAttributes.txt

Examples
--------

::

 <f:form.password name="myExtName[password]" />

or

::

 <f:form.password property="password" />