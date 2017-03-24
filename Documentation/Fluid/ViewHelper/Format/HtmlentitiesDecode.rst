.. include:: ../../../Includes.txt

f:format.htmlentitiesDecode
===========================

htmlEntityDecode

Properties
----------

value
~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Der Text der dekodiert werden soll

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

keepQuotes
~~~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    Sollen einfache und doppelte Anführungsstriche auch dekodiert werden?

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No

encoding
~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Wir sind hier im Bereich TYPO3 und da sollte der Zeichensatz auf UTF-8 und nix anderes stehen. Sollte wiedererwartend ein anderer Zeichensatz gewünscht sein, kann dieser hier angegeben werden. Siehe auch Info auf php.net.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

Beispiel
--------

::

 <p><f:format.htmlentitiesDecode>M&uuml;ller &amp; Breuer</f:format.htmlentitiesDecode>

Im Quelltext sieht man wieder ein richtig sauberes: "Müller & Breuer".