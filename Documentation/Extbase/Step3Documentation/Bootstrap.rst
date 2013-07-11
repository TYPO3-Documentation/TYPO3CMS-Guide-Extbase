.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM. ÄÖÜäöüß

.. include:: ../Includes.txt

Bootstrap
=========

Der Bootstrap Mechanismus kümmert sich darum, die Konfiguration auszulesen, die Reflectionklassen zu laden,
die Caches aufzuwärmen und die Persistenzschicht zu aktivieren.

Dieser Initiierungsprozess wird über die ext_localconf.php vorbereitet::

 Tx_Extbase_Utility_Extension::configurePlugin(
   $_EXTKEY,
   'Products',
   array(
     'Product' => 'list, show',

   ),
   // non-cacheable actions
   array(
     'Product' => '',
   )
 );

Die Methode *configurePlugin* fügt dann mit Hilfe von *t3lib_extMgm::addTypoScript* dieses TypoScript in das globale
TS-Template ein::

 # Setting Productoverview plugin TypoScript
 tt_content.list.20.productoverview_products = USER
 tt_content.list.20.productoverview_products {
   userFunc = tx_extbase_core_bootstrap->run
   extensionName = Productoverview
   pluginName = Products
 }

Sobald Ihr nun dieses Extbaseplugin auf einer Seite einbindet, wird die Methode *run* aus der Klasse
*tx_extbase_core_bootstrap* aufgerufen. Damit die weiß, um welche Extension und Plugin es sich handelt,
werden diese Informationen mit *extensionName* und *pluginName* an die run-Methode übergeben.
Hier findet der eigentliche Bootstrap statt::

 $this->initializeObjectManager();
 $this->initializeConfiguration($configuration);
 $this->configureObjectManager();
 $this->initializeCache();
 $this->initializeReflection();
 $this->initializePersistence();
 $this->initializeBackwardsCompatibility();

Die letzte Aufgabe des Bootsraps ist die Übergabe der gesammelten Daten an den Dispatcher