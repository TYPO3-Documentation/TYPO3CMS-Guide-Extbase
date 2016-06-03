.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:form.textfield
================

Mit diesem ViewHelper erstellt Ihr ein Textfeld.

Properties
----------

.. include:: ../../UniversalTagAttributes.txt

.. include:: ../../UniversalFormFieldAttributes.txt

Exclusive properties of this ViewHelper
#######################################

required
~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    Wenn aktiviert, dann handelt es sich um ein Pflichtfeld

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

type
~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Als Alternative gibt es noch email, url

:aspect:`Default value`
    text

:aspect:`Mandatory`
    No

placeholder
~~~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Ein beliebiger Text, der verschwindet, sobald in dieses Feld reingeklickt wird.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

Beispiel
--------

::

 <f:form.textfield name="myExtName[strasse]" />

oder

::

 <f:form.textfield property="strasse" />