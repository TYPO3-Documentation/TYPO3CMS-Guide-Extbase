.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:link.action
=============

Dieser ViewHelper erstellt einen Link zu einer anderen aufzurufenden Action

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
   :Standard,10:    Default value
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
   :Standard,10:    Default value
   :Mandatory,10:   Mandatory

 - :Property:    action
   :Datatype:    String
   :Description: Auf welche Actionmethode soll der Link zeigen
   :Standard:    NULL
   :Mandatory:   Nein

 - :Property:    arguments
   :Datatype:    Array
   :Description: Welche Argumente/Parameter sollen dem Link angehängt werden
   :Standard:    Leeres Array
   :Mandatory:   Nein

 - :Property:    controller
   :Datatype:    String
   :Description: Auf welchen Controller soll der Link zeigen
   :Standard:    NULL
   :Mandatory:   Nein

 - :Property:    extensionName
   :Datatype:    String
   :Description: Auf welchen Controller und/oder Action welcher Extension soll der Link zeigen
   :Standard:    NULL
   :Mandatory:   Nein

 - :Property:    pluginName
   :Datatype:    String
   :Description: Auf welchen Controller und/oder Action welchen Plugins soll der Link zeigen
   :Standard:    NULL
   :Mandatory:   Nein

 - :Property:    pageUid
   :Datatype:    Integer
   :Description: Auf welche Seiten-UID soll verlinkt werden
   :Standard:    NULL
   :Mandatory:   Nein

 - :Property:    pageType
   :Datatype:    Integer
   :Description: Auf welche Seitentyp ID soll verlinkt werden.
   :Standard:    0
   :Mandatory:   Nein

 - :Property:    noCache
   :Datatype:    Boolean
   :Description: Verhindert das Caching der aufzurufenden Seite
   :Standard:    FALSE
   :Mandatory:   Nein

 - :Property:    noCacheHash
   :Datatype:    Boolean
   :Description: Verhindert, dass der cHash-Parameter nicht mit an die URL angehangen wird.
   :Standard:    FALSE
   :Mandatory:   Nein

 - :Property:    section
   :Datatype:    String
   :Description: Auf welchen Anker soll die Zielseite springen (#anker)
   :Standard:    Leerer String
   :Mandatory:   Nein

 - :Property:    format
   :Datatype:    String
   :Description: Gibt an um welches Format es sich bei der Zielseite handelt. Alternativ gibt es noch "xml"
   :Standard:    Leerer String
   :Mandatory:   Nein

 - :Property:    linkAccessRestrictedPages
   :Datatype:    Boolean
   :Description: Normalerweise werden Links auf geschützte Seiten nicht erzeugt. Hier mit kann man die Linkgeneration erzwingen.
   :Standard:    FALSE
   :Mandatory:   Nein

 - :Property:    additionalParams
   :Datatype:    Array
   :Description: Fügt weitere Parameter der Zielseite an. Im Gegensatz zu arguments, können hiermit Variablen hinzugefügt werden die nicht mit dem Extensionnamen geprefixed werden.
   :Standard:    Leeres Array
   :Mandatory:   Nein

 - :Property:    absolute
   :Datatype:    Boolean
   :Description: Nach Aktivierung wird der Zeilseite noch der Domainname und Pfad vorangestellt.
   :Standard:    FALSE
   :Mandatory:   Nein

 - :Property:    addQueryString
   :Datatype:    Boolean
   :Description: Falls der aktuellen Seite bereits Parameter über die URL mitgegeben wurden, könnt Ihr hier nun entscheiden, ob diese Parameter auch mit auf die Zielseite übergeben werden.
   :Standard:    FALSE
   :Mandatory:   Nein

 - :Property:    argumentsToBeExcludedFromQueryString
   :Datatype:    Array
   :Description: Falls Ihr addQueryString aktiviert habt, aber einen oder zwei bestimmte Parameter wieder entfernen wollt, dann tragt Ihr hier diese Parameter ein.
   :Standard:    Leeres Array
   :Mandatory:   Nein

Beispiel
--------

::

 <f:link.action action="show">Zeige Details</f:link.action>
