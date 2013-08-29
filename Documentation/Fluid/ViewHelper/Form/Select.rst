.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:form.select
=============

Mit diesem ViewHelper erstellt Ihr eine Selectbox.

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

 - :Property:    options
   :Datatype:    Array
   :Description: Welche Optionen sollen in der Auswahlliste erscheinen.
   :Standard:    NULL
   :Mandatory:   Ja

 - :Property:    optionValueField
   :Datatype:    String
   :Description: Wenn options Objekte enthält, dann könnt Ihr hier angeben welche Eigenschaft als zu übergebenden Wert verwendet werden soll
   :Standard:    NULL
   :Mandatory:   Ja

 - :Property:    optionLabelField
   :Datatype:    String
   :Description: Wenn options Objekte enthält, dann könnt Ihr hier angeben welche Eigenschaft als anzuzeigender Titel verwendet werden soll
   :Standard:    NULL
   :Mandatory:   Ja

 - :Property:    sortByOptionLabel
   :Datatype:    Boolean
   :Description: Soll nach dem anzuzeigenden Titel sortiert werden?
   :Standard:    FALSE
   :Mandatory:   Ja

 - :Property:    selectAllByDefault
   :Datatype:    Boolean
   :Description: Damit alle Optionen direkt vorausgewählt sind, muss das Attribut multiple und die size größer 1 gesetzt sein.
   :Standard:    FALSE
   :Mandatory:   Ja

 - :Property:    errorClass
   :Datatype:    Boolean
   :Description:
   :Standard:
   :Mandatory:   Ja

Beispiel
--------

::

 <f:form.select name="myExtName[country]" options="{data.countries}" />

oder

::

 <f:form.select property="country" options="{data.countries}" />