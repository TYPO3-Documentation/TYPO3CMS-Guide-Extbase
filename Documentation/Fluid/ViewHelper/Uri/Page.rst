.. include:: ../../../Includes.txt

.. _vh-uri-page:

==========
f:uri.page
==========

This ViewHelper creates a URI to a given page. If you need
a ViewHelper for creating a link, look at :ref:`vh-link-page`.

.. _vh-uri-page-properties:

Properties
==========

pageUid
-------

:aspect:`Variable type`
   Integer|NULL

:aspect:`Description`
   Links to this page UID.

:aspect:`Default value`
   NULL

:aspect:`Mandatory`
   No

additionalParams
----------------

:aspect:`Variable type`
   Array

:aspect:`Description`
   Adds additional parameters for the target page. Compared to `arguments` the variables can be added without extension key prefix.

:aspect:`Default value`
   Empty Array

:aspect:`Mandatory`
   No

pageType
--------

:aspect:`Variable type`
   Integer

:aspect:`Description`
   Links to this page type.

:aspect:`Default value`
   0

:aspect:`Mandatory`
   No

noCache
-------

:aspect:`Variable type`
   Boolean

:aspect:`Description`
   Prevents the caching of the called page.

:aspect:`Default value`
   FALSE

:aspect:`Mandatory`
   No

noCacheHash
-----------

:aspect:`Variable type`
   Boolean

:aspect:`Description`
   Prevents the additional cHash parameter added to the link.

:aspect:`Default value`
   FALSE

:aspect:`Mandatory`
   No

section
-------

:aspect:`Variable type`
   String

:aspect:`Description`
   Links to this anchor on the target page.

:aspect:`Default value`
   Empty string

:aspect:`Mandatory`
   No

linkAccessRestrictedPages
-------------------------

:aspect:`Variable type`
   Boolean

:aspect:`Description`
   Forces a link to a restricted page. Normally such links won't be generated.

:aspect:`Default value`
   FALSE

:aspect:`Mandatory`
   No

absolute
--------

:aspect:`Variable type`
   Boolean

:aspect:`Description`
   Creates an absolute link with domain name.

:aspect:`Default value`
   FALSE

:aspect:`Mandatory`
   No

addQueryString
--------------

:aspect:`Variable type`
   Boolean

:aspect:`Description`
   Adds all parameters to the target URL which are on the current page.

:aspect:`Default value`
   FALSE

:aspect:`Mandatory`
   No

argumentsToBeExcludedFromQueryString
------------------------------------

:aspect:`Variable type`
   Array

:aspect:`Description`
   Excludes all give arguments if `addQueryString` is active.

:aspect:`Default value`
   Empty array

:aspect:`Mandatory`
   No


Examples
========

.. code-block:: html

   <f:uri.page pageUid="1" additionalParams="{foo: 'bar'}">page link</f:uri.page>
