.. include:: ../../../Includes.txt

f:uri.external
==============

This ViewHelper creates a link to an external page

.. tip::

   If you set an absolute URL (e.g. with http:// or ftp://) you don't need to set ``defaultScheme``

Properties
----------

uri
~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    URL to the targe page

:aspect:`Default value`

:aspect:`Mandatory`
    Yes

defaultScheme
~~~~~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    You can set the scheme for this link, e.g. ftp or https

:aspect:`Default value`
    http

:aspect:`Mandatory`
    No

Example
--------

:: 

 {f:uri.external(uri: 'www.example.com', defaultScheme: 'https')}
