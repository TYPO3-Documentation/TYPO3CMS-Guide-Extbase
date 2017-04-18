.. include:: ../../../Includes.txt

f:link.external
===============

A ViewHelper for creating links to external targets.

.. tip::

   Wenn Ihr bei uri einen vollständigen Link angebt, also inkl. http:// oder ftp://,
   dann braucht Ihr defaultScheme nicht zu setzen.

Properties
----------

All the :ref:`universal tag attributes <UniversalTagAttributes>`

Exclusive properties for the HTML-Element
#########################################

name
~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Specifies the name of an anchor.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

rel
~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Specifies the relationship between the current document and the linked document.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

rev
~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Specifies the relationship between the linked document and the current document.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

target
~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Specifies where to open the linked document.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

Exclusive properties of this ViewHelper
#######################################

uri
~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    The URI that will be put in the href attribute of the rendered link tag.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    Yes

defaultScheme
~~~~~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Scheme the href attribute will be prefixed with if specified $uri does not contain a scheme already.

:aspect:`Default value`
    'http'

:aspect:`Mandatory`
    No

Examples
--------

::

 <f:link.external uri="http://www.typo3.org" target="_blank">external link</f:link.external>

 <a href="http://www.typo3.org" target="_blank">external link</a>

Custom default scheme

::

 <f:link.external uri="typo3.org" defaultScheme="ftp">external ftp link</f:link.external>

 <a href="ftp://typo3.org">external ftp link</a>
