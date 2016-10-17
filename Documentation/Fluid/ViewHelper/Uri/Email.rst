.. include:: ../../../Includes.txt

f:uri.email
===========

With this ViewHelper you can link to an email address. If you enabled the email encryption in TypoScript, it will be recognized here, too.

Properties
----------

email
~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    The email address to link to

:aspect:`Default value`

:aspect:`Mandatory`
    Yes

Example
--------

::

 {f:uri.email(email: 'my@email.tld')}
 
::

  <f:uri.email email="my@email.tld">Email</f:uri.email>
