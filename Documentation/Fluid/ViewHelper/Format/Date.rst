.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:format.date
=============

Konvertiert einen Timestamp in einen lesbaren Datumswert.

Properties
----------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Property
   :Datatype,20:    Variable type
   :Description,40: Description
   :Standard,10:    Default value
   :Mandatory,10:   Mandatory

 - :Property:    date
   :Datatype:    Mixed
   :Description: Entweder ein Objekt vom Typ DateTime oder eine Text/Datum, das in ein DateTime-Objekt konvertiert werden kann. Z.B. 17.01.1979 geht. 17.01.79 geht nicht.
   :Standard:    NULL
   :Mandatory:   No

 - :Property:    format
   :Datatype:    String
   :Description: Wie soll das Datum ausgegeben werden? Format-Syntax ist identisch mit PHPs strftime-Funktion (https://secure.php.net/manual/de/function.strftime.php).
   :Standard:    Y-m-d
   :Mandatory:   No

So schön wie das mit den ganzen DateTime-Objekten ist, prüft die Wert bitte ganz genau. Besucht
Online-Timestamp-Konverter oder gleicht die Wert mit denen in Eurer Datenbank ab. So steht in der Doku z.B. Wenn Ihr
einen Timestamp in ein DateTime-Objekt konvertieren wollt, dann fügt einfach ein @-Zeichen vorne an. Ich hoffe ich
erzähl jetzt nichts Falsches, aber dieser Timestamp wird nach dem RFC2822 konvertiert und das ist Zeitzone 0. In
Deutschland würden wir dem resultierenden DateTimewert also immer hinterherhinken. Die DateTime-Objekt sollten besser
nach ISO8601 konvertiert werden. Dann klappts auch mit der richtigen Zeitzone. Ich für meinen Teil hab mir einen
eigenen ViewHelper geschrieben der sich daran hält und auch Extbase arbeitet intern mit diesem ISO-Format. Siehe:

::

 DataMapper->mapDateTime()

Zitat: return new DateTime(date('c', $timestamp));

Warum das in den ViewHelper noch nicht eingeflossen ist, kann ich mir nicht erklären.

Beispiel
--------

::

 <f:format.date date="17.01.1979" format="d/m/y" />

Beispiel Timestamp
------------------

::

 <f:format.date format="d.m.Y">@1334439765</f:format.date>

Wie schon gesagt: Je nach Land/Kontinent bitte mit Vorsicht zu behandeln.
