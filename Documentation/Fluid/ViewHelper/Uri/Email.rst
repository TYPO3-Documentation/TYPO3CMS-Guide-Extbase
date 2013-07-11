.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:uri.email
===========

Mit diesem ViewHelper erstellt Ihr einen Link auf eine E-Mail-Adresse. Falls Ihr mit TypoScript im Bereich "config"
Angaben zum Verschlüsseln der E-Mail-Adresse gemacht habt, so werden diese Einstellungen auch hier angewendet.

Eigenschaften
-------------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Eigenschaft
   :Datatype,20:    Datentyp
   :Description,40: Beschreibung
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    email
   :Datatype:    String
   :Description: Die zu verlinkende E-Mail-Adresse
   :Standard:
   :Mandatory:   Ja

Beispiel
--------

<f:link.email email="meine@mailadresse.tld" />
