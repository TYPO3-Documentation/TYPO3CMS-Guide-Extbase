.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:format.printf
===============

Mit diesem ViewHelper können Platzhalter in einem Text mit den Werten auf dem Array ersetzt werden.

Properties
----------

arguments
~~~~~~~~~
:aspect:`Variable type`
    Array

:aspect:`Description`
    Gib hier Werte in Arraynotation ein, die die Platzhalter in dem Text, der sich zwischen den Tags befindet, ersetzt.

:aspect:`Default value`

:aspect:`Mandatory`
    Yes

Beispiel
--------

::

 <f:format.printf arguments="{0: 'Stefan', 1: 2, 2: '4'}">%1$s hat eine %3$d-seitige Dokumentation geschrieben und %2$d Tage dafür gebraucht.</f:format.printf>

Mit %1, %2 und %3 wird der jeweilige Wert aus dem Array geholt. Da es unterschiedliche Datentypen gibt, müssen wir
jedem Wert noch mitteilen, um was für einen Datentyp es sich handelt. Dabei steht $s für string also Text. $d für
einen Zahlenwert, der auch ein Vorzeichen enthalten darf und wie Ihr evtl. schon gesehen habt, habe ich die Zahl 4
als Text deklariert, gebe sie aber als Typ Integer an den Text weiter. Weitere Infos auf php.net

Wenn dieser ViewHelper überhaupt nicht angezeigt wird, dann habt Ihr entweder einen Fehler in Eurem Array oder Ihr
habe die Typdefinition der Variablen wie $s oder $d vergessen mit anzugeben.Parameter