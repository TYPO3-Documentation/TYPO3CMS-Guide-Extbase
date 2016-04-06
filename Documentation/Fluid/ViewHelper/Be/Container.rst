.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:be.container
==============

The first question you should ask yourself is whether you want to build something using the existing TYPO3 interface, or 
build something completely bespoke. If you're making a bespoke interface, then you don't need this ViewHelper at all. 
In this event, bind your own JavaScript and CSS assets yourself.

However, if you want to build something using the standard TYPO3 interface, thereby providing a close integration and 
compatibility with other modules, then use this ViewHelper. In essence, you only need to use two rows of code and around 
ten properties.

Properties
----------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Property
   :Datatype,20:    Variable type
   :Description,40: Description
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    pageTitle
   :Datatype:    String
   :Description: Backend modules are loaded in an HTML frame, so it's not essential to define an HTML page title. If you 
                 want to, then this is the property to use.
   :Standard:    Empty string
   :Mandatory:   No

 - :Property:    enableJumpToUrl
   :Datatype:    Boolean
   :Description: Activate this parameter if you want to use the ActionMenu ViewHelper. This loads the necessary 
                 JavaScript assets.
   :Standard:    TRUE
   :Mandatory:   No

 - :Property:    enableClickMenu
   :Datatype:    Boolean
   :Description: When active, this property loads the JavaScript for context menu functionality.
   :Standard:    TRUE
   :Mandatory:   No

 - :Property:    loadPrototype
   :Datatype:    Boolean
   :Description: When active, the Prototype JS framework will be loaded.
   :Standard:    TRUE
   :Mandatory:   No

 - :Property:    loadScriptaculous
   :Datatype:    Boolean
   :Description: When active, the Scriptaculous extension to Prototype JS will be loaded.
   :Standard:    FALSE
   :Mandatory:   No

 - :Property:    scriptaculousModule
   :Datatype:    String
   :Description: Using this option, you can load additional JavaScript modules for Scriptaculous.
   :Standard:    Empty string
   :Mandatory:   No

 - :Property:    loadExtJs
   :Datatype:    Boolean
   :Description: When active, the ExtJS framework will be loaded.
   :Standard:    FALSE
   :Mandatory:   No

 - :Property:    loadExtJsTheme
   :Datatype:    Boolean
   :Description: When active, templates for the graphical elements of the ExtJs framework will be loaded.
   :Standard:    TRUE
   :Mandatory:   No

 - :Property:    extJsAdapter
   :Datatype:    String
   :Description: You can use this property to define a different adaptor instead of the standard, Extbase.
   :Standard:    Empty string
   :Mandatory:   No

 - :Property:    enableExtJsDebug
   :Datatype:    Boolean
   :Description: This property should only be activated during a development process involving ExtJS.
   :Standard:    FALSE
   :Mandatory:   No

 - :Property:    addCssFile
   :Datatype:    String
   :Description: Bind a specific CSS asset file to the view.
   :Standard:    NULL
   :Mandatory:   No

 - :Property:    addJsFile
   :Datatype:    String
   :Description: Bind a specific JavaScript asset file to the view.
   :Standard:    NULL
   :Mandatory:   No

 - :Property:    loadJQuery
   :Datatype:    Boolean
   :Description: When active, jQuery will be loaded.
   :Standard:    FALSE
   :Mandatory:   No

 - :Property:    includeCssFiles
   :Datatype:    Array
   :Description: Using addCssFile will only allow you to bind in a single CSS asset file. Using includeCssFiles allows 
                 you to bind multiple files.
   :Standard:    NULL
   :Mandatory:   No

 - :Property:    includeJsFiles
   :Datatype:    Array
   :Description: Using addJsFile will only allow you to bind in a single JavaScript asset file. Using includeCssFiles 
                 allows you to bind multiple files.
   :Standard:    NULL
   :Mandatory:   No

 - :Property:    addJsInlineLabels
   :Datatype:    Array
   :Description: Each value must correspond to a key from the locallang.xml/xlf file. The matching translation will then 
                 be available in the backend.
   :Standard:    NULL
   :Mandatory:   No
