.. include:: ../../../Includes.txt

f:format.case
=============

Modifies the case of an input string to upper- or lowercase or capitalization.

The default transformation will be uppercase as in `mb_convert_case` [http://php.net/manual/function.mb-convert-case.php].

Note that the behavior will be the same as in the appropriate PHP function `mb_convert_case`;
especially regarding locale and multibyte behavior.

Properties
----------

value
~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    The input value. If not given, the evaluated child nodes will be used.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

mode
~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    The case to apply, must be one of this' CASE_* constants. Defaults to uppercase application.
    Possible modes are:

    `CASE_LOWER = 'lower'`
    Transforms the input string to its lowercase representation

    `CASE_UPPER = 'upper'`
    Transforms the input string to its uppercase representation

    `CASE_CAPITAL = 'capital`
    Transforms the input string to its first letter upper-cased, i.e. capitalization

    `CASE_UNCAPITAL = 'uncapital'`
    Transforms the input string to its first letter lower-cased, i.e. uncapitalization

    `CASE_CAPITAL_WORDS = 'capitalWords'`
    Not supported yet: Transforms the input string to each containing word being capitalized

:aspect:`Default value`
    self::CASE_UPPER

:aspect:`Mandatory`
    No

Examples
--------

Some Text with mixed case

::

   <f:format.case>Some Text with miXed case</f:format.case>

   SOME TEXT WITH MIXED CASE

Example with given mode

::

   <f:format.case mode="capital">someString</f:format.case>

   SomeString
   
Example: inline notation

::

   {f:format.case(mode: 'lower', value: 'UPPERCASE STRING')}
   
   Output: uppercase string
 
::

   {myVar -> f:format.case(mode: 'lower')}
   
