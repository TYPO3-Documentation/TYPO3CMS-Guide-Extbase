.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:be.tableList
==============

Sehr geiles Teil. Was wir aus dem Modul Web->Liste kennen können wir nun selbst verwenden und super einfach
konfigurieren, wie die folgenden Beispiele zeigen.

Eigenschaften
-------------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Eigenschaft
   :Datatype,20:    Datentyp
   :Description,40: Beschreibung
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    tableName
   :Datatype:    String
   :Description: Der Name der Tabelle
   :Standard:    NULL
   :Mandatory:   Ja

 - :Property:    storagePid
   :Datatype:    Integer
   :Description: Die Daten welcher Seite sollen angezeigt werden? Wenn nichts anderen angegeben wurde, werden die Datensätze der Seite angezeigt, die über persistence.storagePid angegeben wurde.
   :Standard:    NULL
   :Mandatory:   Ja

 - :Property:    levels
   :Datatype:    Integer
   :Description: Falls die Seite aus storagePid noch Unterordner enthält, könnt Ihr hier angeben wie viele Ebenen tiefer nach weiteren Datensätzen gesucht werden soll.
   :Standard:    0
   :Mandatory:   Ja

 - :Property:    filter
   :Datatype:    String
   :Description: Gebt hier ein Suchwort ein, nach dem Eure Datensätze gefiltert werden sollen.
   :Standard:    Leerer String
   :Mandatory:   Ja

 - :Property:    recordsPerPage
   :Datatype:    Integer
   :Description: Wie viele Datensätze dürfen maximal auf einer Seite angezeigt werden.
   :Standard:    0
   :Mandatory:   Ja

 - :Property:    sortField
   :Datatype:    String
   :Description: Nach welchem Feld sollen die gefundenen Datensätze sortiert werden
   :Standard:    Leerer String
   :Mandatory:   Ja

 - :Property:    sortDescending
   :Datatype:    Boolean
   :Description: Wenn aktiviert, dann werden die Datensätze rückwärts sortiert.
   :Standard:    FALSE
   :Mandatory:   Ja

 - :Property:    readOnly
   :Datatype:    Boolean
   :Description: Wenn aktiviert, dann werden die Bearbeitungssymbole nicht mehr angezeigt.
   :Standard:    FALSE
   :Mandatory:   Ja

 - :Property:    enableClickMenu
   :Datatype:    Boolean
   :Description: Wenn aktiviert, dann kann das Contextmenü verwendet werden
   :Standard:    TRUE
   :Mandatory:   Ja

 - :Property:    clickTitleMode
   :Datatype:    String
   :Description: Auswahl von "edit", "info" und "show". Falls Ihr show auswählt, dann klappt das nur bei der Tabelle pages und tt_content. Normalerweise müsst Ihr immer erst über das Kontextmenü oder über ein anderes Modul in diese Bereich klicken. Nun reicht ein Klick auf den Titel des Datensatzes.
   :Standard:    NULL
   :Mandatory:   Ja

 - :Property:    alternateBackgroundColors
   :Datatype:    Boolean
   :Description: Wenn aktiviert, wechseln sich die Hintergrundfarben je Datenzeile ab.
   :Standard:    FALSE
   :Mandatory:   Ja

Minimalistisches Beispiel
-------------------------

Dieses Beispiel zeigt die Tabelle tt_content mit den beiden Feldern header und bodytext. Die Tabelle wird nur dann
angezeigt wenn sich auf der Seite, die durch storagePid angegeben wurde auch tatsächlich Datensätze dieser Tabelle
befinden. Alle Backendmodule, die zumindest über den extension_builder erzeugt wurden bringen ein Extensiontemplete
mit, das auf der Rootseite eingebunden werden sollte. Über den Konstanteneditor kann nun eine Seiten-UID eingetragen
werden, die als Fallback dienst, falls wie hier in unserem Beispiel keine storagePid angegeben worden ist.

::

 <f:be.tableList tableName="tt_content" fieldList="{0: 'header', 1: 'bodytext'}" />

Beispiel: Maximale Datensatzanzahl
----------------------------------

Obwohl wir hier den Parameter recordsPerPage nicht angegeben haben, werden uns innerhalb des Introductionpackage nur
100 Datensätz auf der ersten Seite angezeigt von etwas über 150. Denn wenn dieser Parameter nicht angegeben wird, gilt
erstens der Wert aus dem TCA ($TCA[TabellenName]['interface']['maxSingleDBListItems']) und wenn dieser nicht angegeben
ist 100. Mit Hilfe von recordsPerPage ist es auch möglich mehr als 100 Datensätze anzeigen zu lassen.

::

 <f:be.tableList tableName="tt_content" fieldList="{0: 'header', 1: 'bodytext'}" storagePid="1" levels="5" />

Beispiel: Datensatz direkt anzeigen
-----------------------------------

Normalerweise muss man immer über das Modul Web->Anzeigen oder über das Kontextmenü navigieren, um eine erste Preview
seines gewählten Datensatzes zu erhalten. Viel einfacher geht es, wenn man den Titel eines Datensatzes (Der Wert aus
der ersten Spalte) mit dieser Möglichkeit verlinkt. Hierfür gibt es den Parameter clickTitleMode, den Ihr auf "show"
setzen müsst. Zusätzlich habe ich in dieses Beispiel nach einen Wechselnden Hintergrund je Datenzeile implementiert.

::

 <f:be.tableList tableName="tt_content" fieldList="{0: 'header', 1: 'bodytext'}" storagePid="1" levels="5" alternateBackgroundColors="TRUE" clickTitleMode="show" />