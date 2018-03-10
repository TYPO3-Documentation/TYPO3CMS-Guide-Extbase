.. include:: ../../../Includes.txt

=================
f:be.pageRenderer
=================

The first question you should ask yourself is whether you want to build something using the existing TYPO3 interface, or
build something completely bespoke. If you're making a bespoke interface, then you don't need this ViewHelper at all.
In this event, bind your own JavaScript and CSS assets yourself.

However, if you want to build Extbase modules using the standard TYPO3 interface, thereby providing a close integration and
compatibility with other modules, then use this ViewHelper. In essence, you only need to use two rows of code and around
ten properties.

Properties
==========

.. rst-class:: dl-parameters

pageTitle
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       string
   :sep:`|` :aspect:`Default:`    empty string
   :sep:`|`

   'title' tag of the module. Not required by default, as BE modules are shown
   in a frame.


loadExtJs
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       boolean
   :sep:`|` :aspect:`Default:`    false
   :sep:`|`

   Specifies whether to load ExtJS library. This option will be removed in
   TYPO3 v9.


loadExtJsTheme
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       boolean
   :sep:`|` :aspect:`Default:`    true
   :sep:`|`

   Whether to load ExtJS "grey" theme. This option will be removed in TYPO3 v9.


enableExtJsDebug
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       boolean
   :sep:`|` :aspect:`Default:`    false
   :sep:`|`

   If set to TRUE, the debug version of ExtJS is loaded. Use this for
   development only. This option will be removed in TYPO3 v9.


loadJQuery
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       boolean
   :sep:`|` :aspect:`Default:`    false
   :sep:`|`

   Whether to load jQuery library. This option will be removed in TYPO3 v9.


includeCssFiles
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       array
   :sep:`|` :aspect:`Default:`    null
   :sep:`|`

   List of custom CSS files to be loaded.


includeJsFiles
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       array
   :sep:`|` :aspect:`Default:`    null
   :sep:`|`

   List of custom JavaScript files to be loaded.


addJsInlineLabels
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       array
   :sep:`|` :aspect:`Default:`    null
   :sep:`|`

   Custom labels to add to JavaScript inline labels.


includeRequireJsModules
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       array
   :sep:`|` :aspect:`Default:`    null
   :sep:`|`

   List of RequireJS modules to be loaded.


jQueryNamespace
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       string
   :sep:`|` :aspect:`Default:`    empty string
   :sep:`|`

   Store the jQuery object in a specific namespace. This option will be removed
   in TYPO3 v9.


Examples
========

All options
-----------

Custom CSS file EXT:your_extension/Resources/Public/Css/styles.css and JavaScript files
EXT:your_extension/Resources/Public/JavaScript/Library1.js and EXT:your_extension/Resources/Public/JavaScript/Library2.js
will be loaded, plus ExtJS and jQuery and some inline labels for usage in JS code.

::

    <f:be.pageRenderer pageTitle="foo" 
                       loadExtJs="true" 
                       loadExtJsTheme="false" 
                       extJsAdapter="jQuery" 
                       enableExtJsDebug="true" 
                       loadJQuery="true" 
                       includeCssFiles="0: '{f:uri.resource(path:\'Css/Styles.css\')}'"
                       includeJsFiles="
                           0: '{f:uri.resource(path:\'JavaScript/Library1.js\')}',
                           1: '{f:uri.resource(path:\'JavaScript/Library2.js\')}'" 
                       addJsInlineLabels="{0: 'label1', 1: 'label2'}" 
    />
    
    
