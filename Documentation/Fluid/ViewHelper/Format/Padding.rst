.. include:: ../../../Includes.txt

f:format.padding
================

Formats a string using PHPs str_pad function.
http://www.php.net/manual/en/function.str_pad.php

Properties
----------

value
~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    String to format

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

padLength
~~~~~~~~~
:aspect:`Variable type`
    Integer

:aspect:`Description`
    Length of the resulting string. If the value of pad_length is negative or less than the length of the input string,
    no padding takes place.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    Yes

padString
~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    The padding string.

:aspect:`Default value`
    Space

:aspect:`Mandatory`
    No

padType
~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Append the padding at this site (Possible values: right, left, both).

:aspect:`Default value`
    'right'

:aspect:`Mandatory`
    No

Examples
--------

Defaults

::

 <f:format.padding padLength="10">TYPO3</f:format.padding>

 TYPO3     (note the trailing whitespace)

Specify padding string

::

 <f:format.padding padLength="10" padString="-=">TYPO3</f:format.padding>

 TYPO3-=-=-

Specify padding type

::

 <f:format.padding padLength="10" padString="-" padType="both">TYPO3</f:format.padding>

 --TYPO3---
