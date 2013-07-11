.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../Includes.txt

f:base
======

Dieser ViewHelper bindet den `base-Tag <http://de.selfhtml.org/html/kopfdaten/basis.htm>`_ in Euer HTML-Template
ein.

Eigenschaften
-------------

Dieser ViewHelper besitzt keine Eigenschaften

Beispiel
--------

::

 <f:base />

**Ausgabe**

::

 <base href="http://introgit:8080/">

.. tip::

   Dieser ViewHelper macht nur dann Sinn, wenn Ihr Euer Webseitentemplate (inkl. Kopfbereich <head>) mit Hilfe
   von Fluid aufbaut.
   Wenn kein <head>-Bereich vorhanden ist, wird dieser HTML-Tag im Bodybereich der Webseite eingebunden, wo er nicht hingehört.