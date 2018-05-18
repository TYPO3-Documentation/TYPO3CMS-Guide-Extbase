.. include:: ../../../Includes.txt

.. _vh-uri-external:

f:uri.external
==============

This ViewHelper creates an URI for an external ressource. If you need
a ViewHelper for creating a link, look at :ref:`vh-link-external`.

.. tip::

   If you specify an absolute URL like `http://` or `ftp://`
   you don't need to set `defaultScheme`.


.. _vh-uri-external-properties:

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

.. _vh-uri-external-example:

Examples
--------

Example with https:
~~~~~~~~~~~~~~~~~~~

Fluid:

.. code-block:: html

   <f:uri.external uri="www.example.com" defaultScheme="https" />

Result:

    https://www.example.com

Example with inline notation:
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Fluid:

.. code-block:: html

   {f:uri.external(uri: 'www.example.com', defaultScheme: 'https')}

Result:

    https://www.example.com

