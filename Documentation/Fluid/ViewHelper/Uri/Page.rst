.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:uri.page
==========

Eigenschaften
-------------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Eigenschaft
   :Datatype,20:    Datentyp
   :Description,40: Beschreibung
   :Standard,10:    Default value
   :Mandatory,10:   Mandatory

 - :Property:    pageUid
   :Datatype:    Integer|NULL
   :Description: Auf welche Seiten-UID soll verlinkt werden
   :Standard:    NULL
   :Mandatory:   Nein

 - :Property:    additionalParams
   :Datatype:    Array
   :Description: Fügt weitere Parameter der Zielseite an. Im Gegensatz zu arguments, können hiermit Variablen hinzugefügt werden die nicht mit dem Extensionnamen geprefixed werden.
   :Standard:    Leeres Array
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

 - :Property:    linkAccessRestrictedPages
   :Datatype:    Boolean
   :Description: Normalerweise werden Links auf geschützte Seiten nicht erzeugt. Hier mit kann man die Linkgeneration erzwingen.
   :Standard:    FALSE
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