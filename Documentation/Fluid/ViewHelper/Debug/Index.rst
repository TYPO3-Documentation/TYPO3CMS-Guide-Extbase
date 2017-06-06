.. include:: ../../../Includes.txt

ViewHelper: Debug
=================

This ViewHelper generates a HTML dump of the tagged variable.

Properties
----------

title
~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    An optional custom title for the debug output.

:aspect:`Default value`

:aspect:`Mandatory`
    No

maxDepth
~~~~~~~~
:aspect:`Variable type`
    Integer

:aspect:`Description`
    Sets the max recursion depth of the dump.
    De- or increase the number according to your needs and memory limit.

:aspect:`Default value`
    8

:aspect:`Mandatory`
    No

plainText
~~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    If TRUE, the dump is in plain text, if FALSE the debug output is in HTML format.

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No

ansiColors
~~~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    If TRUE, ANSI color codes are added to the plaintext output, if FALSE the 
    plaintext debug output is not colored.

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No

inline
~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    If TRUE, the dump is rendered at the position of the <f:debug> tag. 
    If FALSE, the dump is displayed at the top of the page.

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No

blacklistedClassNames
~~~~~~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    Array

:aspect:`Description`
    An array of class names (RegEx) to be filtered.

:aspect:`Default value`

:aspect:`Mandatory`
    No

blacklistedPropertyNames
~~~~~~~~~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    Array

:aspect:`Description`
    An array of property names and/or array keys (RegEx) to be filtered.

:aspect:`Default value`

:aspect:`Mandatory`
    No
