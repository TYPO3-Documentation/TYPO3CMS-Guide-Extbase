.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:format.number
===============

Mit diesem ViewHelper könnt Ihr Zahlen formatieren. Er arbeitet ähnlich dem `f:format.currency`-ViewHelper

Properties
----------

decimals
~~~~~~~~
:aspect:`Variable type`
    Integer

:aspect:`Description`
    Wie viele Nachkommastellen dürfen angezeigt werden.

:aspect:`Default value`
    2

:aspect:`Mandatory`
    No

decimalSeparator
~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Welcher Zeichen soll für die Trennung von Euro und Cent verwendet werden. Dezimaltrenner.

:aspect:`Default value`
    .

:aspect:`Mandatory`
    No

thousandsSeparator
~~~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Welches Zeichen soll als Tausendertrennzeichen verwendet werden.

:aspect:`Default value`
    ,

:aspect:`Mandatory`
    No

Beispiel
--------

::

 <f:format.number decimals="3" decimalSeparator="." thousandsSeparator=",">1122334455.667788</f:format.number>

ergibt: 1,122,334,455.668. Wie Ihr seht wird sogar automatisch aufgerundet.
