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

 - :Property:    multiple
   :Datatype:    String
   :Description: Wenn aktiviert, dann können mehrere Optionen gleichzeitig gewählt werden. In diesem Falle macht es
                 Sinn den Wert size auf >=3 zu setzen.
   :Standard:    NULL
   :Mandatory:   Nein

 - :Property:    size
   :Datatype:    String
   :Description: Die Größe der Selectbox. Wie viele Optionen sollen gleichzeit angezeigt werden?
   :Standard:    NULL
   :Mandatory:   Nein

 - :Property:    disabled
   :Datatype:    String
   :Description: Wenn aktiviert, dann ist die Selectbox beim Laen des Formulars deaktiviert.
   :Standard:    NULL
   :Mandatory:   Nein

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
   :Standard:
   :Mandatory:   Ja

 - :Property:    optionValueField
   :Datatype:    String
   :Description: Wenn options Objekte enthält, dann könnt Ihr hier angeben welche Eigenschaft als zu übergebenden Wert verwendet werden soll
   :Standard:
   :Mandatory:   Nein

 - :Property:    optionLabelField
   :Datatype:    String
   :Description: Wenn options Objekte enthält, dann könnt Ihr hier angeben welche Eigenschaft als anzuzeigender Titel verwendet werden soll
   :Standard:
   :Mandatory:   Nein

 - :Property:    sortByOptionLabel
   :Datatype:    Boolean
   :Description: Soll nach dem anzuzeigenden Titel sortiert werden?
   :Standard:    FALSE
   :Mandatory:   Nein

 - :Property:    selectAllByDefault
   :Datatype:    Boolean
   :Description: Damit alle Optionen direkt vorausgewählt sind, muss das Attribut multiple und die size größer 1 gesetzt sein.
   :Standard:    FALSE
   :Mandatory:   Nein

 - :Property:    errorClass
   :Datatype:    String
   :Description: Eine CSS-Klasse, die gesetzt werden soll, wenn der Validator für dieses Feld einen Fehler
                 gemeldet hat.
   :Standard:    f3-form-error
   :Mandatory:   Nein

 - :Property:    prependOptionLabel
   :Datatype:    String
   :Description: Erzeugt eine weitere Option ganz am Anfang der Auflistung mit dem angegebenen Text.
   :Standard:
   :Mandatory:   Nein

 - :Property:    prependOptionValue
   :Datatype:    String
   :Description: Erzeugt eine weitere Option ganz am Anfang der Auflistung mit dem angegebenen Wert.
   :Standard:
   :Mandatory:   Nein

.. tip::

   Die Eigenschaften optionValueField und optionLabelField funktionieren nur, wenn es sich bei den Daten für eine
   Option, um ein Objekt handelt.

.. tip::

   Die Eigenschaften selectAllByDefault klappt nur, wenn auch die Eigenschaft multiple gesetzt ist.

Beispiel
--------

::

 <f:form.select name="myExtName[country]" options="{data.countries}" />

oder

::

 <f:form.select property="country" options="{data.countries}" />

