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

checked
~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    Wenn aktiviert, dann gilt diese Checkbox als markiert.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

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