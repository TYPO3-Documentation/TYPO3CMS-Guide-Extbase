.. include:: ../../../Includes.txt

f:uri.email
===========

With this ViewHelper you can link to an email address. If you enabled
email encryption in TypoScript that will be recognized here too.

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

Examples
--------

Just the email::

   {f:uri.email(email: 'my@email.tld')}

With custom linktext::

   <f:uri.email email="my@email.tld">Email</f:uri.email>
