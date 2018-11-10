.. include:: ../../../Includes.txt

.. _vh-link-typolink:

f:link.typolink
===============

A ViewHelper to create links from fields supported by the link wizard.

.. _vh-link-typolink-properties:

Properties
----------

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

target
~~~~~~

:aspect:`Variable type`
    String

:aspect:`Description`
    What Window shall be used to open the link?

:aspect:`Default value`
    Empty string

:aspect:`Mandatory`
    No

class
~~~~~

:aspect:`Variable type`
    String

:aspect:`Description`
    The class to be added to the link.

:aspect:`Default value`
    Empty string

:aspect:`Mandatory`
    No

title
~~~~~

:aspect:`Variable type`
    String

:aspect:`Description`
    The title attribute of the link.

:aspect:`Default value`
    Empty string

:aspect:`Mandatory`
    No

additionalParams
~~~~~~~~~~~~~~~~

:aspect:`Variable type`
    String

:aspect:`Description`
    Add more parameters to the link. Opposed to `arguments` these names will not be
    prefixed with the extension name.

:aspect:`Default value`
    Empty string

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

useCacheHash
~~~~~~~~~~~~

:aspect:`Variable type`
    Boolean

:aspect:`Description`


:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No

addQueryString
~~~~~~~~~~~~~~~~~~~~

:aspect:`Variable type`
    Boolean

:aspect:`Description`
   If set, the current query parameters will be kept in the URI.

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No
	
addQueryStringMethod
~~~~~~~~~~~~~~~~~~~~

:aspect:`Variable type`
    String

:aspect:`Description`
	If set to GET or POST, then the parsed query arguments
	(GET or POST data) will be used. This setting is useful, if you use
	URL processing extensions like Real URL, which translate part of the
	path into query arguments.

	It's also possible to get both, POST and GET data, on setting this to

	"POST,GET" or "GET,POST". The last method in this sequence takes
	precedence and overwrites the parts that are also present for the
	first method.

:aspect:`Default value`
    GET

:aspect:`Mandatory`
    No
	
addQueryStringExclude
~~~~~~~~~~~~~~~~~~~~

:aspect:`Variable type`
    Boolean

:aspect:`Description`
   List of query arguments to exclude from the link. Typical examples are 'L' or 'cHash'.

:aspect:`Default value`
    Empty string

:aspect:`Mandatory`
    No
	
absolute
~~~~~~~~~~~~~~~~~~~~

:aspect:`Variable type`
    Boolean

:aspect:`Description`
   If set, the URI of the rendered link is absolute.

:aspect:`Default value`
    GET

:aspect:`Mandatory`
    No

.. highlight:: html

.. _vh-link-typolink-example:

Example
-------

Minimal example
###############


::

   <f:link.typolink parameter="{link}">Linktext</f:link.typolink>

We assume that :html:`{link}` has the string value `19 _blank - "testtitle with whitespace" &X=y`.
The linkwizzard in the backend for example uses strings like this.

Result

::

   <a href="index.php?id=19&X=y" title="testtitle with whitespace" target="_blank">Linktext</a>

Full configuration
##################

::

   <f:link.typolink parameter="{link}" target="_blank" class="ico-class"
    title="some title" additionalParams="&u=b" additionalAttributes="{type:'button'}"
    >Linktext</f:link.typolink>

Result

::

   <a href="index.php?id=19&X=y&u=b" title="some title" target="_blank"
   class="ico-class" type="button">Linktext</a>
