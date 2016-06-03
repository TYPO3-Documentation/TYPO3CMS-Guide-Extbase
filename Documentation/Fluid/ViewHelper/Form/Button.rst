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

type
~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Gibt den Typ des Buttons an. Mögliche Werte sind: "button", "reset" oder "submit"

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

Beispiel
--------

::

 <f:form.button>Send Mail</f:form.button>
 
::

 <f:form.button type="reset" name="buttonName" value="buttonValue" disabled="disabled" formmethod="post" formnovalidate="formnovalidate">Cancel</f:form.button>
