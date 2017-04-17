.. include:: ../../../Includes.txt

f:format.htmlentities
=====================

Escapes special characters with their escaped counterparts as needed using PHPs htmlentities() function.
http://www.php.net/manual/function.htmlentities.php

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

doubleEncode
~~~~~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    If FALSE existing html entities won't be encoded, the default is to convert everything.

:aspect:`Default value`
    TRUE

:aspect:`Mandatory`
    No

Beispiel
--------

::

 <f:format.htmlentities>Müller & Breuer</f:format.htmlentities>

::

 M&uuml;ller &amp; Breuer
