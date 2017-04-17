.. include:: ../../../Includes.txt

f:format.json
=============

This ViewHelper is a wrapper for PHPs json_encode function.

Properties
----------

value
~~~~~

:aspect:`Variable type`
    Mixed

:aspect:`Description`
    The incoming data to convert, or null if VH children should be used.

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No

forceObject
~~~~~~~~~~~

:aspect:`Variable type`
    Boolean

:aspect:`Description`
    Outputs an JSON object rather than an array.

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No


Examples
--------

Encoding a view variable

::

 {someArray -> f:format.json()}

 ["array","values"]

Associative array

::

 {f:format.json(value: {foo: 'bar', bar: 'baz'})}

 {"foo":"bar","bar":"baz"}

Non-associative array with forced object

::

 {f:format.json(value: {0: 'bar', 1: 'baz'}, forceObject: true)}

 {"0":"bar","1":"baz"}
