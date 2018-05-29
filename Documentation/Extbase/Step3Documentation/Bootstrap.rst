.. include:: ../Includes.txt

Bootstrap
=========

The Bootstrap mechanism concerns itself with reading configuration, loading the Reflection classes, warming up the 
caches, and the activation of the persistence layer.

This initialisation process is prepared in ext_localconf.php::

 Tx_Extbase_Utility_Extension::configurePlugin(
   'Vendor.ext_key',
   'Products',
   array(
     'Product' => 'list, show',

   ),
   // non-cacheable actions
   array(
     'Product' => '',
   )
 );

The method *configurePlugin* adds the following TypoScript - with help from *t3lib_extMgm::addTypoScript* - into the 
global TypoScript template::

 # Setting Productoverview plugin TypoScript
 tt_content.list.20.productoverview_products = USER
 tt_content.list.20.productoverview_products {
   userFunc = tx_extbase_core_bootstrap->run
   extensionName = Productoverview
   pluginName = Products
 }

As soon as you add this Extbase plugin to a page, the method *run* in the class *tx_extbase_core_bootstrap* is 
exectued. So that it knows wich extension and plugin we're dealing with, information about the *extensionName* and 
*pluginName* are passed to the method. This is where the actual bootstrapping takes place.::

 $this->initializeObjectManager();
 $this->initializeConfiguration($configuration);
 $this->configureObjectManager();
 $this->initializeCache();
 $this->initializeReflection();
 $this->initializePersistence();
 $this->initializeBackwardsCompatibility();


The final task of the bootstrap is to pass all of the collected data to the *Dispatcher*.
