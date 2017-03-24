.. include:: ../../../Includes.txt

f:be.pageRenderer
=================

The first question you should ask yourself is whether you want to build something using the existing TYPO3 interface, or
build something completely bespoke. If you're making a bespoke interface, then you don't need this ViewHelper at all.
In this event, bind your own JavaScript and CSS assets yourself.

However, if you want to build Extbase modules using the standard TYPO3 interface, thereby providing a close integration and
compatibility with other modules, then use this ViewHelper. In essence, you only need to use two rows of code and around
ten properties.

Properties
----------

pageTitle
~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    'title' tag of the module. Not required by default, as BE modules are shown in a frame.

:aspect:`Default value`
    Empty string

:aspect:`Required`
    No

loadExtJs
~~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    Specifies whether to load ExtJS library.
    This option will be removed in TYPO3 v9.

:aspect:`Default value`
    FALSE

:aspect:`Required`
    No

loadExtJsTheme
~~~~~~~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    Whether to load ExtJS "grey" theme.
    This option will be removed in TYPO3 v9.

:aspect:`Default value`
    TRUE

:aspect:`Required`
    No

enableExtJsDebug
~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    If set to TRUE, the debug version of ExtJS is loaded. Use this for development only.
    This option will be removed in TYPO3 v9.

:aspect:`Default value`
    FALSE

:aspect:`Required`
    No

loadJQuery
~~~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    Whether to load jQuery library.
    This option will be removed in TYPO3 v9.

:aspect:`Default value`
    FALSE

:aspect:`Required`
    No

includeCssFiles
~~~~~~~~~~~~~~~
:aspect:`Variable type`
    Array

:aspect:`Description`
    List of custom CSS files to be loaded.

:aspect:`Default value`
    NULL

:aspect:`Required`
    No

includeJsFiles
~~~~~~~~~~~~~~
:aspect:`Variable type`
    Array

:aspect:`Description`
    List of custom JavaScript files to be loaded.

:aspect:`Default value`
    NULL

:aspect:`Required`
    No

addJsInlineLabels
~~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    Array

:aspect:`Description`
    Custom labels to add to JavaScript inline labels.

:aspect:`Default value`
    NULL

:aspect:`Required`
    No

includeRequireJsModules
~~~~~~~~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    Array

:aspect:`Description`
    List of RequireJS modules to be loaded.

:aspect:`Default value`
    NULL

:aspect:`Required`
    No

jQueryNamespace
~~~~~~~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Store the jQuery object in a specific namespace.
    This option will be removed in TYPO3 v9.

:aspect:`Default value`
    Empty string

:aspect:`Required`
    No


Examples
--------

All options
~~~~~~~~~~~

Custom CSS file EXT:your_extension/Resources/Public/Css/styles.css and JavaScript files
EXT:your_extension/Resources/Public/JavaScript/Library1.js and EXT:your_extension/Resources/Public/JavaScript/Library2.js
will be loaded, plus ExtJS and jQuery and some inline labels for usage in JS code.

::

    <f:be.pageRenderer pageTitle="foo" loadExtJs="true" loadExtJsTheme="false" extJsAdapter="jQuery" enableExtJsDebug="true" loadJQuery="true" includeCssFiles="0: '{f:uri.resource(path:\'Css/Styles.css\')}'" includeJsFiles="0: '{f:uri.resource(path:\'JavaScript/Library1.js\')}', 1: '{f:uri.resource(path:\'JavaScript/Library2.js\')}'" addJsInlineLabels="{0: 'label1', 1: 'label2'}" />
