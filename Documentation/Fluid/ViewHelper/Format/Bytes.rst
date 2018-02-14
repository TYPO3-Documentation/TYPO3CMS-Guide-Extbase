.. include:: ../../../Includes.txt

f:format.bytes
==============

This ViewHelper converts a value in bytes (integer) into a readable format.

Properties
----------

value
~~~~~
:aspect:`Variable type`
    Integer

:aspect:`Description`
    The integer value (bytes) to be converted.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

decimals
~~~~~~~~
:aspect:`Variable type`
    Integer

:aspect:`Description`
    The number of decimals to be shown after the decimal point.

:aspect:`Default value`
    0

:aspect:`Mandatory`
    No

decimalSeparator
~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    The character to use as the decimal separator.

:aspect:`Default value`
    .

:aspect:`Mandatory`
    No

thousandsSeparator
~~~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    The character to use as the “thousands” separator.

:aspect:`Default value`
    ,

:aspect:`Mandatory`
    No

units
~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Comma separated list of available units.

:aspect:`Default value`
    LocalizationUtility::translate('viewhelper.format.bytes.units', 'fluid')

:aspect:`Mandatory`
    No

Examples
--------

With a value of 1024.33, using the code 

::

 <f:format.bytes>{fileSize}</f:format.bytes>

will output

::

 1024 KB

With decimal and thousands separator

::

 {fileSize -> f:format.bytes(decimals: 2, decimalSeparator: '.', thousandsSeparator: ',')}

will output

::

 1,023.00 B

You may provide an own set of units, like this: B,KB,MB,GB,TB,PB,EB,ZB,YB

::

 {fileSize -> f:format.bytes(units: '{f:translate(id: \'viewhelper.format.bytes.units\', extensionName: \'fluid\')}')}

will output

::

 123 KB
