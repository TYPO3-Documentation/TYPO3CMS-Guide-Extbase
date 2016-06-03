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

 - :Property:    email
:aspect:`Variable type`
    String

:aspect:`Description`
    Die zu verlinkende E-Mail-Adresse
   :Standard:

:aspect:`Mandatory`
    Yes

Beispiel
--------

{f:uri.email(email: 'meine@mailadresse.tld')}
