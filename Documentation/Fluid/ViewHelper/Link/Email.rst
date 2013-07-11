.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:link.email
============

Mit diesem ViewHelper erstellt Ihr einen Link auf eine E-Mail-Adresse. Falls Ihr mit TypoScript im Bereich "config"
Angaben zum Verschlüsseln der E-Mail-Adresse gemacht habt, so werden diese Einstellungen auch hier angewendet.

Eigenschaften
-------------

.. include:: ../../UniversalTagAttributes.txt

Eigenschaften speziell für das HTML-Element
###########################################

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Eigenschaft
   :Datatype,20:    Datentyp
   :Description,40: Beschreibung
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    name
   :Datatype:    String
   :Description: Der name des Links
   :Standard:    NULL
   :Mandatory:   Nein

 - :Property:    rel
   :Datatype:    String
   :Description: Gibt die Beziehung zwischen dem aktuellen Dokument und dem verknüpften Dokument an
   :Standard:    NULL
   :Mandatory:   Nein

 - :Property:    rev
   :Datatype:    String
   :Description: Gibt die Beziehung zwischen dem verknüpften Dokument und dem aktuellen Dokument an
   :Standard:    NULL
   :Mandatory:   Nein

 - :Property:    target
   :Datatype:    String
   :Description: In welchem Fenster soll der Link geöffnet werden?
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

 - :Property:    email
   :Datatype:    String
   :Description: Die zu verlinkende E-Mail-Adresse
   :Standard:
   :Mandatory:   Ja

Beispiel
--------

::

 <f:link.email email="meine@mailadresse.tld" />
