.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:form.textfield
================

Mit diesem ViewHelper erstellt Ihr ein Textfeld.

Eigenschaften
-------------

.. include:: ../../UniversalTagAttributes.txt

.. include:: ../../UniversalFormFieldAttributes.txt

Eigenschaften speziell für diesen ViewHelper
############################################

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Property
   :Datatype,20:    Variable type
   :Description,40: Description
   :Standard,10:    Default value
   :Mandatory,10:   Mandatory

 - :Property:    required
   :Datatype:    Boolean
   :Description: Wenn aktiviert, dann handelt es sich um ein Pflichtfeld
   :Standard:    NULL
   :Mandatory:   No

 - :Property:    type
   :Datatype:    String
   :Description: Als Alternative gibt es noch email, url
   :Standard:    text
   :Mandatory:   No

 - :Property:    placeholder
   :Datatype:    String
   :Description: Ein beliebiger Text, der verschwindet, sobald in dieses Feld reingeklickt wird.
   :Standard:    NULL
   :Mandatory:   No

Beispiel
--------

::

 <f:form.textfield name="myExtName[strasse]" />

oder

::

 <f:form.textfield property="strasse" />