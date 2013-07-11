.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM. ÄÖÜäöüß

.. include:: Includes.txt

Erweitern der Extbase Extension
===============================

Dieses Tutorial baut auf das Tutorial zum Erstellen der ersten Extbase Extension auf.

Anzeigen der Kategorien in der Detailansicht
---------------------------------------------

Das Template für die Detailansicht findet Ihr hier:

::

 typo3conf/ext/productoverview/Resources/Private/Partials/Product/Properties.html

Ihr seht, dass nur *title* und *price* ausgegeben werden. Die Verknüpfungen von Domainmodellen kann der Extension
Builder derzeit nicht darstellen, deshalb müsst Ihr das selber nach holen. Fügt nun die Zeile für die *category*
ein. Das Template sollte nun so aussehen:

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

Ihr seht, dass vom *Product* per Punktnotation auf das verknüpfte Domainmodel *Category* zugegriffen werden
kann. Das ist das Prinzip eines *Aggregate Root*. Da Ihr pro Produkt mehrere Kategorien anlegen könnt,
müssen diese Kategorien mit Hilfe einer Schleife durch laufen werden. Pro Durchlauf wird dann die Eigenschaft
*category* in einer Liste ausgegeben.

Speichert dieses Template ab, leert den Cache und ladet Euer Plugin nochmal neu. Die Kategorien zu den Produkten
werden nun in einer Liste aufgeführt.

Mehrfachverwendung von Kategorien
---------------------------------

Derzeit könnt Ihr zwar pro Produkt ein oder mehrere Kategorien zuordnen, aber es ist nicht möglich eine bereits
vorhandene Kategorie einem Produkt zuzuordnen. Um dieses Verhalten zu ändern geht Ihr in diese Datei:

::

 typo3conf/ext/productoverview/Configuration/Tca/Product.php

ersetzt diesen Eintrag hier::

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

mit diesem::

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
