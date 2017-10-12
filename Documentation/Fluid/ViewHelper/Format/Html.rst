.. include:: ../../../Includes.txt

f:format.html
=============

When you've created a Model for the `tt_content` table, data that you receive for the front end is raw and 
unformatted: just as it's stored in the database. So that you can parse this data and output it as you would by 
using `styles.content.get` in TypoScript, you can use this ViewHelper. It takes the unformatted content and runs it 
through a parser, providing you with the formatted output you need.
You can either specify a path to the TypoScript setting or set the parseFunc options directly.
By default `lib.parseFunc_RTE` is used to parse the string.

Properties
----------

parseFuncTSPath
~~~~~~~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Format a piece of text according to the configuration behind this TypoScript object path.

:aspect:`Default value`
    lib.parseFunc_RTE

:aspect:`Mandatory`
    No

Example
-------

::

 <f:format.html>{content.bodytext}</f:format.html>

Example with an alternative TypoScript object path
--------------------------------------------------

This specific alternative will format the text in the variable without passing it through `htmlspecialchars`.

::

 <f:format.html parseFuncTSPath="lib.parseFunc">{variable}</f:format.html>
