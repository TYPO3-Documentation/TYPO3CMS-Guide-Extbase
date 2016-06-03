.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:link.page
===========

Dieser ViewHelper erstellt einen Link zu einer anderen Seiten-UID

Properties
----------

.. include:: ../../UniversalTagAttributes.txt

Exclusive properties for the HTML-Element
#########################################

 - :Property:    target
:aspect:`Variable type`
    String

:aspect:`Description`
    In welchem Fenster soll der Link geöffnet werden?

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

 - :Property:    rel
:aspect:`Variable type`
    String

:aspect:`Description`
    Gibt die Beziehung zwischen dem aktuellen Dokument und dem verknüpften Dokument an

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

Exclusive properties of this ViewHelper
#######################################

 - :Property:    pageUid
:aspect:`Variable type`
    Integer|NULL

:aspect:`Description`
    Auf welche Seiten-UID soll verlinkt werden

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

 - :Property:    additionalParams
:aspect:`Variable type`
    Array

:aspect:`Description`
    Fügt weitere Parameter der Zielseite an. Im Gegensatz zu arguments, können hiermit Variablen hinzugefügt werden die nicht mit dem Extensionnamen geprefixed werden.

:aspect:`Default value`
    Leeres Array

:aspect:`Mandatory`
    No

 - :Property:    pageType
:aspect:`Variable type`
    Integer

:aspect:`Description`
    Auf welche Seitentyp ID soll verlinkt werden.

:aspect:`Default value`
    0

:aspect:`Mandatory`
    No

 - :Property:    noCache
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    Verhindert das Caching der aufzurufenden Seite

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No

 - :Property:    noCacheHash
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    Verhindert, dass der ``cHash``-Parameter mit an die URL angehangen wird.

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No

 - :Property:    section
:aspect:`Variable type`
    String

:aspect:`Description`
    Auf welchen Anker soll die Zielseite springen (#anker)

:aspect:`Default value`
    Leerer String

:aspect:`Mandatory`
    No

 - :Property:    linkAccessRestrictedPages
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    Normalerweise werden Links auf geschützte Seiten nicht erzeugt. Hier mit kann man die Linkgeneration erzwingen.

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No

 - :Property:    absolute
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    Nach Aktivierung wird der Zeilseite noch der Domainname und Pfad vorangestellt.

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No

 - :Property:    addQueryString
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    Falls der aktuellen Seite bereits Parameter über die URL mitgegeben wurden, könnt Ihr hier nun entscheiden, ob diese Parameter auch mit auf die Zielseite übergeben werden.

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No

 - :Property:    argumentsToBeExcludedFromQueryString
:aspect:`Variable type`
    Array

:aspect:`Description`
    Falls Ihr addQueryString aktiviert habt, aber einen oder zwei bestimmte Parameter wieder entfernen wollt, dann tragt Ihr hier diese Parameter ein.

:aspect:`Default value`
    Leeres Array

:aspect:`Mandatory`
    No

Beispiel
--------

::

 <f:link.page pageUid="134">Linkname für die Seite 134</f:link.page>
 
 <f:link.page pageUid="134" additionalParams="{L:1}">
 /index.php?id=134&L=1

 <f:link.page pageUid="134" additionalParams="{param: 'test'}">
 /index.php?id=134&param=test

 <f:link.page pageUid="134" additionalParams="{param: '{name: \'test\'}'}">
 /index.php?id=134&param[name]=test
 
