.. include:: ../../../Includes.txt

f:format.date
=============

This Format/DateViewHelper produces date-time strings in a variety of formats.

Properties
----------

date
~~~~
:aspect:`Variable type`
    Mixed

:aspect:`Description`
    A DateTime object or a string this ViewHelper converts to a DateTime object. This date can be a textual relative time description. If date is null, this ViewHelper returns an empty string. If date is an empty string as of TYPO3 CMS 7, this ViewHelper treats date as 'now'. If date is an integer, this ViewHelper interprets the integer as a Unix timestamp, converts it to a DateTime object, then applies the default timezone from the PHP function date_default_timezone_get() (http://php.net/manual/en/function.date-default-timezone-get.php).

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

format
~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    The desired form of the produced time string. If there is at least one % character in the format string, this ViewHelper will use the rules of PHP's strftime() function (https://secure.php.net/manual/en/function.strftime.php). Otherwise, this ViewHelper will use the rules of PHP's date() function (http://php.net/manual/en/function.date.php).

:aspect:`Default value`
    Firstly the value in $GLOBALS['TYPO3_CONF_VARS']['SYS']['ddmmyy'] or lastly 'Y-m-d'.

:aspect:`Mandatory`
    No

base
~~~~
:aspect:`Variable type`
    Mixed

:aspect:`Description`
    A DateTime object or a string this ViewHelper converts to a DateTime object. This base can be an integer meant to represent a Unix timestamp. As of TYPO3 CMS 7, this ViewHelper uses base as the $now parameter in PHP's strtotime() function (http://php.net/manual/en/function.strtotime.php), where base provides a starting time for calculating textual relative time descriptions.

:aspect:`Default value`
    Now

:aspect:`Mandatory`
    No

Examples
--------

In these examples, dateObject could also be a string or integer. For instance, try 'now' for dateObject.

Day/month/year produced from day.month.year
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

::

 <f:format.date date="17.01.1979" format="d/m/y" />

Unix timestamp into day.month.year
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

::

 <f:format.date format="d.m.Y">@1334439765</f:format.date>
 <f:format.date format="d.m.Y">1334439765</f:format.date>

Format and base defaults
~~~~~~~~~~~~~~~~~~~~~~~~

::

 <f:format.date>{dateObject}</f:format.date>
 <f:format.date>now</f:format.date>

Hours:minutes
~~~~~~~~~~~~~

::

 <f:format.date format="H:i">{dateObject}</f:format.date>

A year ago from the base time
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

::

 <f:format.date format="Y" base="{dateObject}">-1 year</f:format.date>
 <f:format.date format="Y-m-d" base="2016-06-06">-1 year</f:format.date>
 <f:format.date format="Y-m-d" base="yesterday">-1 year</f:format.date>
 <f:format.date format="Y-m-d H:i:s" base="1334439765">-1 year</f:format.date>
 <f:format.date format="Y-m-d H:i:s" base="@1334439765">-1 year</f:format.date>

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

Another inline notation
~~~~~~~~~~~~~~~~~~~~~~~

::

 {dateObject -> f:format.date()}
 {dateObject -> f:format.date(format: 'Y-m-d H:i:s')}

