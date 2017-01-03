.. include:: ../../../Includes.txt

f:format.date
=============

This `f:format.date` viewhelper can produce date-time strings in a variety of formats.

Properties
----------

date
~~~~
:aspect:`Type`
   `date` must be a `DateTime` object, or a string that can be converted to a `DateTime` object, or
   an integer Unix timestamp.

:aspect:`Description`

   `'17.01.1979'` for example is accepted whereas `'17.01.79'` will not work.

   `date` can be a textual relative time description such as `'now'` or `'-1 year'` or `'next Thursday'`.

   If `date` is `null` the ViewHelper returns an empty string.

   As of TYPO3 CMS 7 `date` defaults to `now` if it is an empty string.

   If `date` is an integer it is considered to be a Unix timestamp that gets converted to a `DateTime` object
   with the PHP default timezone applied. The timezone is determined by the PHP
   function :php:`date_default_timezone_get()`. Recommended reading:
   `PHP: Getting the default timezone <http://php.net/manual/en/function.date-default-timezone-get.php>`__.

:aspect:`Default value`
   NULL

:aspect:`Mandatory`
   No

format
~~~~~~
:aspect:`Type`
   String

:aspect:`Description`
   `format` is a string that describes the desired form of the produced date-time string.
   If there is at least one % character in the format string, the rules of PHP's `strftime()
   <https://secure.php.net/manual/en/function.strftime.php>`__ will be used.
   Otherwise the rules of PHP's `date() function <http://php.net/manual/en/function.date.php>`__
   will be applied.


:aspect:`Default value`
   The basic default is `'Y-m-d'`

   This can be overridden by setting :php:`$GLOBALS['TYPO3_CONF_VARS']['SYS']['ddmmyy'] = 'd-m-Y';` , for example.

:aspect:`Mandatory`
    No

.. highlight:: html

Examples
--------

Day Month Year
~~~~~~~~~~~~~~

Convert `dd.mm.yyyy`to `d/m/y`::

   <f:format.date date="17.01.1979" format="d/m/y" />

Now
~~~

::

   <f:format.date date="now" format="d/m/y" />


Format Unix timestamps
~~~~~~~~~~~~~~~~~~~~~~

::

   <f:format.date format="d.m.Y">@1334439765</f:format.date>
   <f:format.date format="d.m.Y">1334439765</f:format.date>


Format defaults
~~~~~~~~~~~~~~~~~~~~~~~~

::

   <f:format.date>{dateObject}</f:format.date>
   <f:format.date>now</f:format.date>


Hours:minutes
~~~~~~~~~~~~~

::

   <f:format.date format="H:i">{dateObject}</f:format.date>



A more complex textual relative time
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

::

   <f:format.date format="d.m.Y - H:i:s">+1 week 2 days 4 hours 2 seconds</f:format.date>


Localized time using strftime syntax
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

::

   <f:format.date format="%d. %B %Y">{dateObject}</f:format.date>
   <f:format.date format="%d. %B %Y">now</f:format.date>


Inline notation
~~~~~~~~~~~~~~~

::

   {f:format.date(date: dateObject)}
   {f:format.date(date: dateObject format: "%d. %B %Y")}
   {f:format.date(date: "now" format: "%c")}


More inline notation
~~~~~~~~~~~~~~~~~~~~

::

   {dateObject -> f:format.date()}
   {dateObject -> f:format.date(format: 'Y-m-d H:i:s')}

