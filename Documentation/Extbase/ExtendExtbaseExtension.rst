.. include:: Includes.txt

Extending an Extbase extension
==============================

This tutorial builds on the tutorial for the creation of your first Extbase extension.


Showing categories in the detail view
-------------------------------------

You'll find the template for the detail view here:

::

 typo3conf/ext/productoverview/Resources/Private/Partials/Product/Properties.html


When you begin, you'll see that only the *title* and *price* are displayed. at present, the 
Extension Builder doesn't automatically display the domain model connections, so you'll need 
to add them yourself. Add the following code to the template, so that the *category* is displayed.

::

 <table class="tx-productoverview" >
   <tr>
     <td>
       <f:translate key="tx_productoverview_domain_model_product.title" />
     </td>
     <td>
       {product.title}
     </td>
   </tr>
   <tr>
     <td>
       <f:translate key="tx_productoverview_domain_model_product.price" />
     </td>
     <td>
       {product.price}
     </td>
   </tr>
   <tr>
     <td>
       <f:translate key="tx_productoverview_domain_model_product.categories" />
     </td>
     <td>
       <ul>
         <f:for each="{product.categories}" as="category">
           <li>{category.category}</li>
         </f:for>
       </ul>
     </td>
   </tr>
 </table>


As you can see, you can access the related *Category* domain model by using simple dot notation. Because you've 
defined that each product can be related to more than one category - a principle of an *aggregate root* -  you'll 
need to use a loop to display all the related categories.

Save the template, clear the TYPO3 caches and reload the page in the frontend. The categories will now be displayed 
for each product.

Multiple usage of categories
----------------------------

So far, you can add one or more categories to a product, but you can't connect an existing category to a new 
product. To change that, edit the following file…

::

 typo3conf/ext/productoverview/Configuration/Tca/Product.php

…by replacing the following configuration code::

 'categories' => array(
   'exclude' => 0,
   'label' => 'LLL:EXT:productoverview/Resources/Private/Language/locallang_db
    .xml:tx_productoverview_domain_model_product.categories',
   'config' => array(
     'type' => 'inline',
     'foreign_table' => 'tx_productoverview_domain_model_category',
     'foreign_field' => 'product',
     'maxitems'      => 9999,
     'appearance' => array(
       'collapseAll' => 0,
       'levelLinksPosition' => 'top',
       'showSynchronizationLink' => 1,
       'showPossibleLocalizationRecords' => 1,
       'showAllLocalizationLink' => 1
     ),
   ),
 ),

…with this code::

 'categories' => array(
   'exclude' => 0,
   'label' => 'LLL:EXT:productoverview/Resources/Private/Language/locallang_db.xml:tx_productoverview_domain_model_product.categories',
   'config' => array(
     'type' => 'select',
     'foreign_table' => 'tx_productoverview_domain_model_category',
     'foreign_field' => 'product',
     'maxitems'      => 9999,
   ),
 ),

This changes the field in the backend from an inline relation field to a select field.