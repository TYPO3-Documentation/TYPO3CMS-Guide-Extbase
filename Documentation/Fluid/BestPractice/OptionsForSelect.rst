
.. -*- coding: utf-8 -*- ÄÖÜäöüß

.. include:: ../../Includes.txt

Static options for f:form.select
================================

The f:form.select ViewHelper provides a few cool options, for example optionValueField and optionLabelField. Using these 
makes it possible to access specific properties of an object and use them as the value or label within the generated 
options of a SELECT element.

These two properties, however, present an problem: they only work with objects. If the data structure is formed of an 
array, the following test within the f:form.select ViewHelper will fail:

   if (is_object($value)) {

These two properties are only processed within this 'if' statement. We could perhaps build our own mini-domain model 
with getter and setter methods to handle the label and value. But this is overkill. The better alternative is to make 
use of the PHP standard class :php:`stdClass`:.

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

You can now use the optionValueField and optionLabelField properties within your Fluid template as usual.

   <f:form.select name="category" options="{categories}" optionValueField="key" optionLabelField="value" />

