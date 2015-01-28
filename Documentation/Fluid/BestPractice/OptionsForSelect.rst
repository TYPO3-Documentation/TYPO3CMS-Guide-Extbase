
.. -*- coding: utf-8 -*- ÄÖÜäöüß

.. include:: ../../Includes.txt

Statische Optionen für f:form.select
====================================

Der f:form.select-ViewHelper bringt einige coole Eigenschaften mit wie zum Beispiel optionValueField
und optionLabelField. Damit ist es möglich, auf bestimmte Eigenschaften eines Objektes zuzugreifen,
um diese als Value oder auch als Label für die zu generierenden Optionen der Selectbox bereit zu stellen.

Diese beiden Eigenschaften haben aber ein Problem: sie funktionieren nur in Zusammenarbeit mit Objekten. Selbst wenn
ihr die Struktur in einem Array nachbaut, so scheitert der Versuch bereits hier im f:form.select-ViewHelper::

   if (is_object($value)) {

Denn nur dort werden diese beiden Eigenschaften verarbeitet.

Natürlich könnten wir uns auch ein kleines Mini-Domainmodel mit zwei Getter- und Setter-Methoden bauen,
um Label und Value hier abzuspeichern. Das erscheint jedoch als zu aufwändig, nur um einige statische Werte
bereit zu stellen.

Abhilfe schafft hier die PHP Standardklasse :php:`stdClass`::

 /**
  * action list
  *
  * @return void
  */
 public function listAction() {
   $this->view->assign('categories', $this->getCategories());
 }

 /**
  * prepare categories for select box
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

Im Fluid-Template könnt ihr dann wieder ganz normal die beiden Eigenschaften verwenden::

   <f:form.select name="category" options="{categories}" optionValueField="key" optionLabelField="value" />

