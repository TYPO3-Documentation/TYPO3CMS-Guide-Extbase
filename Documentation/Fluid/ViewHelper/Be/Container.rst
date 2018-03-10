.. include:: ../../../Includes.txt

==============
f:be.container
==============

The first question you should ask yourself is whether you want to build
something using the existing TYPO3 interface, or build something completely
bespoke. If you're making a bespoke interface, then you don't need this
ViewHelper at all. In this event, bind your own JavaScript and CSS assets
yourself.

However, if you want to build something using the standard TYPO3 interface,
thereby providing a close integration and compatibility with other modules,
then use this ViewHelper. In essence, you only need to use two rows of code and
around ten properties.

Properties
==========

pageTitle
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       string
   :sep:`|` :aspect:`Default:`    empty string
   :sep:`|`

   Backend modules are loaded in an HTML frame, so it's not essential to define
   an HTML page title. If you want to, then this is the property to use.


enableJumpToUrl
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       boolean
   :sep:`|` :aspect:`Default:`    true
   :sep:`|`

   Activate this parameter if you want to use the ActionMenu ViewHelper. This
   loads the necessary JavaScript assets.

   This property has been marked as deprecated in TYPO3 6.2 and was removed in
   TYPO3 7.0.


enableClickMenu
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       boolean
   :sep:`|` :aspect:`Default:`    true
   :sep:`|`

   When active, this property loads the JavaScript for context menu
   functionality.


loadPrototype
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       boolean
   :sep:`|` :aspect:`Default:`    true
   :sep:`|`

   When active, the Prototype JS framework will be loaded.

loadScriptaculous
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       boolean
   :sep:`|` :aspect:`Default:`    false
   :sep:`|`

   When active, the Scriptaculous extension to Prototype JS will be loaded.

scriptaculousModule
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       string
   :sep:`|` :aspect:`Default:`    empty string
   :sep:`|`

   Using this option, you can load additional JavaScript modules for
   Scriptaculous.


loadExtJs
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       boolean
   :sep:`|` :aspect:`Default:`    false
   :sep:`|`

   When active, the ExtJS framework will be loaded.


loadExtJsTheme
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       boolean
   :sep:`|` :aspect:`Default:`    true
   :sep:`|`

   When active, templates for the graphical elements of the ExtJs framework
   will be loaded.


extJsAdapter
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       string
   :sep:`|` :aspect:`Default:`    empty string
   :sep:`|`

   You can use this property to define a different adaptor instead of the
   standard, Extbase.


enableExtJsDebug
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       boolean
   :sep:`|` :aspect:`Default:`    false
   :sep:`|`

   This property should only be activated during a development process
   involving ExtJS.


addCssFile
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       string
   :sep:`|` :aspect:`Default:`    null
   :sep:`|`

   Bind a specific CSS asset file to the view.

   This property has been marked as deprecated in TYPO3 6.2 and was removed in
   TYPO3 7.0. Please use the `includeCssFiles` instead.


addJsFile
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       string
   :sep:`|` :aspect:`Default:`    null
   :sep:`|`

   Bind a specific JavaScript asset file to the view.

   This property has been marked as deprecated in TYPO3 6.2 and was removed in
   TYPO3 7.0. Please use the `includeJsFiles` instead.


loadJQuery
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       boolean
   :sep:`|` :aspect:`Default:`    false
   :sep:`|`

   When active, jQuery will be loaded.


includeCssFiles
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       array
   :sep:`|` :aspect:`Default:`    null
   :sep:`|`

   Using addCssFile will only allow you to bind in a single CSS asset file.
   Using includeCssFiles allows you to bind multiple files.


includeJsFiles
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       array
   :sep:`|` :aspect:`Default:`    null
   :sep:`|`

   Using addJsFile will only allow you to bind in a single JavaScript asset
   file. Using includeJsFiles allows you to bind multiple files.


addJsInlineLabels
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       array
   :sep:`|` :aspect:`Default:`    null
   :sep:`|`

   Each value must correspond to a key from the locallang.xml/xlf file. The
   matching translation will then be available in the backend.


Examples
========

Simple
------

"your module content" wrapped with proper head & body tags.
Default backend CSS styles and JavaScript will be included.

::

   <f:be.container>your module content</f:be.container>

All options
-----------

"your module content" wrapped with proper head & body tags. Custom CSS file
:file:`EXT:your_extension/Resources/Public/Css/styles.css` and JavaScript files
:file:`EXT:your_extension/Resources/Public/JavaScript/Library1.js` and
:file:`EXT:your_extension/Resources/Public/JavaScript/Library2.js` will be
loaded, plus ExtJS and jQuery and some inline labels for usage in JS code.

::

   <f:be.container pageTitle="foo" 
                   enableClickMenu="false" 
                   loadExtJs="true" 
                   loadExtJsTheme="false" 
                   enableExtJsDebug="true" 
                   loadJQuery="true" 
                   includeCssFiles="{0: '{f:uri.resource(path:\'Css/Styles.css\')}'}" 
                   includeJsFiles="{
                      0: '{f:uri.resource(path:\'JavaScript/Library1.js\')}', 
                      1: '{f:uri.resource(path:\'JavaScript/Library2.js\')}'}" 
                   addJsInlineLabels="{
                      0: 'label1', 
                      1: 'label2'}"
   >
      your module content
   </f:be.container>
