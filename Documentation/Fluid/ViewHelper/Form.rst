.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../Includes.txt

f:form
======

Der f:form-ViewHelper schaut von seinen ganzen Parametern extremst gewaltig aus. Aber wenn man mal bedenkt das allein
11 Parameter nur für die Generierung der Zielseiten-URL zuständig sind, bleibt nur noch eine handvoll Parameter übrig.
Der große Vorteil diesen ViewHelpers ist Sicherheit und Arbeitserleichterung, die wir uns in den Beispielen mal näher
anschauen.

Eigenschaften
-------------

.. include:: ../UniversalTagAttributes.txt

Eigenschaften speziell für das HTML-Element
###########################################

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Eigenschaft
   :Datatype,20:    Datentyp
   :Description,40: Beschreibung
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    action
   :Datatype:    String
   :Description: Welche Actionmethode soll aufgerufen werden, wenn das Formular abgesendet wird
   :Standard:    NULL
   :Mandatory:   Ja

 - :Property:    arguments
   :Datatype:    Array
   :Description: Welche zusätzlichen Variablen sollen beim Absenden mit übergeben werden
   :Standard:    Leeres Array
   :Mandatory:   Ja

 - :Property:    controller
   :Datatype:    String
   :Description: Falls sich die gewünschte Actionmethode nicht im gleichen Controller befindet, muss hier dieser entsprechende Controller angegeben werden
   :Standard:    NULL
   :Mandatory:   Ja

 - :Property:    extensionName
   :Datatype:    String
   :Description: Falls das Formular von einer anderen Extension abgearbeitet werden soll, dann muss hier der Extensionname ohne tx\_ und ohne Unterstriche angegeben werden
   :Standard:    NULL
   :Mandatory:   Ja

 - :Property:    pluginName
   :Datatype:    String
   :Description: Falls das Formular von einem anderen Plugin abgearbeitet werden soll, dann muss hier der Pluginname angegeben werden
   :Standard:    NULL
   :Mandatory:   Ja

 - :Property:    pageUid
   :Datatype:    Integer
   :Description: Seiten-UID eintragen, wenn das Formular von einer anderen Seite aus abgearbeitet werden soll
   :Standard:    NULL
   :Mandatory:   Ja

 - :Property:    object
   :Datatype:    Mixed
   :Description: Übergebt hier ein Objekt mit Eigenschaften, die die Eingabefelder im Formular wiederspiegeln.
   :Standard:    NULL
   :Mandatory:   Ja

 - :Property:    pageType
   :Datatype:    Integer
   :Description: Gebt hier eine Seitentyp ID an, die das Formular abarbeiten soll. Könnte für AJAX interessant sein.
   :Standard:    0
   :Mandatory:   Ja

 - :Property:    noCache
   :Datatype:    Boolean
   :Description: Kann aktiviert werden, um das Caching für die Zielseite zu deaktivieren.
   :Standard:    FALSE
   :Mandatory:   Ja

 - :Property:    noCacheHash
   :Datatype:    Boolean
   :Description: Nach Aktivierung wird dem generierten Link zur Zielseite kein cHash-Parameter angehangen
   :Standard:    FALSE
   :Mandatory:   Ja

 - :Property:    section
   :Datatype:    String
   :Description: Definition eines Ankers zu dem auf der Zielseite gesprungen werden soll. Interessant wir Seiten auf denen viele Inhalte sind.
   :Standard:    Leerer String
   :Mandatory:   Ja

 - :Property:    format
   :Datatype:    String
   :Description: Gibt an um welches Format es sich bei der Zielseite handelt. Alternativ ginge auch "xml", obwohl das bei einer Formularzielseite wenig Sinn machen würde. Klappt nur wenn actionUri nicht gesetzt ist.
   :Standard:    Leerer String
   :Mandatory:   Ja

 - :Property:    additionalParams
   :Datatype:    Array
   :Description: Fügt weitere Variablen der Zielseite an. Im Gegensatz zu arguments, können hiermit Variablen hinzugefügt werden die nicht mit dem Extensionnamen geprefixed werden. Klappt nur wenn actionUri nicht gesetzt ist.
   :Standard:    Leeres Array
   :Mandatory:   Ja

 - :Property:    absolute
   :Datatype:    Boolean
   :Description: Nach Aktivierung wird der Zeilseite noch der Domainname und Pfad vorangestellt. Klappt nur wenn actionUri nicht gesetzt ist.
   :Standard:    FALSE
   :Mandatory:   Ja

 - :Property:    addQueryString
   :Datatype:    Boolean
   :Description: Falls dem Formular bereits Parameter über die URL mitgegeben wurden, könnt Ihr hier nun entscheiden, ob diese Parameter auch mit auf die Zielseite übergeben werden. Klappt nur wenn actionUri nicht gesetzt ist.
   :Standard:    FALSE
   :Mandatory:   Ja

 - :Property:    argumentsToBeExcludedFromQueryString
   :Datatype:    Array
   :Description: Falls Ihr addQueryString aktiviert habt, aber einen oder zwei bestimmte Parameter wieder entfernen wollt, dann tragt Ihr hier diese Parameter ein. Klappt nur wenn actionUri nicht gesetzt ist.
   :Standard:    Leeres Array
   :Mandatory:   Ja

 - :Property:    fieldNamePrefix
   :Datatype:    String
   :Description: Falls ein anderer Prefix gewünscht ist. Macht eigentlich nur Sinn, wenn die Formulardaten von einer anderen Extension abgearbeitet werden müssen.
   :Standard:    NULL
   :Mandatory:   Ja

 - :Property:    actionUri
   :Datatype:    String
   :Description: Gebt hier Eure ganz eigene individuelle Zielseiten-URL ein. Viele der oberen Parameter haben aber dann keinen Wirkung mehr.
   :Standard:    NULL
   :Mandatory:   Ja

 - :Property:    objectName
   :Datatype:    String
   :Description: Hier kommt ein Objekt- bzw. Modelname rein, in das die nach Absenden gesammelten Formulardaten gespeichert werden sollen. Hat den Vorteil, dass Ihr nicht in jeder Action die Formulardaten überprüfen, sondern die Überprüfung nur einmalig im Model vornehmen müsst.
   :Standard:    NULL
   :Mandatory:   Ja


