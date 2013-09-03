.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../Includes.txt

Arraynotation
-------------

In TYPO3 6.1

* Allow Fluid arrays only in ViewHelper arguments

Fluid arrays are a subset of the JavaScript object syntax, making it hard to
work with them in mixed HTML/JavaScript documents. For example the following
JavaScript Object was parsed by Fluid::

 var uris = {
   endPoint1: '{f:uri.action(.)}',
   endPoint2: '{f:uri.action(.)}',
 };

With 6.1, Fluid now only parses arrays which are used inside ViewHelper
arguments, such that an array inside normal text is not converted anymore.
This change is only breaking in very rare cases where one relied on the inner
contents of the ViewHelper being an array, eg. if one used the debug
ViewHelper as follows::

 <f:debug>{key1: 'value1', key2: 'value2'}</f:debug>

ViewHelpers which were written like this should be re-written to take the array
as ViewHelper argument::

 <f:debug value="{key1: 'value1', key2: 'value2'}" />
