.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

**Link for german translation**

http://docs.typo3.org/typo3cms/drafts/github/froemken/ExtbaseGuideDE/Fluid/ViewHelper/Form/Button.html

f:form.button
=============

Dieser ViewHelper erzeugt einen Button zum Absenden des Formulars.

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

 - :Property:    type
   :Datatype:    String
   :Description: Gibt den Typ des Buttons an. Mögliche Werte sind: "button", "reset" oder "submit"
   :Standard:    NULL
   :Mandatory:   No

Beispiel
--------

::

 <f:form.button>Send Mail</f:form.button>
 
::

 <f:form.button type="reset" name="buttonName" value="buttonValue" disabled="disabled" formmethod="post" formnovalidate="formnovalidate">Cancel</f:form.button>
