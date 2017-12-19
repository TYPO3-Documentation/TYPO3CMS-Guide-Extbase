.. include:: ../../../Includes.txt

f:format.urlencode
==================

Encodes the given string according to http://www.faqs.org/rfcs/rfc3986.html (applying PHPs rawurlencode() function).
http://www.php.net/manual/function.rawurlencode.php
Note: The output is not escaped. You may have to ensure proper escaping on your own.

Properties
----------

value
~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    String to format.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

Examples
--------

Default notation

::

 <f:format.urlencode>foo @+%/</f:format.urlencode>

 foo%20%40%2B%25%2F
 (urlencode() applied)

Inline notation

::

 {text -> f:format.urlencode()}

 Url encoded text
 (urlencode() applied)
