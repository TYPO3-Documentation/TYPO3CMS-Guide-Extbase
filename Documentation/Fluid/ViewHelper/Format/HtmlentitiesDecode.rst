.. include:: ../../../Includes.txt

f:format.htmlentitiesDecode
===========================

Applies html_entity_decode() to a value.
http://www.php.net/html_entity_decode

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

keepQuotes
~~~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    If TRUE, single and double quotes won't be replaced (sets ENT_NOQUOTES flag).

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No

encoding
~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Generally TYPO3 uses the UTF-8 charset. But if you need an other charset for a special case, you can enter it here.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

Example
-------

::

 <p><f:format.htmlentitiesDecode>M&uuml;ller &amp; Breuer</f:format.htmlentitiesDecode>

In the HTML source code you can see a clean: "Müller & Breuer".
