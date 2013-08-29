.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:form.uploads
==============

Mit diesem ViewHelper erstellst Du ein Uploadfeld, um Dateien an den Server zu senden.

Eigenschaften
-------------

.. include:: ../../UniversalFormFieldAttributes.txt

Beispiel
--------

::

 <f:form.upload name="myExtName[image]" />

oder

::

 <f:form.upload property="image" />