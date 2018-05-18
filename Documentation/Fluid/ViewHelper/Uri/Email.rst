.. include:: ../../../Includes.txt

.. _vh-uri-email:

f:uri.email
===========

With this ViewHelper you can create a URI for an email address. If you need
a ViewHelper for creating a link, look at :ref:`vh-link-email`.


If you enabled email encryption in TypoScript that will be recognized
here too.

.. _vh-uri-email-properties:

Properties
----------

email
~~~~~

:aspect:`Variable type`
    String

:aspect:`Description`
    The email address to link to

:aspect:`Mandatory`
    Yes


.. highlight:: html

.. _vh-uri-email-examples:

Examples
--------

Just the email::
~~~~~~~~~~~~~~~~

   {f:uri.email(email: 'my@email.tld')}

With custom linktext::
~~~~~~~~~~~~~~~~~~~~~~

   <f:uri.email email="my@email.tld">Email</f:uri.email>