Beispiel
--------

::

 <f:form object="{feUser}" objectName="newFeUser">
   <f:form.textarea property="firstName" rows="5" cols="50" />
 </f:form>

Hier eine üngefähre Ausgabe was nun im Seitenquelltext hinzugefügt wurde:

::

 <form action="/typo3_46/index.php?id=6&amp;tx__%5Bcontroller%5D=Standard&amp;cHash=d1469ddb628871564f3257920c1f6ee8" method="post">
   <div style="display: none">
     <input type="hidden" name="__referrer[extensionName]" value="" />
     <input type="hidden" name="__referrer[controllerName]" value="Standard" />
     <input type="hidden" name="__referrer[actionName]" value="index" />
     <input type="hidden" name="__hmac" value="a:2:{s:9:&quot;newFeUser&quot;;a:1:{s:9:&quot;firstName&quot;;i:1;}s:4:&quot;tx__&quot;;a:1:{s:10:&quot;controller&quot;;i:1;}}ff5ff9b62f7b5c49a696d3f7b1009991853d6533" />
   </div>
   <textarea rows="5" cols="50" name="newFeUser[firstName]"></textarea>
 </form>

Hier seht Ihr das Thema Sicherheit. Fluid baut automatisch einen versteckten Bereich mit ein paar Werten in Euer
Formular ein. Unteranderem befindet sich dort ein __hmac-Wert. Innerhalb diesen Wertes sind alle erlaubten
Formularfelder nochmals enthalten. Wenn also über bestimmte Webseitenattacken Felder entfernt oder hinzugefügt werden,
dann kann Extbase später feststellen, dass die Anzahl und/oder Feldnamen nicht übereinstimmen und wirft eine
Fehlermeldung. Das Formular kann also nicht abgesendet werden.

Im Beispiel haben wir noch den Objektnamen "newFeUser" angegeben. Wie Ihr seht wurde dieser Wert jedem Feld in meinem
Formular vorangestellt. Das hat den Vorteil, dass Eure Formularfelder nicht einzeln, sondern gebündelt in einem Array
an die Zielseite übertragen werden. Dort angekommen könnt Ihr Eurer Action mitteilen, dass der Inhalt diesen Arrays in
ein Modell portiert werden soll. Bei dieser Portierung werden auch automatisch die enthaltenen Werte auf Gültigkeit
überprüft, sofern Ihr überhaupt Überprüfungsregeln in Euren Modellen angegeben habt. Nur wenn alle Überprüfungen
gültig waren, kann das Modell mit den Formulardaten an die Action übergeben werden und dort mit einem Einzeiler in der
Datenbank gespeichert werden.