.. include:: ../../../Includes.txt

f:uri.typolink
==========

Example
-------

.. code-block:: html

   <f:uri.typolink parameter="1">linktext</f:uri.typolink>


Properties
----------

parameter
~~~~~~~~~

:aspect:`Variable type`
    String

:aspect:`Description`
    UID of the target page to link to.
    TypoScript-Syntax is expected like `19 _blank`.
    See :ref:`t3tsref:stdwrap-typolink`

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    Yes

additionalParams
~~~~~~~~~~~~~~~~

:aspect:`Variable type`
    String

:aspect:`Description`
    Add more parameters to the link. Opposed to `arguments` these names will not be
    prefixed with the extension name.

:aspect:`Default value`
    Empty string

:aspect:`Mandatory`
    No


additionalAttributes
~~~~~~~~~~~~~~~~~~~~

:aspect:`Variable type`
    Array

:aspect:`Description`
   To add attributes to the 'ATag'. The array will automatically be converted to TypoScript syntax Param1=Wert Param2=Wert

:aspect:`Default value`
    Empty array

:aspect:`Mandatory`
    No

useCacheHash
~~~~~~~~~~~~

:aspect:`Variable type`
    Boolean

:aspect:`Description`


:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No

.. highlight:: html

