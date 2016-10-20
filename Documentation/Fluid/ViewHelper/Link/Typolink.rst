.. include:: ../../../Includes.txt

f:link.typolink
===============

Render a link using the builtin "Typolink method"


Properties
----------

The UniversalTagAttributes :ref:`UniversalTagAttributes`

Plus:

Exclusive properties for the HTML-Element
#########################################

target
~~~~~~

:aspect:`Variable type`
    String

:aspect:`Description`
    What Window shall be used to open the link?

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No


Exclusive properties of this ViewHelper
#######################################

parameter
~~~~~~~~~

:aspect:`Variable type`
    String

:aspect:`Description`
    UID of the target page to link to.
    TypoScript-Syntax is expected like `19 _blank`.
    See :ref:`t3tsref:stdwrap-typolink`

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    Yes


additionalParams
~~~~~~~~~~~~~~~~

:aspect:`Variable type`
    String

:aspect:`Description`
    Add more parameters to the link. Opposed to `arguments` these names will not be
    prefixed with the extension name.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No


additionalAttributes
~~~~~~~~~~~~~~~~~~~~

:aspect:`Variable type`
    Array

:aspect:`Description`
   To add attributes to the 'ATag'. The array will automatically be converted to TypoScript syntax Param1=Wert Param2=Wert

:aspect:`Default value`
    Empty array

:aspect:`Mandatory`
    No


.. highlight:: html

Example
-------

Fluid::

   <f:link.typolink parameter="{link}">Linktext</f:link.typolink>

We assume that :html:`{link}` has the string value `19 _blank - "testtitle with whitespace" &X=y`.
The linkwizzard in the backend for example uses strings like this.

Result::

   <a href="index.php?id=19&X=y" title="testtitle with whitespace" target="_blank">Linktext</a>

Full configuration::

   <f:link.typolink parameter="{link}" target="_blank" class="ico-class"
    title="some title" additionalParams="&u=b" additionalAttributes="{type:'button'}"
    >Linktext</f:link.typolink>

Result::

   <a href="index.php?id=19&X=y&u=b" title="some title" target="_blank"
   class="ico-class" type="button">Linktext</a>
