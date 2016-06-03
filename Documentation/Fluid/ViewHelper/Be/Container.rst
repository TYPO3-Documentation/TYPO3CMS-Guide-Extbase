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

pageTitle
~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Backend modules are loaded in an HTML frame, so it's not essential to define an HTML page title. If you want to, then this is the property to use.

:aspect:`Default value`
     Empty string

:aspect:`Required`
     No

enableJumpToUrl
~~~~~~~~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    Activate this parameter if you want to use the ActionMenu ViewHelper. This loads the necessary 
                 JavaScript assets.

:aspect:`Default value`
     TRUE

:aspect:`Required`
     No

enableClickMenu
~~~~~~~~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    When active, this property loads the JavaScript for context menu functionality.

:aspect:`Default value`
     TRUE

:aspect:`Required`
     No

loadPrototype
~~~~~~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    When active, the Prototype JS framework will be loaded.

:aspect:`Default value`
     TRUE

:aspect:`Required`
     No

loadScriptaculous
~~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    When active, the Scriptaculous extension to Prototype JS will be loaded.

:aspect:`Default value`
     FALSE

:aspect:`Required`
     No

scriptaculousModule
~~~~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Using this option, you can load additional JavaScript modules for Scriptaculous.

:aspect:`Default value`
     Empty string

:aspect:`Required`
     No

loadExtJs
~~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    When active, the ExtJS framework will be loaded.

:aspect:`Default value`
     FALSE

:aspect:`Required`
     No

loadExtJsTheme
~~~~~~~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    When active, templates for the graphical elements of the ExtJs framework will be loaded.

:aspect:`Default value`
     TRUE

:aspect:`Required`
     No

extJsAdapter
~~~~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    You can use this property to define a different adaptor instead of the standard, Extbase.

:aspect:`Default value`
     Empty string

:aspect:`Required`
     No

enableExtJsDebug
~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    This property should only be activated during a development process involving ExtJS.

:aspect:`Default value`
     FALSE

:aspect:`Required`
     No

addCssFile
~~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Bind a specific CSS asset file to the view.

:aspect:`Default value`
     NULL

:aspect:`Required`
     No

addJsFile
~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Bind a specific JavaScript asset file to the view.

:aspect:`Default value`
     NULL

:aspect:`Required`
     No

loadJQuery
~~~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    When active, jQuery will be loaded.

:aspect:`Default value`
     FALSE

:aspect:`Required`
     No

includeCssFiles
~~~~~~~~~~~~~~~
:aspect:`Variable type`
    Array

:aspect:`Description`
    Using addCssFile will only allow you to bind in a single CSS asset file. Using includeCssFiles allows you to bind multiple files.

:aspect:`Default value`
     NULL

:aspect:`Required`
     No

includeJsFiles
~~~~~~~~~~~~~~
:aspect:`Variable type`
    Array

:aspect:`Description`
    Using addJsFile will only allow you to bind in a single JavaScript asset file. Using includeCssFiles allows you to bind multiple files.

:aspect:`Default value`
     NULL

:aspect:`Required`
     No

addJsInlineLabels
~~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    Array

:aspect:`Description`
    Each value must correspond to a key from the locallang.xml/xlf file. The matching translation will then be available in the backend.

:aspect:`Default value`
     NULL

:aspect:`Required`
     No
