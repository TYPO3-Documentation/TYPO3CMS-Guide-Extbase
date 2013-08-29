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

.. include:: ../../UniversalFormFieldAttributes.txt

Eigenschaften speziell für diesen ViewHelper
############################################

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Eigenschaft
   :Datatype,20:    Datentyp
   :Description,40: Beschreibung
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    required
   :Datatype:    Boolean
   :Description: Wenn aktiviert, dann handelt es sich um ein Pflichtfeld
   :Standard:    NULL
   :Mandatory:   Nein

 - :Property:    type
   :Datatype:    String
   :Description: Als Alternative gibt es noch email, url
   :Standard:    text
   :Mandatory:   Nein

 - :Property:    placeholder
   :Datatype:    String
   :Description: Ein beliebiger Text, der verschwindet, sobald in dieses Feld reingeklickt wird.
   :Standard:    NULL
   :Mandatory:   Nein

Beispiel
--------

::

 <f:form.textfield name="myExtName[strasse]" />

oder

::

 <f:form.textfield property="strasse" />