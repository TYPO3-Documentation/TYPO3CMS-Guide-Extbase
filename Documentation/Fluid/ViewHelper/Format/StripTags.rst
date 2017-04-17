.. include:: ../../../Includes.txt

f:format.stripTags
==================

Removes tags from the given string (applying PHPs strip_tags() function).
http://www.php.net/manual/function.strip-tags.php

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

allowedTags
~~~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Optional string of allowed tags as required by PHPs strip_tags() function.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

Examples
--------

Default notation

::

 <f:format.stripTags>Some Text with <b>Tags</b> and an &Uuml;mlaut.</f:format.stripTags>

 Some Text with Tags and an &Uuml;mlaut.
 (strip_tags() applied. Note: encoded entities are not decoded)

Inline notation

::

 {text -> f:format.stripTags()}

 Text without tags
 (strip_tags() applied)
