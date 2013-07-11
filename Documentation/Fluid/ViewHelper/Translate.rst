.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../Includes.txt

f:translate
===========

Mit dem f:translate-ViewHelper greift Ihr auf eine beliebige Sprachdatei (meist locallang.xml) zu und holt Euch die
entsprechende Übersetzung mit Hilfe der Angabe im Parameter "key".

Eigenschaften
-------------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Eigenschaft
   :Datatype,20:    Datentyp
   :Description,40: Beschreibung
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    key
   :Datatype:    String
   :Description: Der key, mit dem man die Übersetzung aus dem Sprachdateien auslesen kann
   :Standard:    NULL
   :Mandatory:   Ja

 - :Property:    default
   :Datatype:    String
   :Description: Wenn der Key in der Sprachdatei nicht gefunden werden kann, dann verwende diesen Text. Wenn default nicht gesetzt ist, wird der Inhalt zwischen den Tags verwendet.
   :Standard:    NULL
   :Mandatory:   Ja

 - :Property:    htmlEscape
   :Datatype:    Boolean
   :Description: Alle Übersetzungen aus den Sprachdateien werden durch htmlspecialchars geschleust, was es unmöglich macht, HTML-Tags in den Übersetzungen anzeigen zu lassen. Setzt diesen Wert auf FALSE, um dieses Vorgehen zu unterbinden.
   :Standard:    TRUE
   :Mandatory:   Ja

 - :Property:    arguments
   :Datatype:    Array
   :Description: In den Übersetzungen können Platzhalter definiert werden, die dann mit den Inhalten diesen Arrays gefüllt werden.
   :Standard:    NULL
   :Mandatory:   Ja

Innerhalb von Extensions wird immer auf die locallang.xml im Verzeichnis Resources/Private/Language/ zugegriffen.
Im Bereich FLUIDTEMPLATE müsste Ihr hier die Pfadsyntax verwenden:

::

 LLL:fileadmin/templates/locallang.xml:domain_model_irgendwas.titel

bzw:

::

 LLL:EXT:meineExtension/Resources/Private/Language/locallang.xml:domain_model_irgendwas.titel

Diese "LLL:" Prefixe müssen bei der Pfadnotation immer gesetzt sein!!! Etwas einfacher machen es sich die
FLUIDTEMPLATE-User, wenn sie im TS zuvor angeben auf welche locallang.xml welcher Extension sie zugreifen wollen:

::

 extbase.pluginName = Pi1
 extbase.controllerExtensionName = MeineExtension

Dann reicht es auch wieder nur den "key" anzugeben OHNE den ganzen Pfad

Beispiel
--------

::

 <f:translate key="domain_model.title" htmlEscape="false" />

Beispiel mit Pfad
-----------------

::

 <f:translate key="LLL:fileadmin/lang/locallang.xml:domain_model.title" />

Beispiel mit Platzhaltern
-------------------------

In unserem Template:

::

 <f:translate key="LLL:fileadmin/lang/locallang.xml:domain_model.title" arguments="{0: 'Herr der Ringe'}" />

In der locallang.xml

::

 <label index="domain_model.title">Title of: %s</label>

Mit %s wird auf den ersten Wert des übergebenen Arrays zugegriffen. Kommt %s nochmals vor, dann wird auf den zweiten
Arrayeintrag zugegriffen. Um das unabhängig von der Reihenfolge zu machen empfehlen wir noch folgende Notation:

::

 <label index="domain_model.title">Titel von: %1$s</label>

Mit %1 greift Ihr auf den ersten Eintrag zu und sagt diesem, dass er als String/Text interpretiert werden soll ($s).
Auf php.net findet Ihr heraus wofür diese ganzen Kürzel stehen.