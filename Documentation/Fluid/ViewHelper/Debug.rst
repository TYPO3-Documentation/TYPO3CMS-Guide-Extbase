.. include:: ../../Includes.txt

f:debug
=======

This ViewHelper allows you to output the value of a variable or a set of variables (e.g. array) to the screen. This can 
be helpful when debugging, to make sure that the value of the variable is as you would expect it to be. Individual nested 
array or object attributes can be individually expanded.

Properties
----------

title
~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    You can use this property to give the debug output a title, so that it can more readily be identified. 
                 (For example, if you're going to output multiple debug blocks during the same request.)

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    Yes

maxDepth
~~~~~~~~
:aspect:`Variable type`
    Integer

:aspect:`Description`
    Extremely large arrays or deeply-nested objects can lead to TYPO3 being unable to build a complete view 
                 of the entire structure. By using the 'maxDepth' property, you can adjust the depth of the output to a 
                 maximum of 8 levels, in order to get around this problem. You can fine-tune the value of the property 
                 according to the performance of the server and the maximum processing time available.

:aspect:`Default value`
    8

:aspect:`Mandatory`
    No

plainText
~~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    If you're using the CLI mode, using this property will switch the output into plain text mode.

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No

ansiColors
~~~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    Some shell environments allow syntax highlighting - by activating the ansiColors mode, the debug 
                 output will be extended with control characters, so that the shell can implement highlighting. This 
                 option only works when 'plainText' mode is active.

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No

inline
~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    The debug output usually appears at the top of the page output. By setting this property, the output 
                 will appear at the point where the `f:debug` ViewHelper is inserted in the code.

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No

blacklistedClassNames
~~~~~~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    Array

:aspect:`Description`
    The use of this property highlights specific classes. It currently (?) doesn't work when Namespaces 
                 are in use.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

blacklistedPropertyNames
~~~~~~~~~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    Array

:aspect:`Description`
    The use of this property highlights specific object properties. It currently (?) doesn't work when 
                 Namespaces are in use.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

.. tip::

   Debugging aggregate root objects in earlier versions often lead to problems. Many objects are deeply nested or even 
   built recursively. This lead in many instances to the system exceeding the memory_limit or max_execution_time in 
   php.ini. In such cases, it's recommended to only debug a part of the object in question, or to first convert it to 
   an array.

Examples
--------

::

   <f:debug title="Results of customers query">{customers}</f:debug>

::

   {customers -> f:debug(title: "Results of customers query")}

::

   {f:debug(subject: customers, title: "Results of customers query")}
