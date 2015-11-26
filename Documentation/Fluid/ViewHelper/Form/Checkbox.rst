.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:form.checkbox
===============

Dieser ViewHelper erzeugt eine Checkbox.

Eigenschaften
-------------

.. include:: ../../UniversalTagAttributes.txt

.. include:: ../../UniversalFormFieldAttributes.txt

Eigenschaften speziell für das HTML-Element
###########################################

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Eigenschaft
   :Datatype,20:    Datentyp
   :Description,40: Beschreibung
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    disabled
   :Datatype:    String
   :Description: Die Checkbox wird deaktiviert angezeigt.
   :Standard:
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

 - :Property:    checked
   :Datatype:    Boolean
   :Description: Wenn aktiviert, dann gilt diese Checkbox als markiert.
   :Standard:    NULL
   :Mandatory:   Nein
   
 - :Property:    multiple
   :Datatype:    Boolean
   :Description: Spezifiziert ob eine Checkbox zu einer Multiselect-Gruppe gehört.
   :Standard:    NULL
   :Mandatory:   Nein

Derzeit sind Checkboxen innerhalb von Fluid/Extbase noch eine echte Katastrophe. Es hat mich viel Zeit gekostet eine
Checkbox überhaupt ans Laufen zu bekommen, da sie ein leeres aber vorhandenes Model erfordern, wenn sie mit Hilfe der
Property-Eigenschaft an ein Objekt gebunden werden:

No value found for key "Tx_Fluid_ViewHelpers_FormViewHelper->formObject"

Um diesen Fehler weg zu bekommen, darf das Objekt nicht NULL sein. In der entsprechenden Action muss ein leeres Objekt
erstellt werden. Könnte dann z.B. so aussehen (Auszug aus dem extension_builder):

::

 /**
  * action new
  *
  * @param $newAuto
  * @dontvalidate $newAuto
  * @return void
  */
 public function newAction(Tx_Sffluid_Domain_Model_Auto $newAuto = NULL) {
   if ($newAuto == NULL) { // workaround for fluid bug ##5636
     $newAuto = t3lib_div::makeInstance('Tx_Sffluid_Domain_Model_Auto');
   }
   $this->view->assign('newAuto', $newAuto);
 }

Erst nach dieser Änderung erscheint überhaupt mal eine Checkbox.

Beispiel ohne property
----------------------

Das Problem bei dieser Variante: Ihr müsst Euch selbst darum kümmern zu prüfen, ob die Checkbox markiert ist oder
nicht. Ihr müsst die Werte schon innerhalb Eures Controllers gesetzt haben und mit Hilfe des Checked-Attributes
zuweisen. Erlaubt ist nur TRUE oder FALSE bzw. 1 oder 0. Ihr müsst hier auch die leeren eckigen Klammern setzen,
damit die markierten Werte später als Array (Mehrfachauswahl) übergeben werden können.

::

 <f:form.checkbox name="myExtName[pizza][]" checked="{data.salami}" value="Salami" />
 <f:form.checkbox name="myExtName[pizza][]" checked="{data.hawaii}" value="Hawaii" />
 <f:form.checkbox name="myExtName[pizza][]" checked="{data.tonno}" value="Tonno" />

Beispiel mit property
---------------------

Damit Ihr dem Problem von oben entgehen könnt, bindet die Checkboxen an eine Objekteigenschaft, die Ihr im
f:form-ViewHelper hinterlegt habt:

::

 <f:form.checkbox property="pizza" value="Salami" />
 <f:form.checkbox property="pizza" value="Hawaii" />
 <f:form.checkbox property="pizza" value="Tonno" />

Schaut schon eine ganze Ecke kürzer aus.

Beispiel Multiselect
--------------------

Der extension_builder kann bis lang nur EINE Checkbox erstellen. Nämlich dann, wenn der Typ "Boolean" gewählt wurde.
Wollt Ihr aber wie in den oberen Beispielen mehrere Checkboxen gleichzeitig setzen, dann müsst Ihr Euch vom Typ
"Boolean" verabschieden. Mit dem alten kickstarter von TYPO3 können bis zu 10 gruppierte Checkboxen erstellt werden
in dem die Checkboxen binär in der Datenbank abgespeichert wurden. Jede Stelle dieser "Zahl" spiegelte eine Checkbox
wieder. 0 für deaktiviert. 1 für aktiviert. Ich will Euch heute eine Möglichkeit zeigen, wie Ihr über 10 Checkboxen
abspeichern könnt.

Innerhalb des extension_builder wählt Ihr nun den Typ "Text" aus. Damit wird in der Datenbank eine Spalte erstellt,
die etwas über 65.000 Zeichen abspeichern kann. Vergesst nicht über Database Analyser den neuen Typ in die Datenbank
zu schreiben.

Das Formular bleibt ähnlich den oberen Beispielen:

::

 <f:form.checkbox property="farbe" value="gelb" multiple=1 />&nbsp:gelb<br />
 <f:form.checkbox property="farbe" value="braun" multiple=1 />&nbsp:braun<br /> <f:form.checkbox property="farbe" value="blau" multiple=1 />&nbsp:blau<br />

Da Ihr ein Array nicht in der Datenbank abspeichern könnt, müsst Ihr das Array, das von den Checkboxen kommt in einen
String konvertieren. Das könnt Ihr zum Beispiel mit serialize() und unserialize() realisieren. Bearbeitet dazu in Eurem
Model den getter und setter für die Checkboxen:

::

 /**
  * @var string
  */
 protected $farbe;
 /**
  * @return array $farbe
  */
 public function getFarbe() {
   return unserialize($this->farbe);
 }
 /**
  * @param array $farbe
  * @return void
  */
 public function setFarbe(array $farbe) {
   $this->farbe = serialize($farbe);
 }

und fügt einen Konstruktor im Model hinzu:

::

 /**
  * initializes this object
  *
  * @param string $marke
  * @param string $beschreibung
  * @param boolean $unfall
  * @param array $farbe
  */
 public function __construct($marke = '', $beschreibung = '', $unfall = false, array $farbe = array()) {
   $this->setMarke($marke);
   $this->setBeschreibung($beschreibung);
   $this->setUnfall($unfall);
   $this->setFarbe($farbe);
 }

Nur mit diesem Konstruktor wird Eure Gruppe von Checkboxen überhaupt zur Mehrfachauswahl. Schaut Euch auch den
Quellcode an:

::

 <input type="checkbox" name="tx_sffluid_sffluid[newAuto][farbe][]" value="gelb" /><br /> <input type="checkbox" name="tx_sffluid_sffluid[newAuto][farbe][]" value="braun" /><br /> <input type="checkbox" name="tx_sffluid_sffluid[newAuto][farbe][]" value="blau" /><br />

An Hand der leeren eckigen Klammern kann man schön erkennen, dass nun die Mehrfachauswahl möglich ist. Auch das
Bearbeiten vorhandener Datensätze klappt mit dieser Methode problemlos.

Einziger Nachteil: Im Backend lassen sich die Checkboxen nicht mehr setzen.