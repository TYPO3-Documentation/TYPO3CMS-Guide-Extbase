.. include:: ../../../Includes.txt

.. _vh-link-action:

f:link.action
=============

A ViewHelper for creating links to Extbase actions.

.. _vh-link-action-properties:

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

action
~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Target action.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

arguments
~~~~~~~~~
:aspect:`Variable type`
    Array

:aspect:`Description`
    Arguments to be added to the link.

:aspect:`Default value`
    Empty Array

:aspect:`Mandatory`
    No

controller
~~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Target controller. If NULL current controllerName is used.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

extensionName
~~~~~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Target Extension Name (without "tx_" prefix and no underscores). If NULL the current extension name is used.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

pluginName
~~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Target plugin. If empty, the current plugin name is used.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

pageUid
~~~~~~~
:aspect:`Variable type`
    Integer

:aspect:`Description`
    Target page. See TypoLink destination.

:aspect:`Default value`
    NULL

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
    Set this to suppress the cHash query parameter created by TypoLink. You should not need this.

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
    Empty String

:aspect:`Mandatory`
    No

format
~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    The requested format, e.g. ".html.

:aspect:`Default value`
    Empty String

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

additionalParams
~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    Array

:aspect:`Description`
    Additional query parameters that won't be prefixed like $arguments (overrule $arguments).

:aspect:`Default value`
    Empty Array

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
    Empty Array

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

Link to the show-action of the current controller
##################################################

.. code-block:: html

   <f:link.action action="show">action link</f:link.action>

Result:

.. code-block:: html

   <a href="index.php?id=123&tx_myextension_plugin[action]=show&tx_myextension_plugin[controller]=Standard&cHash=xyz">action link</f:link.action>

Depending on the current page and TypoScript configuration.

Link to download-action with multiple arguments
##################################################

.. code-block:: html

   <f:link.action action="download"
       arguments="{
                     uid: User.id,
                     name: User.name,
                     email: User.contact.email
                   }"
       target="_blank">Download
    </f:link.action>

Result:

.. code-block:: html

   <a target="_blank" href="/site/?extension_plugin%5Buid%5D=1234&amp;extension_plugin%5Bname%5D=Linda%20Test&amp;extension_plugin%5Bemail%5D=test%40testmail.com&amp;extension_plugin%5Baction%5D=download&amp;extension_plugin%5Bcontroller%5D=Standard&amp;cHash=xyz">Download</a>

Depending on the current page and TypoScript configuration.
