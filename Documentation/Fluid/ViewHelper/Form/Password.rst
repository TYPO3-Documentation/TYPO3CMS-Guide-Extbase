.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:form.password
===============

Mit diesem ViewHelper erstellst Du ein Textfeld dessen Inhalt nicht lesbar ist. Alle Zeichen werden sofort in
Sternchen umgewandelt.

Eigenschaften
-------------

.. include:: ../../UniversalFormFieldAttributes.txt

Beispiel
--------

::

 <f:form.password name="myExtName[password]" />

oder

::

 <f:form.password property="password" />