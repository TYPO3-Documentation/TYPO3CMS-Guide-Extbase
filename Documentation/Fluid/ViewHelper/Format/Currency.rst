.. include:: ../../../Includes.txt

f:format.currency
=================

This ViewHelper allows you to display a number in currency format.

Properties
----------

currencySign
~~~~~~~~~~~~

:aspect:`Variable type`
    String

:aspect:`Description`
    The currency symbol, for example £ or €. This symbol is usually appended after the numeric value.

:aspect:`Default value`
    Empty string

:aspect:`Mandatory`
    No

decimalSeparator
~~~~~~~~~~~~~~~~

:aspect:`Variable type`
    String

:aspect:`Description`
    Decimal separator, which separates (for example) Euro and Cent.

:aspect:`Default value`
    ,

:aspect:`Mandatory`
    No

thousandsSeparator
~~~~~~~~~~~~~~~~~~

:aspect:`Variable type`
    String

:aspect:`Description`
    Character to be used as a thousands separator.

:aspect:`Default value`
    .

:aspect:`Mandatory`
    No

prependCurrency
~~~~~~~~~~~~~~~

:aspect:`Variable type`
    Boolean

:aspect:`Description`
    Set to TRUE to indicate that the currency symbol should be placed before the numeric value.

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No

separateCurrency
~~~~~~~~~~~~~~~~

:aspect:`Variable type`
    Boolean

:aspect:`Description`
    If this property is TRUE, a space character will be placed between the currency symbol and the numeric value.

:aspect:`Default value`
    TRUE

:aspect:`Mandatory`
    No

decimals
~~~~~~~~

:aspect:`Variable type`
    Integer

:aspect:`Description`
    To how many decimal places should the number be rounded?

:aspect:`Default value`
    2

:aspect:`Mandatory`
    No

Two important pieces of information:

If you pass an empty string to this ViewHelper, it takes 23 milliseconds to return a value. If you pass in 0.00 as a value,
then it'll be finished in 1-2 milliseconds. Take care when working with long lists of values.

This ViewHelper doesn't accept values passed with a comma as a decimal separator. (Common in German and French usage.)


Examples
--------

::

   <f:format.currency currencySign="€" decimalSeparator="." thousandsSeparator="," prependCurrency="true">1122334455.66</f:format.currency>

produces: € 1,122,334,455.66

Non-float value
~~~~~~~~~~~~~~~

::

   <f:format.currency currencySign="€" decimalSeparator="." thousandsSeparator="," prependCurrency="true">1122334455,66</f:format.currency>

produces: `€ 1,122,334,455.00`