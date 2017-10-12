.. include:: ../../Includes.txt

f:translate
===========

This ViewHelper connects to a standard translation file - most often locallang.xlf - and provides a defined
translation for the current language using a “key” parameter.

Properties
----------

key
~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    The key by which the translation is referenced in the translation file.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    Yes

default
~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
   If the key canto be matched in the translation file, then use this text instead. If this property isn't
   defined, then the value between the opening and closing `f:translate` tags will be used.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    Yes

htmlEscape
~~~~~~~~~~

.. attention::

   Property `htmlEscape` doesn't exist any more. Html escaping is now done by default.
   To suppress that wrap the `f:translate` in a `<f:format.raw>` viewhelper.

arguments
~~~~~~~~~
:aspect:`Variable type`
    Array

:aspect:`Description`
   Placeholders can be set in the strings within the translation file, which will be replaced with the
   content of the array passed in this property.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    Yes

This ViewHelper accesses files in the folder Resources/Private/Language. If you're using FLUIDTEMPLATE, you'll need to
use the following path syntax::



   LLL:fileadmin/templates/locallang.xlf:domain_model_whatever.title

or, in the case of an extension::

   LLL:EXT:myExtension/Resources/Private/Language/locallang.xml:domain_model_whatever.title

FLUIDTEMPLATE users can make their lives easier by applying the following settings via TypoScript:

.. code-block:: typoscript

   extbase.pluginName = Pi1
   extbase.controllerExtensionName = MyExtension

Then it's enough to just use the key, without the entire LLL path.

Examples
--------

Basic
~~~~~

::

 <f:translate key="domain_model.title" />

With full file path
~~~~~~~~~~~~~~~~~~~

::

 <f:translate key="LLL:fileadmin/lang/locallang.xlf:domain_model.title" />

With placeholders
~~~~~~~~~~~~~~~~~

In the template::

 <f:translate key="LLL:fileadmin/lang/locallang.xml:domain_model.bestfilm" arguments="{0: 'Back to the Future'}" />

In locallang.xlf::

   <trans-unit id="domain_model.bestfilm" approved="yes">
      <source>Best film ever: %s</source>
   </trans-unit>

%s will be replaced with the first array entry. If %s is used more than once, then each array entry will be applied
sequentially. In order to be more specific about which placeholders are replaced by which array values, use the more
specific placeholder syntax::

   <f:translate key="LLL:fileadmin/lang/locallang.xml:domain_model.bestfilm" arguments="{0: 'Back to the Future', 1: '1985'}" />

and::

   <label index="domain_model.bestfilm">Best film ever: %1$s from %2$s.</label>

You can find more information about placeholder replacement in sprintf() documentation (e.g. at php.net).
