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
   :Standard,10:    Default value
   :Mandatory,10:   Mandatory

 - :Property:    type
   :Datatype:    String
   :Description: Gibt den Typ des Buttons an. Mögliche Werte sind: "button", "reset" oder "submit"
   :Standard:    NULL
   :Mandatory:   Nein

Beispiel
--------

::

 <f:form.button>Send Mail</f:form.button>
 
::

 <f:form.button type="reset" name="buttonName" value="buttonValue" disabled="disabled" formmethod="post" formnovalidate="formnovalidate">Cancel</f:form.button>
