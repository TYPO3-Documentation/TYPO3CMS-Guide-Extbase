.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:format.stripTags
==================

Dieser ViewHelper entfernt sämtliche HTML-Tags aus einem Text.

Properties
----------

value
~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Der Text aus dem die HTML-Tags entfernt werden sollen

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

Beispiel
--------

::

 <f:format.stripTags>Ein <strong>fetter</strong> Text mit einigen <span style="color: blue;">bunten</span> HTML-Tags.</f:format.stripTags>