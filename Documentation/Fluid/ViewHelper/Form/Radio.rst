.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:form.radio
============

Mit diesem ViewHelper erstellst Du einen Radiobutton. Normalerweise tauchen diese immer in Gruppen auf und bieten dem
Besucher an sich für EINE Möglichkeit zu entscheiden. Eine Mehrfachauswahl wie bei den Checkboxen ist hier nicht
möglich.

Properties
----------

.. include:: ../../UniversalTagAttributes.txt

.. include:: ../../UniversalFormFieldAttributes.txt

Exclusive properties for the HTML-Element
#########################################

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Property
   :Datatype,20:    Variable type
   :Description,40: Description
   :Standard,10:    Default value
   :Mandatory,10:   Mandatory

 - :Property:    checked
   :Datatype:    Boolean
   :Description: Wenn aktiviert, dann gilt diese Checkbox als markiert.
   :Standard:    NULL
   :Mandatory:   No

Beispiel
--------

::

 <f:form.radio name="myExtName[age]" value="1-10" />
 <f:form.radio name="myExtName[age]" value="11-40" />
 <f:form.radio name="myExtName[age]" value="41-99" />

oder

::

 <f:form.radio property="age" value="1-10" />
 <f:form.radio property="age" value="11-40" />
 <f:form.radio property="age" value="41-99" />