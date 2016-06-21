.. include:: ../../../Includes.txt

f:format.raw
============

`f:format.raw` seit v1.4. Es gibt viele ViewHelper, die Inhalte vor der Ausgabe durch htmlspecialchars und anderen 
Methoden und Funktionen schleusen. Dies zu verhindern stellt auf jeden Fall ein Sicherheitsrisiko dar, kann aber mit 
diesem ViewHelper erreicht werden. Ich denke gerade im Bereich von Formulardaten kann dieser ViewHelper evtl. 
Verwendung finden.

Properties
----------

value
~~~~~
:aspect:`Variable type`
    Mixed

:aspect:`Description`
    Der Text, der unangetastet/unverändert ausgegeben werden soll

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

Beispiel
--------

::

 <f:format.raw value="{formData.nachricht}" />