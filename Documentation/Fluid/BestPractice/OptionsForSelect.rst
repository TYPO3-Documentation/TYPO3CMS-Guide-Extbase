.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../Includes.txt

Statische Optionen für f:form.select
====================================

Der f:form.select-ViewHelper bringt ein paar coole Eigenschaften mit wie z.B. optionValueField und optionLabelField.
Damit ist es Euch möglich auf bestimmte Eigenschaften eines Objektes zuzugreifen, um diese als value oder auch label
für die zu generierenden Optionen der Selectbox zu erzeugen.

Diese beiden Eigenschaften haben aber ein Problem. Sie funktionieren nur in Zusammenarbeit mit Objekten. Selbst wenn
Ihr Euch die Struktur in einem Array nachbaut, so scheitert allein der Versuch an der Zeile im
f:form.select-ViewHelper::

 if (is_object($value)) {

Denn nur dort werden diese beiden Eigenschaften überhaupt verarbeitet.

Natürlich könnten wir uns auch ein kleines Mini-Domainmodel mit 2 getter und setter-Methoden bauen,
um den Label und Value hier abzuspeichern. Etwas zu umfangreich, um "mal eben" ein paar statische Werte hinzuzufügen.

Abhilfe schafft hier die PHP Standardklasse: stdClass::

 /**
  * action list
  *
  * @return void
  */
 public function listAction() {
   $this->view->assign('categories', $this->getCategories());
 }

 /**
  * get categories for select box
  *
  * @return array
  */
 public function getCategories() {
   $categories = array();
   $entries = array('car', 'bike', 'train');
   foreach ($entries as $entry) {
     $category = new stdClass();
     $category->key = $entry;
     $category->value = LocalizationUtility::translate('category.' . $entry, 'myExtName');
     $categories[] = $category;
   }
   return $categories;
 }

Im Fluid-Template könnt Ihr dann wieder ganz normal die beiden Eigenschaften verwenden::

 <f:form.select name="category" options="{categories}" optionValueField="key" optionLabelField="value" />

