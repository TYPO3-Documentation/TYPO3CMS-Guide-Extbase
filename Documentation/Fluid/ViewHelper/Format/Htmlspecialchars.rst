.. include:: ../../../Includes.txt

f:format.htmlspecialchars
=========================

Wenn Ihr mit Userdaten (Formulardaten) arbeitet, dann sollte dieser Inhalt zuallererst durch diesen ViewHelper.
Denn dieser wandelt alle spitzen Klammern von HTML-Tags in ein nicht mehr interprtierbares Format um. Die HTML-Tags
können also keinen Schaden mehr verursachen und werden im FE angezeigt statt verarbeitet.

Properties
----------

value
~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Der Text der formatiert werden soll

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

keepQuotes
~~~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    Sollen einfache und doppelte Anführungszeichen auch formatiert werden

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No

encoding
~~~~~~~~
:aspect:`Variable type`
    String
   :Description:

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

doubleEncode
~~~~~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    Mit jedem Aufruf diesen ViewHelpers wird ein bereits htmlspecialchared Text immer und immer wieder gehtmlspecialchared. Auf & wird dann &amp; dann &amp;amp;, dann &amp;amp;amp; und so weiter. Um das zu verhindert, kann dieser Parameter auf FALSE gesetzt werden.

:aspect:`Default value`
    TRUE

:aspect:`Mandatory`
    No

Beispiel
--------

::

 <f:format.htmlspecialchars><p><strong>fetter</strong> Text</p></f:format.htmlspecialchars>
