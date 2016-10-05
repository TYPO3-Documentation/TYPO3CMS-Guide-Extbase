.. include:: ../../../Includes.txt

f:format.date
=============

Konvertiert einen Timestamp in einen lesbaren Datumswert.

Properties
----------

date
~~~~
:aspect:`Variable type`
    Mixed

:aspect:`Description`
    Either an object of type DateTime, or a text/date which can be converted to a DateTime object. e.g. 17.01.1979 is acceptable, 17.01.79 isn't.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

format
~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    How should the date be output? The format syntax is identical to the strftime function in PHP (https://secure.php.net/manual/en/function.strftime.php).

:aspect:`Default value`
    Y-m-d

:aspect:`Mandatory`
    No

Although the process with DateTime objects is pretty good, make sure that the value is checked precisely. You can use 
online tools like a timestamp convertor, or validate the value by comparison with the value in your database. The 
documentation cites that if you want to convert a timestamp to a DateTime object, then prefix it with an @ character. 
I hope that I'm not explaining this incorrectly, but the timestamp will be converted according to RFC2822 in time zone 
zero (0). In Germany, for example, the resultant DateTime value will always be “behind” (as Germany is in a different 
time zone). You're better off converting the timestamp using ISO8601, so that the correct time zone is used. For my 
part, I wrote my own ViewHelper to use this method: Extbase uses this ISO format internally too. See:

::

 DataMapper->mapDateTime()

Excerpt: return new DateTime(date('c', $timestamp));

I'm not quite sure why this hasn't been implemented in this ViewHelper.

Example
--------

::

 <f:format.date date="17.01.1979" format="d/m/y" />

Example using a timestamp
-------------------------

::

 <f:format.date format="d.m.Y">@1334439765</f:format.date>

As mentioned: take care to take your national/continental time zone into account when using this ViewHelper.
