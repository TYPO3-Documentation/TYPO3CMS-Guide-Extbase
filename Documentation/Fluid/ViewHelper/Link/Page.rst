.. include:: ../../../Includes.txt

f:link.page
===========

A view helper for creating links to TYPO3 pages.

Properties
----------

All the :ref:`universal tag attributes <UniversalTagAttributes>`

Exclusive properties for the HTML-Element
#########################################

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

Exclusive properties of this ViewHelper
#######################################

pageUid
~~~~~~~
:aspect:`Variable type`
    Integer|NULL

:aspect:`Description`
    Target page. See TypoLink destination.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

additionalParams
~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    Array

:aspect:`Description`
    Query parameters to be attached to the resulting URI.

:aspect:`Default value`
    Leeres Array

:aspect:`Mandatory`
    No

pageType
~~~~~~~~
:aspect:`Variable type`
    Integer

:aspect:`Description`
    Type of the target page. See typolink.parameter.

:aspect:`Default value`
    0

:aspect:`Mandatory`
    No

noCache
~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    Set this to disable caching for the target page. You should not need this.

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No

noCacheHash
~~~~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    Set this to suppress the `cHash` query parameter created by TypoLink. You should not need this.

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No

section
~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    The anchor to be added to the URI.

:aspect:`Default value`
    Leerer String

:aspect:`Mandatory`
    No

linkAccessRestrictedPages
~~~~~~~~~~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    If set, links pointing to access restricted pages will still link to the page even though the page cannot be accessed.

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No

absolute
~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    If set, the URI of the rendered link is absolute.

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No

addQueryString
~~~~~~~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    If set, the current query parameters will be kept in the URI.
    
    .. attention::

       This property should not be used for cached contents without a valid
       cHash. Otherwise the page is cached for the first set of parameters
       and subsubsequently taken from the cache no matter what parameters
       are given. Additionally the security risk of cache poisoning has to
       be considered.


:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No

argumentsToBeExcludedFromQueryString
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    Array

:aspect:`Description`
    Arguments to be removed from the URI. Only active if $addQueryString = TRUE.

:aspect:`Default value`
    Leeres Array

:aspect:`Mandatory`
    No

addQueryStringMethod
~~~~~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Set which parameters will be kept. Only active if $addQueryString = TRUE.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No


Examples
--------

Link to the current page

::

 <f:link.page>page link</f:link.page>

 <a href="index.php?id=123">page link</a>
 (depending on the current page and your TS configuration)

Query parameters

::

 <f:link.page pageUid="1" additionalParams="{foo: 'bar'}">page link</f:link.page>

 <a href="index.php?id=1&foo=bar">page link</a>
 (depending on your TS configuration)

Query parameters for extensions

::

 <f:link.page pageUid="1" additionalParams="{extension_key: {foo: 'bar'}}">page link</f:link.page>

 <a href="index.php?id=1&extension_key[foo]=bar">page link</a>
 (depending on your TS configuration)
