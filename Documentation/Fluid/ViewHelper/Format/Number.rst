.. include:: ../../../Includes.txt

f:format.number
===============

Formats a number with custom precision, decimal point and grouped thousands.
http://www.php.net/manual/en/function.number-format.php

Properties
----------

decimals
~~~~~~~~
:aspect:`Variable type`
    Integer

:aspect:`Description`
    The number of digits after the decimal point.

:aspect:`Default value`
    2

:aspect:`Mandatory`
    No

decimalSeparator
~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    The decimal point character.

:aspect:`Default value`
    .

:aspect:`Mandatory`
    No

thousandsSeparator
~~~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    The character for grouping the thousand digits.

:aspect:`Default value`
    ,

:aspect:`Mandatory`
    No

Examples
--------

Defaults

::

 <f:format.number>423423.234</f:format.number>

 423,423.23


With all parameters

::

 <f:format.number decimals="1" decimalSeparator="," thousandsSeparator=".">423423.234</f:format.number>

 423.423,2


::

 <f:format.number decimals="3" decimalSeparator="." thousandsSeparator=",">1122334455.667788</f:format.number>

 1,122,334,455.668
