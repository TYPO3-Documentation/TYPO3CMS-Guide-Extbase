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

Eigenschaften
-------------

.. include:: ../../UniversalTagAttributes.txt

.. include:: ../../UniversalFormFieldAttributes.txt

Eigenschaften speziell für das HTML-Element
###########################################

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Eigenschaft
   :Datatype,20:    Datentyp
   :Description,40: Beschreibung
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    checked
   :Datatype:    Boolean
   :Description: Wenn aktiviert, dann gilt diese Checkbox als markiert.
   :Standard:    NULL
   :Mandatory:   Nein

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