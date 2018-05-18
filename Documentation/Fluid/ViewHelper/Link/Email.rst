.. include:: ../../../Includes.txt

.. _vh-link-email:

f:link.email
============

Email link ViewHelper.
Generates an email link incorporating TYPO3s spamProtectEmailAddresses-settings.

.. _vh-link-email-properties:

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

email
~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    The email address to be turned into a link.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    Yes


.. _vh-link-email-examples:

Examples
--------

Basic email link
################

.. code-block:: html

 <f:link.email email="foo@bar.tld" />

Result:

.. code-block:: html

 <a href="javascript:linkTo_UnCryptMailto('ocknvq,hqqBdct0vnf');">foo(at)bar.tld</a>
 (depending on your spamProtectEmailAddresses-settings)

Email link with custom linktext
###############################

.. code-block:: html

 <f:link.email email="foo@bar.tld">some custom content</f:link.email>

Result:

.. code-block:: html

 <a href="javascript:linkTo_UnCryptMailto('ocknvq,hqqBdct0vnf');">some custom content</a>
