.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:format.currency
=================

This ViewHelper allows you to display a number in currency format.

Properties
-------------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Property
   :Datatype,20:    Variable type
   :Description,40: Description
   :Standard,10:    Default value
   :Mandatory,10:   Mandatory

 - :Property:    currencySign
   :Datatype:    String
   :Description: The currency symbol, for example £ or €. This symbol is usually appended after the numeric value.
   :Standard:    Empty string
   :Mandatory:   No

 - :Property:    decimalSeparator
   :Datatype:    String
   :Description: Decimal separator, which separates (for example) Euro and Cent.
   :Standard:    ,
   :Mandatory:   No

 - :Property:    thousandsSeparator
   :Datatype:    String
   :Description: Character to be used as a thousands separator.
   :Standard:    .
   :Mandatory:   No

 - :Property:    prependCurrency
   :Datatype:    Boolean
   :Description: Set to TRUE to indicate that the currency symbol should be placed before the numeric value.
   :Standard:    FALSE
   :Mandatory:   No

 - :Property:    separateCurrency
   :Datatype:    Boolean
   :Description: If this property is TRUE, a space character will be placed between the currency symbol and the numeric value.
   :Standard:    TRUE
   :Mandatory:   No

 - :Property:    decimals
   :Datatype:    Integer
   :Description: To how many decimal places should the number be rounded?
   :Standard:    2
   :Mandatory:   No

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
###############

::

 <f:format.currency currencySign="€" decimalSeparator="." thousandsSeparator="," prependCurrency="true">1122334455,66</f:format.currency>

produces: € 1,122,334,455.00