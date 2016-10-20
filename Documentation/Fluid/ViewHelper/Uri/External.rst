.. include:: ../../../Includes.txt

f:uri.external
==============

This ViewHelper creates a link to an external page

.. tip::

   If you specify an absolute URL like `http://` or `ftp://`
   you don't need to set `defaultScheme`.


Properties
----------

uri
~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    URL of the target page

:aspect:`Default value`

:aspect:`Mandatory`
    Yes


defaultScheme
~~~~~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    You can set the default scheme for this link, for example `ftp` or `https`

:aspect:`Default value`
    http

:aspect:`Mandatory`
    No


Example
-------

.. code-block:: html

   {f:uri.external(uri: 'www.example.com', defaultScheme: 'https')}

