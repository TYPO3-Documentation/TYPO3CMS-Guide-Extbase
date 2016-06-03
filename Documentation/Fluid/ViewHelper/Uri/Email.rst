.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:uri.email
===========

Mit diesem ViewHelper erstellt Ihr einen Link auf eine E-Mail-Adresse. Falls Ihr mit TypoScript im Bereich "config"
Angaben zum Verschlüsseln der E-Mail-Adresse gemacht habt, so werden diese Einstellungen auch hier angewendet.

Properties
----------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Property
   :Datatype,20:    Variable type
   :Description,40: Description
   :Standard,10:    Default value
   :Mandatory,10:   Mandatory

 - :Property:    email
   :Datatype:    String
   :Description: Die zu verlinkende E-Mail-Adresse
   :Standard:
   :Mandatory:   Yes

Beispiel
--------

{f:uri.email(email: 'meine@mailadresse.tld')}
