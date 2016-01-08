.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../../Includes.txt

f:be.buttons.csh
================

This ViewHelper is rarely used, but very helpful nonetheless. It enables to include hints into Backend forms.
TYPO3 uses this functionality all over the backend, and it is noticeable by the small question mark images. When
hovered it reveals the helptext in a little tooltip. It can be activated by mouse click and then display the help
text in a popup window. There is a setting in the user configuration whether to show the popup or not.

Features
--------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Property
   :Datatype,20:    Datatype
   :Description,40: Description
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    table
   :Datatype:    String
   :Description: table name
   :Standard:    NULL
   :Mandatory:   No

 - :Property:    field
   :Datatype:    String
   :Description: the key from locallang file to use
   :Standard:    empty string
   :Mandatory:   No

 - :Property:    iconOnly
   :Datatype:    Boolean
   :Description: display the icon, but not the text
   :Standard:    FALSE
   :Mandatory:   No

 - :Property:    styleAttributes
   :Datatype:    String
   :Description: additional style attribute, added to the containing table
   :Standard:    empty string
   :Mandatory:   No

**Hinweis zu einem Sonderfall bei der Eigenschaft "table"**

Es gibt einen Sonderfall bei dem die Eigenschaft "table" überhaupt nicht angegeben werden muss. Dieser tritt dann
ein, wenn es in dem Modul zwar Formularfelder gibt, die aber keine 1zu1-Spalte in der Datenbank besitzen. So werden
beim scheduler z.B. alle Formularfelder serialisiert in einem DB-Feld abgespeichert (kein 1zu1-Abbild der Felder)
oder z.B. Textfelder, die für Suchanfragen benötigt werden (keine DB-Speicherung). Diesen besonderen Felder kann mit
Hilfe eines Eintrages in der ext_tables.php ein csh-Icon zugewiesen werden::

 \TYPO3\CMS\Core\Utility\ExtensionManagementUtility::addLLrefForTCAdescr(
   '_MOD_VollständigerModulname',
   'PfadZuEinerSprachdatei'
 );

Beachtet bitte, dass es sich bei dem Modulnamen um den vollständig ausgeschriebenen Modulnamen handelt. Dieser
besteht aus Kategorie (z.B. web), Extensionname (upper camel case) und Modulname (upper camel case). In meiner
Beispielextension "sfextbase" mit dem Modulnamen "extbase" würde der vollständige Name so lauten::

 web_SfextbaseExtbase

Hier eine Möglichkeit, wie es bei Euch aussehen könnte::

 \TYPO3\CMS\Core\Utility\ExtensionManagementUtility::addLLrefForTCAdescr(
   '_MOD_web_SfextbaseExtbase',
   'EXT:' . $_EXTKEY . '/Resources/Private/Language/locallang_extbase.xlf'
 );

Der Eintrag für die E-Mail-Adresse sieht in meiner xlf-Datei so aus::

 <trans-unit id="email.alttitle" xml:space="preserve">
   <source>E-Mail</source>
 </trans-unit>
 <trans-unit id="email.description" xml:space="preserve">
   <source>Tragen Sie hier Ihre E-Mail-Adresse ein</source>
 </trans-unit>
 <trans-unit id="email.details" xml:space="preserve">
   <source>Ich bin eine ewig lange Beschreibung, die Ihnen on Detail erklärt, wobei es sich um eine
   E-Mail-Adress handelt, wo Sie eine her bekommen und was zu beachten ist,
   um eine valide Adresse in dieses Feld einzutragen</source>
 </trans-unit>

Beispiele
---------

.. caution::

 Im Quellcode der csh-API befindet sich eine Abfrage auf die BE-User-Option: edit_showFieldHelp. Diese ist per
 Default nicht gesetzt und verhindert somit grundsätzlich die Ausgabe dieser csh-Hilfetexte. Um diesen ViewHelper in
 Aktion sehen zu können, müsst Ihr entweder in den Benutzer- oder Gruppenoptionen folgende Einstellung in die
 UserTSconfig setzen::

  setup.override.edit_showFieldHelp = text

Beispiel: Datenbankfelder
#########################

Usually in the most TYPO3 tables the language file key is the same as the column name::

 <f:be.buttons.csh table="tt_content" field="header" />

Beispiel mit Stil
#################

::

 <f:be.buttons.csh table="tt_content" field="header" styleAttributes="background-color: red;" />

Beispiel: Icons für Formularfelder ohne 1zu1-Abbild in der Datenbank
####################################################################

Hier ein Beispiel für den oben beschriebenen Sonderfall, bei dem der Tabellenname nicht angegeben werden darf::

 <f:be.buttons.csh field="email" />

