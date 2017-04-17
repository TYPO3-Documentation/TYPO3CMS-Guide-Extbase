.. include:: ../../../Includes.txt

f:format.nl2br
==============

This ViewHelper is a wrapper for PHPs nl2br function.
All CHR(10) linebreaks are translated in <br /> tags.

Properties
----------

value
~~~~~

:aspect:`Variable type`
    String

:aspect:`Description`
    The string to format.

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No

Example
-------

::

 <f:format.nl2br>Text
 with
 linebreaks</f:format.nl2br>

ergibt

::

 Text<br />with<br />linebreaks
