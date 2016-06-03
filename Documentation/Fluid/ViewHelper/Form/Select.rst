.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:form.select
=============

Mit diesem ViewHelper erstellt Ihr eine Selectbox.

Properties
----------

.. include:: ../../UniversalTagAttributes.txt

.. include:: ../../UniversalFormFieldAttributes.txt

Exclusive properties for the HTML-Element
#########################################

multiple
~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Wenn aktiviert, dann können mehrere Optionen gleichzeitig gewählt werden. In diesem Falle macht es
                 Sinn den Wert size auf >=3 zu setzen.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

size
~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Die Größe der Selectbox. Wie viele Optionen sollen gleichzeitig angezeigt werden?

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

disabled
~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Wenn aktiviert, dann ist die Selectbox beim Laden des Formulars deaktiviert.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

Exclusive properties of this ViewHelper
#######################################

options
~~~~~~~
:aspect:`Variable type`
    Array

:aspect:`Description`
    Welche Optionen sollen in der Auswahlliste erscheinen.

:aspect:`Default value`

:aspect:`Mandatory`
    Yes

optionValueField
~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Wenn options Objekte enthält, dann könnt Ihr hier angeben welche Eigenschaft als zu übergebenden Wert verwendet werden soll

:aspect:`Default value`

:aspect:`Mandatory`
    No

optionLabelField
~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Wenn options Objekte enthält, dann könnt Ihr hier angeben welche Eigenschaft als anzuzeigender Titel verwendet werden soll

:aspect:`Default value`

:aspect:`Mandatory`
    No

sortByOptionLabel
~~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    Soll nach dem anzuzeigenden Titel sortiert werden?

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No

selectAllByDefault
~~~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    Damit alle Optionen direkt vorausgewählt sind, muss das Attribut multiple und die size größer 1 gesetzt sein.

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No

errorClass
~~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Eine CSS-Klasse, die gesetzt werden soll, wenn der Validator für dieses Feld einen Fehler
                 gemeldet hat.

:aspect:`Default value`
    f3-form-error

:aspect:`Mandatory`
    No

prependOptionLabel
~~~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Erzeugt eine weitere Option ganz am Anfang der Auflistung mit dem angegebenen Text.

:aspect:`Default value`

:aspect:`Mandatory`
    No

prependOptionValue
~~~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Erzeugt eine weitere Option ganz am Anfang der Auflistung mit dem angegebenen Wert.

:aspect:`Default value`

:aspect:`Mandatory`
    No

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

