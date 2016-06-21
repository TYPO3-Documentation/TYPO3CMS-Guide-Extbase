.. include:: ../../../Includes.txt

f:uri.page
==========

Properties
----------

pageUid
~~~~~~~
:aspect:`Variable type`
    Integer|NULL

:aspect:`Description`
    Auf welche Seiten-UID soll verlinkt werden

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

additionalParams
~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    Array

:aspect:`Description`
    Fügt weitere Parameter der Zielseite an. Im Gegensatz zu arguments, können hiermit Variablen hinzugefügt werden die nicht mit dem Extensionnamen geprefixed werden.

:aspect:`Default value`
    Leeres Array

:aspect:`Mandatory`
    No

pageType
~~~~~~~~
:aspect:`Variable type`
    Integer

:aspect:`Description`
    Auf welche Seitentyp ID soll verlinkt werden.

:aspect:`Default value`
    0

:aspect:`Mandatory`
    No

noCache
~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    Verhindert das Caching der aufzurufenden Seite

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No

noCacheHash
~~~~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    Verhindert, dass der cHash-Parameter nicht mit an die URL angehangen wird.

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No

section
~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Auf welchen Anker soll die Zielseite springen (#anker)

:aspect:`Default value`
    Leerer String

:aspect:`Mandatory`
    No

linkAccessRestrictedPages
~~~~~~~~~~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    Normalerweise werden Links auf geschützte Seiten nicht erzeugt. Hier mit kann man die Linkgeneration erzwingen.

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No

absolute
~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    Nach Aktivierung wird der Zeilseite noch der Domainname und Pfad vorangestellt.

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No

addQueryString
~~~~~~~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    Falls der aktuellen Seite bereits Parameter über die URL mitgegeben wurden, könnt Ihr hier nun entscheiden, ob diese Parameter auch mit auf die Zielseite übergeben werden.

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No

argumentsToBeExcludedFromQueryString
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    Array

:aspect:`Description`
    Falls Ihr addQueryString aktiviert habt, aber einen oder zwei bestimmte Parameter wieder entfernen wollt, dann tragt Ihr hier diese Parameter ein.

:aspect:`Default value`
    Leeres Array

:aspect:`Mandatory`
    No