.. include:: ../../../Includes.txt

.. _vh-link-external:

f:link.external
===============

A ViewHelper for creating links to external targets.

.. tip::

   If you specify an absolute URL like `http://` or `ftp://`
   you don't need to set `defaultScheme`.

.. _vh-link-external-properties:

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

.. _vh-link-external-examples:

Examples
--------

.. code-block:: html

   <f:link.external uri="http://www.typo3.org" target="_blank">external link</f:link.external>

Result:

.. code-block:: html

    <a href="http://www.typo3.org" target="_blank">external link</a>

Custom default scheme
#####################

::

 <f:link.external uri="typo3.org" defaultScheme="ftp">external ftp link</f:link.external>


Result:

::

 <a href="ftp://typo3.org">external ftp link</a>
